# documentku
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes, viewport-fit=cover">
    <title>Jejak Karyaku 🎨</title>

    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/js/all.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>

    <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;500;600;700&display=swap" rel="stylesheet">

    <style>
        * {
            font-family: 'Fredoka', sans-serif;
            -webkit-tap-highlight-color: transparent;
            -webkit-overflow-scrolling: touch;
            box-sizing: border-box;
        }

        body {
            background: #fff9fb;
            color: #334155;
            overflow-x: hidden;
        }

        .kids-btn {
            border-radius: 20px;
            font-weight: 700;
            transition: .2s;
        }

        .kids-btn:active {
            transform: scale(.96);
        }

        .btn-primary {
            background: #ff6b9d;
            color: white;
        }

        .btn-secondary {
            background: #60a5fa;
            color: white;
        }

        .card {
            background: white;
            border-radius: 24px;
            box-shadow: 0 6px 24px rgba(0,0,0,.06);
        }

        .gallery-slider {
            display: flex;
            overflow-x: auto;
            gap: 1rem;
            scroll-snap-type: x mandatory;
            padding-bottom: 1rem;
        }

        .gallery-slider::-webkit-scrollbar {
            display: none;
        }

        .gallery-card {
            min-width: 100%;
            scroll-snap-align: start;
        }

        @media(min-width:768px){
            .gallery-card {
                min-width: calc(50% - .5rem);
            }
        }

        .modal {
            background: rgba(0,0,0,.55);
            backdrop-filter: blur(8px);
        }

        .notification-badge {
            position: relative;
        }
        
        .badge-number {
            position: absolute;
            top: -8px;
            right: -8px;
            background: #ef4444;
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            font-size: 11px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
        }

        .pin-dots {
            display: flex;
            gap: 8px;
            justify-content: center;
            margin-top: 20px;
        }
        .pin-dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            background: #cbd5e1;
            transition: all 0.2s;
        }
        .pin-dot.active {
            background: #ff6b9d;
            width: 24px;
            border-radius: 6px;
        }
    </style>
</head>
<body class="min-h-screen pb-10">

<div id="loading" class="hidden fixed inset-0 z-50 flex items-center justify-center bg-white/90">
    <div class="text-center">
        <div class="animate-spin w-16 h-16 border-4 border-pink-400 border-t-transparent rounded-full mx-auto"></div>
        <p class="mt-4 font-bold text-pink-500">Memuat Data Hebat...</p>
    </div>
</div>

<nav class="sticky top-0 z-40 p-3">
    <div class="max-w-6xl mx-auto bg-white rounded-3xl shadow-lg p-4 flex justify-between items-center">
        <h1 class="text-2xl font-black text-pink-500 cursor-pointer" onclick="showView('home')">JejakKaryaku 🎨</h1>

        <div class="flex gap-2 items-center">
            <button onclick="showView('home')" class="px-4 py-2 rounded-xl hover:bg-pink-50 font-bold">Beranda</button>
            <button id="admin-nav-btn" onclick="openLogin()" class="kids-btn btn-secondary px-5 py-2 relative notification-badge">
                Guru 🍎
                <span id="notif-floating" class="badge-number hidden"></span>
            </button>
        </div>
    </div>
</nav>

<main class="max-w-6xl mx-auto px-4">

    <section id="view-home" class="view space-y-8">
        <div class="text-center py-8">
            <h2 class="text-5xl font-black text-slate-800">Galeri Teman Hebat 🌈</h2>
            <p class="text-slate-400 mt-2 font-bold">Klik foto, masukkan PIN, lalu lihat karya</p>
        </div>
        <div id="student-grid" class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-5 gap-4"></div>
    </section>

    <section id="view-gallery" class="view hidden space-y-5">
        <button onclick="showView('home')" class="kids-btn bg-white px-5 py-3 rounded-2xl shadow font-bold">← Kembali</button>
        <div id="gallery-header" class="card p-6"></div>
        <div class="flex justify-end">
            <button id="download-pdf-btn" onclick="downloadStudentPortfolio()" class="kids-btn bg-green-500 text-white px-5 py-3 rounded-2xl shadow font-bold">
                <i class="fas fa-file-pdf mr-2"></i> Download Portofolio PDF
            </button>
        </div>
        <div id="gallery-grid" class="gallery-slider"></div>
    </section>

    <section id="view-admin" class="view hidden space-y-5">
        <div class="card p-5 flex justify-between items-center">
            <div class="flex items-center gap-3">
                <h2 class="text-3xl font-black">Dashboard Guru 🍏</h2>
                <span id="notif-badge" class="bg-red-500 text-white px-3 py-1 rounded-full text-sm font-bold hidden"></span>
            </div>
            <button onclick="logout()" class="text-red-400 font-bold">Keluar</button>
        </div>
        <div class="grid lg:grid-cols-3 gap-5">
            <div class="space-y-4">
                <button onclick="showModal('modal-student')" class="kids-btn btn-primary w-full py-4 text-lg">+ Tambah Murid</button>
                <div id="admin-student-list" class="space-y-3"></div>
            </div>
            <div class="lg:col-span-2 card p-6">
                <h3 class="text-2xl font-black mb-5">Pesan Orang Tua 💌</h3>
                <div id="admin-comment-log" class="space-y-4 max-h-[600px] overflow-y-auto"></div>
            </div>
        </div>
    </section>

</main>

<div id="modal-password" class="hidden fixed inset-0 modal z-50 flex items-center justify-center p-4">
    <div class="bg-white rounded-3xl p-7 w-full max-w-sm">
        <div id="pin-student-info" class="text-center mb-4">
            <img id="pin-student-avatar" class="w-20 h-20 rounded-full mx-auto object-cover mb-2">
            <h3 id="pin-student-name" class="text-xl font-black"></h3>
        </div>
        <h3 class="text-2xl font-black text-center mb-4">Masukkan PIN 🔐</h3>
        <div class="space-y-4">
            <input type="password" id="pin-input" maxlength="6" 
                class="w-full p-4 text-center text-2xl rounded-2xl bg-slate-100 outline-none tracking-widest"
                placeholder="••••••">
            <div class="pin-dots" id="pin-dots-wrapper">
                <span class="pin-dot"></span><span class="pin-dot"></span>
                <span class="pin-dot"></span><span class="pin-dot"></span>
                <span class="pin-dot"></span><span class="pin-dot"></span>
            </div>
            <button onclick="verifyPassword()" class="kids-btn btn-primary w-full py-4 text-lg">Buka Galeri 🎨</button>
            <button onclick="hideModal('modal-password')" class="w-full text-slate-400 font-bold">Tutup</button>
        </div>
    </div>
</div>

<div id="modal-login" class="hidden fixed inset-0 modal z-50 flex items-center justify-center p-4">
    <div class="bg-white rounded-3xl p-7 w-full max-w-sm">
        <h3 class="text-3xl font-black text-center mb-6">Login Guru 🍎</h3>
        <div class="space-y-3">
            <input id="login-user" type="text" placeholder="Username" class="w-full p-4 rounded-2xl bg-slate-100 outline-none">
            <input id="login-pass" type="password" placeholder="Password" class="w-full p-4 rounded-2xl bg-slate-100 outline-none">
            <button onclick="handleLogin()" class="kids-btn btn-secondary w-full py-4 text-lg">Login</button>
            <button onclick="hideModal('modal-login')" class="w-full text-slate-400 font-bold">Tutup</button>
        </div>
    </div>
</div>

<div id="modal-upload" class="hidden fixed inset-0 modal z-50 flex items-center justify-center p-4">
    <div class="bg-white rounded-3xl w-full max-w-2xl max-h-[90vh] overflow-y-auto p-6">
        <div class="flex justify-between items-center mb-5">
            <h3 id="upload-modal-title" class="text-2xl font-black">Kelola Karya</h3>
            <button onclick="hideModal('modal-upload')" class="text-2xl text-slate-400">✖</button>
        </div>
        <div class="space-y-4 bg-pink-50 p-5 rounded-3xl">
            <input id="up-judul" type="text" placeholder="Judul karya" class="w-full p-4 rounded-2xl outline-none">
            <input id="up-file" type="file" accept="image/*" class="w-full">
            <img id="preview-upload" class="hidden w-full rounded-2xl shadow-md max-h-60 object-cover">
            <button onclick="processUpload()" class="kids-btn btn-primary w-full py-4">Upload 🚀</button>
        </div>
        <div id="admin-work-list" class="space-y-3 mt-5"></div>
    </div>
</div>

<div id="modal-student" class="hidden fixed inset-0 modal z-50 flex items-center justify-center p-4">
    <div class="bg-white rounded-3xl p-6 w-full max-w-sm">
        <h3 id="student-modal-title" class="text-2xl font-black mb-5">Tambah Murid 👶</h3>
        <div class="space-y-3">
            <input id="st-nama" type="text" placeholder="Nama" class="w-full p-4 rounded-2xl bg-slate-100 outline-none">
            <input id="st-pass" type="text" placeholder="PIN (6 Digit)" class="w-full p-4 rounded-2xl bg-slate-100 outline-none" maxlength="6">
            <input id="st-foto" type="text" placeholder="URL Foto Profil (Opsional)" class="w-full p-4 rounded-2xl bg-slate-100 outline-none">
            <button onclick="saveStudent()" class="kids-btn btn-primary w-full py-4">Simpan</button>
            <button onclick="hideModal('modal-student')" class="w-full text-slate-400 font-bold">Tutup</button>
        </div>
    </div>
</div>

<script>
// URL SINKRONISASI DATABASE GOOGLE APPS SCRIPT BERHASIL
const API_URL = 'https://script.google.com/macros/s/AKfycbwyS4RzN6n_7PSCN7ZL3a2crXkNe5rxh_aQ-ldtbKS9AfuBWYXhC_Dffnbans-zG_jk/exec';

let appData = { students: [] };
let isAdminLoggedIn = false;
let currentStudentId = null;
let pendingStudentId = null; 
let editingStudentId = null;

// Fungsi Navigasi dan Tampilan Umum
function toggleLoading(v){
    document.getElementById('loading').classList.toggle('hidden', !v);
}
function showModal(id){
    document.getElementById(id).classList.remove('hidden');
}
function hideModal(id){
    document.getElementById(id).classList.add('hidden');
    if(id === 'modal-student') {
        editingStudentId = null;
        document.getElementById('student-modal-title').innerText = "Tambah Murid 👶";
        document.getElementById('st-nama').value = '';
        document.getElementById('st-pass').value = '';
        document.getElementById('st-foto').value = '';
    }
}
function showView(id){
    document.querySelectorAll('.view').forEach(v=>{ v.classList.add('hidden'); });
    document.getElementById('view-'+id).classList.remove('hidden');
    window.scrollTo({top:0, behavior:'smooth'});
}

// Mengambil Data dari Google Sheets via API
async function fetchData(){
    toggleLoading(true);
    try {
        const res = await fetch(API_URL, {
            method:'POST',
            body: JSON.stringify({ action:'getInitialData' })
        });
        const json = await res.json();
        if(json.success){
            appData.students = json.data || [];
            renderHome();
            if(isAdminLoggedIn) renderAdmin();
        }
    } catch(err){ console.error(err); }
    toggleLoading(false);
}

// Menampilkan Daftar Murid di Beranda Utama
function renderHome(){
    const grid = document.getElementById('student-grid');
    if(!appData.students || !appData.students.length){
        grid.innerHTML = `<div class="col-span-full text-center py-20 text-slate-400 font-bold">Belum ada siswa</div>`;
        return;
    }
    grid.innerHTML = appData.students.map(s=>`
        <div onclick="requestPassword('${s.id}')" class="card p-4 text-center cursor-pointer hover:shadow-xl transition">
            <img loading="lazy" src="${s.foto || 'https://ui-avatars.com/api/?name='+encodeURIComponent(s.nama)}" class="w-full aspect-square rounded-2xl object-cover mb-3">
            <h3 class="font-black truncate text-slate-700">${s.nama}</h3>
            <p class="text-xs text-slate-400 mt-1 font-bold">${s.karya?.length || 0} karya</p>
        </div>
    `).join('');
}

// Sistem Pengecekan PIN Murid sebelum Membuka Galeri
function requestPassword(studentId){
    const student = appData.students.find(x=>x.id===studentId);
    if(!student) return;
    pendingStudentId = studentId;
    document.getElementById('pin-student-name').innerText = student.nama;
    document.getElementById('pin-student-avatar').src = student.foto || 'https://ui-avatars.com/api/?name='+encodeURIComponent(student.nama);
    document.getElementById('pin-input').value = '';
    updatePinDots('');
    showModal('modal-password');
    setTimeout(()=> document.getElementById('pin-input').focus(), 100);
}

function updatePinDots(value){
    const dots = document.querySelectorAll('#pin-dots-wrapper .pin-dot');
    dots.forEach((dot, idx)=> {
        dot.classList.toggle('active', idx < value.length);
    });
}

document.getElementById('pin-input')?.addEventListener('input', function(e){
    updatePinDots(e.target.value);
});
document.getElementById('pin-input')?.addEventListener('keypress', function(e){
    if(e.key === 'Enter') verifyPassword();
});

async function verifyPassword(){
    const inputPin = document.getElementById('pin-input').value.trim();
    if(!inputPin) return alert('Masukkan PIN terlebih dahulu');
    const student = appData.students.find(x=>x.id===pendingStudentId);
    if(!student) return;
    
    if(inputPin === student.pass){
        hideModal('modal-password');
        renderGallery(pendingStudentId);
    } else {
        alert('PIN salah! Silakan coba lagi.');
        document.getElementById('pin-input').value = '';
        updatePinDots('');
        document.getElementById('pin-input').focus();
    }
}

// Menampilkan Halaman Galeri Karya Siswa secara Detail
function renderGallery(id){
    currentStudentId = id;
    const s = appData.students.find(x=>x.id===id);
    if(!s) return;

    document.getElementById('gallery-header').innerHTML = `
        <div class="flex items-center gap-5">
            <img src="${s.foto || 'https://ui-avatars.com/api/?name='+encodeURIComponent(s.nama)}" class="w-24 h-24 rounded-3xl object-cover shadow-md">
            <div>
                <h2 class="text-3xl font-black text-pink-500">${s.nama}</h2>
                <p class="text-slate-400 font-bold mt-1">${s.karya?.length || 0} karya hebat ✨</p>
            </div>
        </div>
    `;

    const grid = document.getElementById('gallery-grid');
    if(!s.karya || !s.karya.length){
        grid.innerHTML = `<div class="w-full card p-10 text-center text-slate-400 font-bold">Belum ada karya</div>`;
        showView('gallery');
        return;
    }

    grid.innerHTML = s.karya.map(k=>`
        <div class="gallery-card card overflow-hidden flex flex-col md:flex-row max-w-full">
            <img src="${k.link}" class="w-full md:w-1/2 aspect-[4/3] object-cover bg-slate-100">
            <div class="p-5 flex-1 flex flex-col justify-between">
                <div>
                    <div class="flex justify-between items-start gap-3 mb-3">
                        <h3 class="text-xl font-black text-slate-700">${k.judul}</h3>
                        <span class="text-xs text-slate-400 font-bold">${new Date(k.date).toLocaleDateString('id-ID')}</span>
                    </div>
                    <div class="space-y-3 max-h-[180px] overflow-y-auto mb-3">
                        ${(s.percakapan || []).filter(p=>p.workId===k.id).map(c=>`
                            <div class="bg-slate-50 p-3 rounded-2xl text-xs">
                                <p class="font-black text-blue-500">Orang Tua:</p>
                                <p class="font-medium mt-0.5">${c.pesanWali}</p>
                                ${c.balasanGuru ? `
                                    <div class="bg-green-50 rounded-xl p-2 mt-2">
                                        <p class="font-black text-green-600">Guru:</p>
                                        <p class="font-medium mt-0.5 text-slate-700">${c.balasanGuru}</p>
                                    </div>
                                `:''}
                            </div>
                        `).join('')}
                    </div>
                </div>
                <div class="flex gap-2">
                    <input id="input-chat-${k.id}" type="text" placeholder="Tulis pesan orang tua..." class="flex-1 p-3 rounded-xl border text-sm outline-none">
                    <button onclick="sendComment('${k.id}')" class="kids-btn btn-primary px-4">➤</button>
                </div>
            </div>
        </div>
    `).join('');
    showView('gallery');
}

// Sistem Autentikasi Login Admin/Guru
function openLogin(){
    if(isAdminLoggedIn) { showView('admin'); return; }
    showModal('modal-login');
}
function handleLogin(){
    if(document.getElementById('login-user').value==='admin' && document.getElementById('login-pass').value==='guru123'){
        isAdminLoggedIn = true;
        hideModal('modal-login');
        document.getElementById('admin-nav-btn').innerHTML = 'Dashboard 🏠 <span id="notif-floating" class="badge-number hidden"></span>';
        renderAdmin();
        showView('admin');
    } else { alert('Login salah!'); }
}
function logout(){
    isAdminLoggedIn = false;
    document.getElementById('admin-nav-btn').innerHTML = 'Guru 🍎 <span id="notif-floating" class="badge-number hidden"></span>';
    showView('home');
}

// Dashboard Guru: List Murid Kontrol CRUD
function renderAdmin(){
    const list = document.getElementById('admin-student-list');
    list.innerHTML = appData.students.map(s=>`
        <div class="card p-4 bg-white border border-slate-100 shadow-sm">
            <div class="flex justify-between items-center gap-3">
                <div class="flex items-center gap-3">
                    <img src="${s.foto || 'https://ui-avatars.com/api/?name='+encodeURIComponent(s.nama)}" class="w-12 h-12 rounded-xl object-cover">
                    <div>
                        <p class="font-black text-slate-700 text-sm">${s.nama}</p>
                        <p class="text-xs text-slate-400 font-bold">PIN: ${s.pass} | ${s.karya?.length || 0} Karya</p>
                    </div>
                </div>
                <div class="flex gap-1">
                    <button onclick="triggerEditStudent('${s.id}')" class="w-8 h-8 rounded-lg bg-yellow-50 text-yellow-600 text-xs"><i class="fas fa-pen"></i></button>
                    <button onclick="manageKarya('${s.id}')" class="w-8 h-8 rounded-lg bg-blue-50 text-blue-600 text-xs"><i class="fas fa-images"></i></button>
                    <button onclick="deleteStudent('${s.id}')" class="w-8 h-8 rounded-lg bg-red-50 text-red-500 text-xs"><i class="fas fa-trash"></i></button>
                    <button onclick="exportPortfolio('${s.id}', true)" class="w-8 h-8 rounded-lg bg-green-50 text-green-600 text-xs"><i class="fas fa-file-pdf"></i></button>
                </div>
            </div>
        </div>
    `).join('');
    renderCommentInbox();
}

// Fitur Kotak Masuk Pesan Wali Murid & Notifikasi Angka Realtime
function renderCommentInbox(){
    const wrap = document.getElementById('admin-comment-log');
    let allComments = [];
    appData.students.forEach(s=>{
        (s.percakapan || []).forEach(c=>{
            allComments.push({ ...c, student:s, karya: s.karya?.find(k=>k.id===c.workId) });
        });
    });
    allComments.sort((a,b)=> new Date(b.date) - new Date(a.date));
    
    let unreplyCount = allComments.filter(x=>!x.balasanGuru).length;
    document.getElementById('notif-badge').classList.toggle('hidden', unreplyCount===0);
    if(unreplyCount > 0) document.getElementById('notif-badge').innerText = `${unreplyCount} Baru`;
    document.getElementById('notif-floating').classList.toggle('hidden', unreplyCount===0);
    if(unreplyCount > 0) document.getElementById('notif-floating').innerText = unreplyCount;

    if(!allComments.length){
        wrap.innerHTML = `<div class="p-10 text-center text-slate-400 font-bold">Belum ada pesan masuk.</div>`;
        return;
    }

    wrap.innerHTML = allComments.map(c=>`
        <div class="bg-slate-50 rounded-2xl p-4 border border-slate-100 flex gap-4">
            ${c.karya ? `<img src="${c.karya.link}" class="w-24 h-24 object-cover rounded-xl bg-white shadow-sm">`:''}
            <div class="flex-1">
                <div class="flex items-center gap-2">
                    <h4 class="font-black text-slate-700">${c.student.nama}</h4>
                    ${!c.balasanGuru ? `<span class="bg-red-500 text-white text-[10px] px-2 py-0.5 rounded-full font-bold">Baru</span>`:''}
                </div>
                <p class="text-xs font-bold text-pink-400 mt-0.5">Karya: ${c.karya?.judul || 'Karya'}</p>
                <div class="bg-white p-3 rounded-xl border mt-2 text-sm text-slate-600">
                    <span class="text-xs font-bold text-blue-500 block mb-1">Pesan Wali:</span>
                    "${c.pesanWali}"
                </div>
                ${c.balasanGuru ? `
                    <div class="bg-green-50 p-3 rounded-xl border border-green-100 mt-2 text-sm text-green-800">
                        <span class="text-xs font-bold text-green-600 block mb-1">Balasan Anda:</span>
                        "${c.balasanGuru}"
                    </div>
                ` : `
                    <div class="flex gap-2 mt-2">
                        <input id="reply-${c.id}" type="text" placeholder="Tulis balasan guru..." class="flex-1 p-2 rounded-xl text-xs border outline-none">
                        <button onclick="replyComment('${c.id}')" class="kids-btn btn-primary px-4 text-xs">Kirim</button>
                    </div>
                `}
            </div>
        </div>
    `).join('');
}

// Membalas Komentar Orang Tua
async function replyComment(commentId){
    const text = document.getElementById(`reply-${commentId}`).value.trim();
    if(!text) return;
    toggleLoading(true);
    try {
        await fetch(API_URL, { method:'POST', body: JSON.stringify({ action:'replyComment', commentId, replyText: text }) });
        await fetchData();
    } catch(err){ alert('Gagal membalas'); }
    toggleLoading(false);
}

// Membuka daftar koleksi gambar karya per siswa
function manageKarya(id){
    currentStudentId = id;
    const s = appData.students.find(x=>x.id===id);
    document.getElementById('upload-modal-title').innerText = `Koleksi Karya - ${s.nama}`;
    const list = document.getElementById('admin-work-list');
    list.innerHTML = (s.karya || []).map(k=>`
        <div class="flex justify-between items-center bg-slate-50 p-3 rounded-2xl">
            <div class="flex items-center gap-3">
                <img src="${k.link}" class="w-12 h-12 rounded-xl object-cover bg-white">
                <p class="font-black text-sm text-slate-700">${k.judul}</p>
            </div>
            <button onclick="deleteKarya('${k.id}')" class="text-red-500 p-2"><i class="fas fa-trash"></i></button>
        </div>
    `).join('');
    showModal('modal-upload');
}

// Handler Preview Gambar sebelum Upload
document.getElementById('up-file')?.addEventListener('change', function(e){
    const file = e.target.files[0];
    if(!file) return;
    const reader = new FileReader();
    reader.onload = function(ev){
        const img = document.getElementById('preview-upload');
        img.src = ev.target.result;
        img.classList.remove('hidden');
    };
    reader.readAsDataURL(file);
});

// Memproses konversi kompresi gambar lalu mengirimkannya ke hosting Drive via AppScript
async function processUpload(){
    const judul = document.getElementById('up-judul').value.trim();
    const fileInput = document.getElementById('up-file');
    if(!judul || !fileInput.files[0]) return alert('Isi judul dan pilih file gambar terlebih dahulu');
    toggleLoading(true);
    
    const file = fileInput.files[0];
    const reader = new FileReader();
    reader.onload = async(e)=>{
        const img = new Image();
        img.onload = async function(){
            const canvas = document.createElement('canvas');
            let width = img.width, height = img.height;
            if(width > 1000){ height *= 1000 / width; width = 1000; }
            canvas.width = width; canvas.height = height;
            const ctx = canvas.getContext('2d');
            ctx.drawImage(img,0,0,width,height);
            
            const base64 = canvas.toDataURL('image/jpeg',0.7).split(',')[1];
            try {
                const res = await fetch(API_URL, {
                    method:'POST',
                    body: JSON.stringify({ action:'uploadKarya', studentId: currentStudentId, judul, fileName: file.name, fileData: base64 })
                });
                const json = await res.json();
                if(json.success){
                    document.getElementById('up-judul').value = '';
                    document.getElementById('up-file').value = '';
                    document.getElementById('preview-upload').classList.add('hidden');
                    await fetchData();
                    manageKarya(currentStudentId);
                }
            } catch(err){ alert('Upload gagal'); }
            toggleLoading(false);
        };
        img.src = e.target.result;
    };
    reader.readAsDataURL(file);
}

async function deleteKarya(workId){
    if(!confirm('Hapus karya ini secara permanen?')) return;
    toggleLoading(true);
    try {
        await fetch(API_URL, { method:'POST', body: JSON.stringify({ action:'deleteKarya', workId }) });
        await fetchData();
        manageKarya(currentStudentId);
    } catch(err){ alert('Gagal menghapus'); }
    toggleLoading(false);
}

// Fungsi Trigger edit data siswa agar memunculkan form terisi
function triggerEditStudent(id){
    const s = appData.students.find(x=>x.id===id);
    if(!s) return;
    editingStudentId = id;
    document.getElementById('student-modal-title').innerText = "Edit Data Murid ✏️";
    document.getElementById('st-nama').value = s.nama;
    document.getElementById('st-pass').value = s.pass;
    document.getElementById('st-foto').value = s.foto || '';
    showModal('modal-student');
}

// Simpan Tambah baru / Edit Data Siswa ke Sheets
async function saveStudent(){
    const nama = document.getElementById('st-nama').value.trim();
    const pass = document.getElementById('st-pass').value.trim();
    const foto = document.getElementById('st-foto').value.trim();
    if(!nama || !pass) return alert('Nama dan PIN wajib diisi');
    toggleLoading(true);
    try {
        let payload = { action: 'addStudent', id: 'S' + Date.now(), nama, pass, foto };
        if(editingStudentId) payload = { action: 'editStudent', id: editingStudentId, nama, pass, foto };
        
        const res = await fetch(API_URL, { method:'POST', body: JSON.stringify(payload) });
        const json = await res.json();
        if(json.success){
            hideModal('modal-student');
            await fetchData();
        }
    } catch(err){ alert('Gagal menyimpan data murid'); }
    toggleLoading(false);
}

async function deleteStudent(id){
    if(!confirm('Hapus murid ini beserta semua datanya?')) return;
    toggleLoading(true);
    try {
        await fetch(API_URL, { method:'POST', body: JSON.stringify({ action:'deleteStudent', id }) });
        await fetchData();
    } catch(err){ alert('Gagal menghapus murid'); }
    toggleLoading(false);
}

// Kirim Komentar Orang Tua Murid
async function sendComment(workId){
    const input = document.getElementById(`input-chat-${workId}`);
    const text = input.value.trim();
    if(!text) return;
    toggleLoading(true);
    try {
        await fetch(API_URL, { method:'POST', body: JSON.stringify({ action:'addComment', workId, studentId: currentStudentId, comment:text }) });
        input.value = '';
        await fetchData();
        renderGallery(currentStudentId);
    } catch(err) { alert('Gagal mengirim pesan'); }
    toggleLoading(false);
}

// Pengubah Link Gambar menjadi Data Base64 untuk keperluan PDF Engine
async function loadImageAsBase64(url){
    return new Promise((resolve,reject)=>{
        const img = new Image();
        img.crossOrigin = 'Anonymous';
        img.onload = function(){
            const canvas = document.createElement('canvas');
            canvas.width = img.width; canvas.height = img.height;
            const ctx = canvas.getContext('2d');
            ctx.drawImage(img,0,0);
            resolve(canvas.toDataURL('image/jpeg'));
        };
        img.onerror = () => resolve(null); 
        img.src = url;
    });
}

// GENERATOR PORTOFOLIO CETAK PDF TANPA PECAH (SINKRONISASI LINK RESOLUSI BERSIH)
async function exportPortfolio(id, isAdminExport = false){
    const s = appData.students.find(x=>x.id===id);
    if(!s) return;
    toggleLoading(true);
    const { jsPDF } = window.jspdf;
    const doc = new jsPDF({ orientation:'portrait', unit:'mm', format:'a4' });

    // HALAMAN SAMPUL (COVER)
    doc.setFillColor(255,107,157);
    doc.rect(0,0,210,297,'F');
    doc.setTextColor(255,255,255);
    
    try {
        const studentPhoto = s.foto || 'https://ui-avatars.com/api/?name='+encodeURIComponent(s.nama)+'&background=ffffff&color=ff6b9d&size=200';
        const photoBase64 = await loadImageAsBase64(studentPhoto);
        if(photoBase64) {
            doc.addImage(photoBase64, 'JPEG', 75, 60, 60, 60);
            doc.setDrawColor(255,255,255); doc.setLineWidth(1); doc.circle(105, 90, 31, 'S');
        }
    } catch(err){}
    
    doc.setFontSize(28); doc.text('PORTOFOLIO KARYA', 105, 155, { align: 'center' });
    doc.setFontSize(22); doc.text(s.nama, 105, 175, { align: 'center' });
    doc.setFontSize(14); doc.text(`${s.karya?.length || 0} Karya Hebat ✨`, 105, 190, { align: 'center' });
    
    // HALAMAN ISI KARYA DAN PERCAKAPAN
    if(s.karya && s.karya.length){
        for(let i=0; i<s.karya.length; i++){
            doc.addPage();
            const k = s.karya[i];
            doc.setFillColor(255,240,245); doc.rect(0,0,210,25,'F');
            doc.setTextColor(40); doc.setFontSize(18); doc.text(k.judul, 15, 16);
            
            try {
                const img = await loadImageAsBase64(k.link);
                if(img) doc.addImage(img, 'JPEG', 15, 35, 180, 110);
            } catch(err){}

            let y = 160;
            doc.setFontSize(10); doc.text(`Tanggal Upload: ${new Date(k.date).toLocaleDateString('id-ID')}`, 15, y);
            y += 15;
            
            const chats = (s.percakapan || []).filter(p=>p.workId===k.id);
            chats.forEach(c=>{
                if(y > 240){ doc.addPage(); y = 20; }
                doc.setFillColor(240,248,255); doc.roundedRect(15, y, 180, 20, 3, 3, 'F');
                doc.setFontSize(9); doc.text(`Pesan Wali: "${c.pesanWali}"`, 20, y+11);
                y += 25;
                if(c.balasanGuru){
                    doc.setFillColor(240,255,240); doc.roundedRect(15, y, 180, 20, 3, 3, 'F');
                    doc.text(`Balasan Guru: "${c.balasanGuru}"`, 20, y+11);
                    y += 25;
                }
            });
        }
    }
    doc.save(`Portofolio-${s.nama}.pdf`);
    toggleLoading(false);
}

// Inisialisasi awal saat dokumen dibuka
window.onload = ()=>{
    fetchData();
};
</script>

</body>
</html>
