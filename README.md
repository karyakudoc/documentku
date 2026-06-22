<!doctype html>
<html lang="id"><head><script src="/_sdk/telemetry_sdk.js"></script>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Platform Pembelajaran Bahasa Indonesia Kelas V</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;700&amp;family=Fraunces:wght@700;900&amp;display=swap" rel="stylesheet">
  <script src="https://cdn.jsdelivr.net/npm/lucide@0.263.0/dist/umd/lucide.min.js"></script>
  <style>
body{font-family:'DM Sans',sans-serif}
h1,h2,h3{font-family:'Fraunces',serif}
.tab-active{background:#f59e0b;color:#fff;transform:scale(1.05)}
.tab-btn{transition:all .2s}
.fade-in{animation:fadeIn .3s ease}
@keyframes fadeIn{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}
.option-btn{transition:all .15s}
.option-btn:hover:not(:disabled){transform:translateY(-2px);box-shadow:0 4px 12px rgba(0,0,0,.15)}
.correct{background:#10b981!important;color:#fff!important;border-color:#10b981!important}
.incorrect{background:#ef4444!important;color:#fff!important;border-color:#ef4444!important}
.mode-active{background:#d97706;color:#fff}
.chap-active{background:#7c2d12;color:#fff}
.game-type-active{background:#7c2d12;color:#fff}
.match-card{transition:all .2s;cursor:pointer}
.match-card.selected{ring:3px;box-shadow:0 0 0 3px #f59e0b}
.match-card.matched{background:#10b981!important;color:#fff!important;pointer-events:none}
.letter-btn{transition:all .1s}
.letter-btn:hover{transform:scale(1.1)}
.letter-btn.used{opacity:.3;pointer-events:none}
.puzzle-word{cursor:grab;transition:all .15s}
.puzzle-word:hover{transform:scale(1.05)}
.puzzle-word.placed{opacity:.4;pointer-events:none}
</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
  <script src="/_sdk/resizing_sdk.js" type="text/javascript"></script>
 </head>
 <body data-template-id="__page-root" class="min-h-screen" style="background: linear-gradient(135deg, rgb(254, 243, 199), rgb(253, 230, 138), rgb(251, 191, 36));">
  <header class="relative overflow-hidden"><img data-template-id="hero-image" class="canva-image absolute inset-0 w-full h-full object-cover opacity-20" loading="lazy" src="https://images.pexels.com/photos/8618015/pexels-photo-8618015.jpeg?auto=compress&amp;cs=tinysrgb&amp;w=1280" alt="Diverse children participating actively in a colorful school classroom setting.">
   <div class="relative z-10 text-center py-10 px-4">
    <h1 data-template-id="main-title" class="canva-text text-4xl md:text-5xl font-black mb-2" style="color: rgb(120, 53, 15); font-weight: 900; font-style: normal; font-size: 32px;">Platform Bahasa Indonesia 🌟</h1>
    <p data-template-id="subtitle" class="canva-text text-lg opacity-80" style="color: rgb(146, 64, 14); font-weight: 500; font-style: normal; font-size: 16px;">Kelas V — Bab 1 sampai Bab 7 | UPT SD Negeri 1 Wargomulyo</p>
   </div>
  </header>
  <main class="max-w-4xl mx-auto px-4 pb-12">
   <div class="flex flex-wrap gap-2 justify-center -mt-5 mb-4"><button class="chap-btn chap-active px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900" onclick="switchChapter(0)">Bab 1</button> <button class="chap-btn px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900 bg-white text-amber-900" onclick="switchChapter(1)">Bab 2</button> <button class="chap-btn px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900 bg-white text-amber-900" onclick="switchChapter(2)">Bab 3</button> <button class="chap-btn px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900 bg-white text-amber-900" onclick="switchChapter(3)">Bab 4</button> <button class="chap-btn px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900 bg-white text-amber-900" onclick="switchChapter(4)">Bab 5</button> <button class="chap-btn px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900 bg-white text-amber-900" onclick="switchChapter(5)">Bab 6</button> <button class="chap-btn px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900 bg-white text-amber-900" onclick="switchChapter(6)">Bab 7</button>
   </div>
   <div id="chapter-title" class="text-center text-sm font-semibold text-amber-800 mb-6">
    Bab 1: Aku yang Unik
   </div>
   <nav class="flex flex-wrap gap-2 justify-center mb-8" role="tablist"><button data-template-id="tab-game" class="canva-button tab-btn tab-active px-5 py-2.5 rounded-full font-semibold shadow" onclick="switchSection('game')" role="tab" style="font-weight: 600; font-style: normal; font-size: 16px;">🎮 Game</button> <button data-template-id="tab-materi" class="canva-button tab-btn px-5 py-2.5 rounded-full font-semibold shadow bg-white text-gray-700" onclick="switchSection('materi')" role="tab" style="font-weight: 600; font-style: normal; font-size: 16px;">📖 Materi</button> <button data-template-id="tab-media" class="canva-button tab-btn px-5 py-2.5 rounded-full font-semibold shadow bg-white text-gray-700" onclick="switchSection('media')" role="tab" style="font-weight: 600; font-style: normal; font-size: 16px;">🎬 Media</button> <button data-template-id="tab-modul" class="canva-button tab-btn px-5 py-2.5 rounded-full font-semibold shadow bg-white text-gray-700" onclick="switchSection('modul')" role="tab" style="font-weight: 600; font-style: normal; font-size: 16px;">📋 Modul</button> <button data-template-id="tab-refleksi" class="canva-button tab-btn px-5 py-2.5 rounded-full font-semibold shadow bg-white text-gray-700" onclick="switchSection('refleksi')" role="tab" style="font-weight: 600; font-style: normal; font-size: 16px;">💭 Refleksi</button>
   </nav><!-- GAME SECTION -->
   <section id="section-game" class="fade-in">
    <div class="flex flex-wrap gap-2 justify-center mb-4"><button class="mode-btn mode-active px-4 py-2 rounded-full text-sm font-semibold border-2 border-amber-600" onclick="switchMode(0)">🧑 Sendiri</button> <button class="mode-btn px-4 py-2 rounded-full text-sm font-semibold border-2 border-amber-600 bg-white text-amber-800" onclick="switchMode(1)">👫 Berpasangan</button> <button class="mode-btn px-4 py-2 rounded-full text-sm font-semibold border-2 border-amber-600 bg-white text-amber-800" onclick="switchMode(2)">👥 Berkelompok</button>
    </div>
    <div id="mode-info" class="text-center text-sm text-amber-800 mb-4 italic">
     Jawab soal sendiri dan kumpulkan skor tertinggi!
    </div><!-- Game Type Tabs -->
    <div id="game-type-tabs" class="flex flex-wrap gap-2 justify-center mb-4"><button class="game-type-btn game-type-active px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900" onclick="switchGameType(0)">📝 Quiz</button> <button class="game-type-btn px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900 bg-white text-amber-900" onclick="switchGameType(1)">🔤 Acak Kata</button> <button class="game-type-btn px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900 bg-white text-amber-900" onclick="switchGameType(2)">✅ Benar/Salah</button> <button class="game-type-btn px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900 bg-white text-amber-900" onclick="switchGameType(3)">🔗 Berpasangan</button> <button class="game-type-btn px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900 bg-white text-amber-900" onclick="switchGameType(4)">✏️ Bermain Kata</button> <button class="game-type-btn px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900 bg-white text-amber-900" onclick="switchGameType(5)">🧩 Puzzle</button>
    </div>
    <div class="text-center mb-4"><span id="score-display" class="inline-block bg-white/80 backdrop-blur px-4 py-1.5 rounded-full font-semibold text-amber-700 shadow-sm">Skor: 0 / 0</span>
    </div>
    <div id="game-area" class="bg-white rounded-2xl shadow-lg p-6 md:p-8 fade-in"></div>
    <div id="feedback" class="mt-4 text-center font-semibold text-lg min-h-[2rem]"></div>
    <div class="text-center mt-4"><button id="next-btn" class="hidden px-6 py-2.5 bg-amber-500 hover:bg-amber-600 text-white font-semibold rounded-full shadow transition" onclick="nextQuestion()">Soal Berikutnya →</button>
    </div>
   </section><!-- MATERI SECTION -->
   <section id="section-materi" class="hidden fade-in">
    <div class="bg-white rounded-2xl shadow-lg p-6 md:p-8">
     <div class="flex items-center gap-4 mb-4"><img data-template-id="materi-image" class="canva-image w-32 h-32 rounded-xl object-cover flex-shrink-0" loading="lazy" src="https://images.pexels.com/photos/10638213/pexels-photo-10638213.jpeg?auto=compress&amp;cs=tinysrgb&amp;w=800" alt="Three children in school uniforms reading books together in a vibrant library setting.">
      <div>
       <h2 data-template-id="materi-title" class="canva-text text-2xl font-bold mb-1" style="color: rgb(120, 53, 15); font-weight: 700; font-style: normal; font-size: 24px;">Materi Pembelajaran</h2>
       <p data-template-id="materi-desc" class="canva-text text-gray-600" style="color: rgb(107, 114, 128); font-weight: 400; font-style: normal; font-size: 16px;">Ringkasan materi setiap bab. Pilih bab di atas untuk melihat materi yang sesuai.</p>
      </div>
     </div>
     <div id="materi-content" class="space-y-4"></div>
    </div>
   </section><!-- MEDIA SECTION -->
   <section id="section-media" class="hidden fade-in">
    <div class="bg-white rounded-2xl shadow-lg p-6 md:p-8">
     <h2 data-template-id="media-title" class="canva-text text-2xl font-bold mb-4" style="color: rgb(120, 53, 15); font-weight: 700; font-style: normal; font-size: 24px;">Media Pembelajaran</h2>
     <div class="grid md:grid-cols-2 gap-4">
      <div data-template-id="media-card-1" class="canva-card rounded-xl overflow-hidden shadow" style="background: rgb(255, 255, 255);"><img data-template-id="media-img-1" class="canva-image w-full h-40 object-cover" loading="lazy" src="https://images.pexels.com/photos/10638224/pexels-photo-10638224.jpeg?auto=compress&amp;cs=tinysrgb&amp;w=800" alt="Group of children reading books together in a classroom setting.">
       <div class="p-4">
        <h3 data-template-id="media-label-1" class="canva-text font-bold" style="color: rgb(17, 24, 39); font-weight: 700; font-style: normal; font-size: 19px;">Buku Siswa &amp; Teks Bacaan</h3>
        <p data-template-id="media-desc-1" class="canva-text text-sm text-gray-600 mt-1" style="color: rgb(107, 114, 128); font-weight: 400; font-style: normal; font-size: 16px;">Buku 'Bahasa Indonesia: Bergerak Bersama' Kelas V sebagai sumber utama pembelajaran.</p>
       </div>
      </div>
      <div data-template-id="media-card-2" class="canva-card rounded-xl overflow-hidden shadow" style="background: rgb(255, 255, 255);"><img data-template-id="media-img-2" class="canva-image w-full h-40 object-cover" loading="lazy" src="https://images.pexels.com/photos/5849168/pexels-photo-5849168.jpeg?auto=compress&amp;cs=tinysrgb&amp;w=800" alt="Group of Indonesian children smiling and posing for the camera in a classroom setting.">
       <div class="p-4">
        <h3 data-template-id="media-label-2" class="canva-text font-bold" style="color: rgb(17, 24, 39); font-weight: 700; font-style: normal; font-size: 19px;">Kegiatan &amp; Permainan</h3>
        <p data-template-id="media-desc-2" class="canva-text text-sm text-gray-600 mt-1" style="color: rgb(107, 114, 128); font-weight: 400; font-style: normal; font-size: 16px;">Berbagai permainan interaktif dan kegiatan kelompok untuk pembelajaran menyenangkan.</p>
       </div>
      </div>
     </div>
     <div data-template-id="media-info-box" class="canva-panel bg-amber-50 rounded-xl p-4 mt-4" style="background: rgb(255, 251, 235);">
      <h3 data-template-id="media-info-title" class="canva-text font-bold mb-2" style="color: rgb(146, 64, 14); font-weight: 700; font-style: normal; font-size: 19px;">🌐 Pemanfaatan Digital</h3>
      <p id="media-info-dynamic" class="text-sm text-gray-700"></p>
     </div>
    </div>
   </section><!-- MODUL SECTION -->
   <section id="section-modul" class="hidden fade-in">
    <div class="bg-white rounded-2xl shadow-lg p-6 md:p-8">
     <div class="flex items-center gap-4 mb-2"><img data-template-id="modul-image" class="canva-image w-28 h-28 rounded-xl object-cover flex-shrink-0" loading="lazy" src="https://images.pexels.com/photos/5427998/pexels-photo-5427998.jpeg?auto=compress&amp;cs=tinysrgb&amp;w=800" alt="A diverse group of students in an English class with a smiling teacher at the whiteboard.">
      <div>
       <h2 data-template-id="modul-title" class="canva-text text-2xl font-bold" style="color: rgb(120, 53, 15); font-weight: 700; font-style: normal; font-size: 24px;">Modul Ajar</h2>
       <p id="modul-sub-dynamic" class="text-gray-600 text-sm"></p>
      </div>
     </div>
     <div data-template-id="modul-info" class="canva-panel bg-yellow-50 rounded-xl p-4 mb-4" style="background: rgb(254, 252, 232);">
      <p data-template-id="modul-info-text" class="canva-text text-sm text-gray-800" style="color: rgb(120, 53, 15); font-weight: 400; font-style: normal; font-size: 16px;">Penyusun: Nurhamidah Safitri, S.Pd.SD | UPT SD Negeri 1 Wargomulyo | 2025/2026 | Fase C | Pendekatan Deep Learning</p>
     </div>
     <div id="modul-items" class="space-y-3"></div>
    </div>
   </section><!-- REFLEKSI SECTION -->
   <section id="section-refleksi" class="hidden fade-in">
    <div class="bg-white rounded-2xl shadow-lg p-6 md:p-8">
     <div class="flex items-center gap-4 mb-4"><img data-template-id="refleksi-image" class="canva-image w-28 h-28 rounded-xl object-cover flex-shrink-0" loading="lazy" src="https://images.pexels.com/photos/8423452/pexels-photo-8423452.jpeg?auto=compress&amp;cs=tinysrgb&amp;w=800" alt="Focused young girl writing at a desk with school supplies, creating a study atmosphere.">
      <div>
       <h2 data-template-id="refleksi-title" class="canva-text text-2xl font-bold" style="color: rgb(120, 53, 15); font-weight: 700; font-style: normal; font-size: 24px;">Refleksi Pembelajaran</h2>
       <p data-template-id="refleksi-desc" class="canva-text text-gray-600 text-sm" style="color: rgb(107, 114, 128); font-weight: 400; font-style: normal; font-size: 16px;">Renungkan apa yang telah kamu pelajari! Pilih bab untuk melihat pertanyaan refleksi.</p>
      </div>
     </div>
     <div id="refleksi-items" class="space-y-3"></div>
    </div>
   </section>
  </main>
  <script src="/_sdk/editing_sdk.js"></script>
  <script>
const chapters=[
{
name:"Bab 1: Aku yang Unik",
categories:["Kata Sifat","Sinonim & Antonim","Kalimat Majemuk","Imbuhan Pe-"],
questions:[
[{q:"Manakah yang merupakan kata sifat?",options:["berlari","rajin","meja","membaca"],answer:1},{q:"Kata sifat dalam kalimat: 'Rani adalah anak yang periang.'",options:["anak","periang","adalah","Rani"],answer:1},{q:"Manakah kata sifat?",options:["menulis","kursi","pemaaf","sekolah"],answer:2},{q:"Kata sifat yang cocok: 'Darman sangat ____'",options:["pendiam","bermain","buku","pergi"],answer:0},{q:"Manakah yang BUKAN kata sifat?",options:["ceria","baik hati","berlari","pemberani"],answer:2}],
[{q:"Sinonim dari 'pintar' adalah...",options:["bodoh","pandai","malas","nakal"],answer:1},{q:"Antonim dari 'rajin' adalah...",options:["tekun","giat","malas","pintar"],answer:2},{q:"Sinonim dari 'berani' adalah...",options:["penakut","pemberani","pemalu","pendiam"],answer:1},{q:"Antonim dari 'periang' adalah...",options:["gembira","ceria","pendiam","ramah"],answer:2},{q:"Sinonim dari 'cantik' adalah...",options:["jelek","elok","tinggi","kurus"],answer:1}],
[{q:"Rani periang, ____ Rana pendiam.",options:["dan","sedangkan","karena","sehingga"],answer:1},{q:"Budi rajin ____ pandai.",options:["tetapi","sedangkan","dan","karena"],answer:2},{q:"Dia ingin bermain, ____ hujan turun.",options:["dan","sehingga","tetapi","atau"],answer:2},{q:"Dia rajin belajar ____ nilainya selalu bagus.",options:["tetapi","sedangkan","dan","sehingga"],answer:3},{q:"Ibu memasak ____ ayah mencuci mobil.",options:["sehingga","tetapi","dan","karena"],answer:2}],
[{q:"Kata dasar dari 'pemaaf' adalah...",options:["maaf","memaafkan","dimaaf","maafan"],answer:0},{q:"Imbuhan pe- pada 'pembohong' dari kata dasar...",options:["bohong","berbohong","dibohongi","bohongan"],answer:0},{q:"'Pemalu' berasal dari kata dasar...",options:["malu","memalu","malukan","dimalu"],answer:0},{q:"Kata dasar dari 'penyabar' adalah...",options:["sabar","menyabar","disabar","sabaran"],answer:0},{q:"Kata dasar dari 'pendiam' adalah...",options:["diam","berdiam","mendiamkan","diaman"],answer:0}]
],
scramble:[
{word:"RAJIN",hint:"Sifat anak yang tekun belajar"},
{word:"PEMAAF",hint:"Sifat orang yang mudah memaafkan"},
{word:"PERIANG",hint:"Sifat orang yang selalu ceria"},
{word:"PENDIAM",hint:"Sifat orang yang jarang berbicara"},
{word:"PEMBERANI",hint:"Sifat orang yang tidak takut"}
],
truefalse:[
{s:"'Rajin' adalah kata sifat.",a:true},
{s:"'Berlari' adalah kata sifat.",a:false},
{s:"Sinonim dari 'pintar' adalah 'pandai'.",a:true},
{s:"Antonim dari 'rajin' adalah 'tekun'.",a:false},
{s:"Kata hubung 'sedangkan' digunakan untuk hal yang berlawanan.",a:true},
{s:"'Pemaaf' berasal dari kata dasar 'memaafkan'.",a:false},
{s:"Kalimat majemuk setara menggabungkan dua kalimat dengan kata hubung.",a:true},
{s:"'Dan' digunakan untuk menghubungkan hal yang berlawanan.",a:false}
],
matching:[
{pairs:[["pintar","pandai"],["rajin","tekun"],["cantik","elok"],["berani","pemberani"],["gembira","senang"]]},
],
fillword:[
{word:"PEMAAF",hint:"Orang yang mudah memaafkan (pe-___)",reveal:[0,1]},
{word:"PENDIAM",hint:"Orang yang jarang bicara (pe-___)",reveal:[0,1,2]},
{word:"SEDANGKAN",hint:"Kata hubung untuk hal berlawanan",reveal:[0,4]},
{word:"SINONIM",hint:"Persamaan kata",reveal:[0,3]},
{word:"ANTONIM",hint:"Lawan kata",reveal:[0,4]}
],
puzzle:[
{words:["Rani","anak","yang","periang","sedangkan","Rana","pendiam"],correct:"Rani anak yang periang sedangkan Rana pendiam"},
{words:["Dia","rajin","belajar","sehingga","nilainya","bagus"],correct:"Dia rajin belajar sehingga nilainya bagus"},
{words:["Ibu","memasak","dan","ayah","mencuci","mobil"],correct:"Ibu memasak dan ayah mencuci mobil"}
],
materi:["<b>1. Kata Sifat:</b> Kata yang menjelaskan sifat/keadaan. Contoh: rajin, pemaaf, periang.","<b>2. Sinonim & Antonim:</b> Sinonim = persamaan kata (pintar=pandai). Antonim = lawan kata (rajin≠malas).","<b>3. Kalimat Majemuk Setara:</b> Menggabungkan kalimat dengan 'dan', 'tetapi', 'sedangkan', 'sehingga'.","<b>4. Imbuhan Pe-:</b> Membentuk kata sifat (maaf→pemaaf, bohong→pembohong)."],
modul:["Pert 1: Aku Ini Unik! — Puisi Akrostik, Gallery Walk","Pert 2: Membandingkan Karakter — Diagram Venn","Pert 3: Jelajah Kata Sifat — Sinonim, Antonim, Kamus","Pert 4: Merangkai Kalimat — Kalimat majemuk, imbuhan pe-","Pert 5: Sahabatku dalam Tulisan — Menulis draf deskripsi","Pert 6: Karya Final — Menyunting, presentasi"],
refleksi:["Hal apa yang paling menyenangkan yang kamu pelajari di bab ini?","Bagian mana yang menurutmu paling menantang? Mengapa?","Setelah belajar bab ini, apa yang membuatmu bangga dengan sahabatmu?","Keterampilan baru apa yang akan kamu gunakan lagi nanti?"],
media:"KBBI Daring, Lagu 'Kembali ke Sekolah', Diagram Venn, Teka-Teki Silang, Game interaktif."
},
{
name:"Bab 2: Buku Jendela Dunia",
categories:["Fiksi vs Nonfiksi","Unsur Intrinsik","Majas","Kalimat Langsung"],
questions:[
[{q:"Teks yang berisi cerita khayalan disebut...",options:["nonfiksi","fiksi","prosedur","eksposisi"],answer:1},{q:"Manakah ciri teks nonfiksi?",options:["ada tokoh rekaan","berisi fakta dan data","menggunakan dialog","ada alur cerita"],answer:1},{q:"Contoh buku fiksi adalah...",options:["kamus","ensiklopedia","dongeng","buku pelajaran"],answer:2},{q:"Teks nonfiksi bertujuan untuk...",options:["menghibur dengan imajinasi","menyampaikan informasi faktual","membuat tertawa","menceritakan dongeng"],answer:1},{q:"Manakah yang termasuk teks fiksi?",options:["berita koran","resep masakan","novel petualangan","buku biografi"],answer:2}],
[{q:"Pesan moral dalam cerita disebut...",options:["tema","alur","amanat","latar"],answer:2},{q:"Tokoh utama dalam cerita disebut...",options:["antagonis","protagonis","figuran","narator"],answer:1},{q:"Latar menjelaskan tentang...",options:["watak tokoh","tempat dan waktu","pesan moral","jalan cerita"],answer:1},{q:"Rangkaian peristiwa disebut...",options:["tema","latar","alur","amanat"],answer:2},{q:"Ide utama cerita disebut...",options:["alur","amanat","latar","tema"],answer:3}],
[{q:"'Tangisnya membanjiri kebun' termasuk majas...",options:["personifikasi","metafora","hiperbola","simile"],answer:2},{q:"'Angin berbisik lembut' termasuk majas...",options:["hiperbola","personifikasi","metafora","simile"],answer:1},{q:"Majas yang melebih-lebihkan disebut...",options:["personifikasi","metafora","hiperbola","litotes"],answer:2},{q:"Majas yang memberi sifat manusia pada benda...",options:["hiperbola","metafora","personifikasi","simile"],answer:2},{q:"'Dia bintang kelas' termasuk majas...",options:["personifikasi","hiperbola","metafora","simile"],answer:2}],
[{q:"Kalimat langsung ditandai dengan...",options:["tanda seru","tanda petik","tanda tanya","tanda kurung"],answer:1},{q:"Ciri kalimat tidak langsung adalah...",options:["ada tanda petik","ada kata 'bahwa'","ada tanda seru","huruf kapital"],answer:1},{q:"Manakah kalimat langsung?",options:["Ibu berkata bahwa dia pergi","\"Aku akan pergi,\" kata Ibu","Ibu mengatakan dia pergi","Kata ibu dia pergi"],answer:1},{q:"Kata ganti 'aku' berubah menjadi...",options:["kamu","dia/ia","kami","mereka"],answer:1},{q:"Kalimat langsung biasanya berisi...",options:["ucapan tokoh","narasi penulis","deskripsi latar","penjelasan tema"],answer:0}]
],
scramble:[{word:"FIKSI",hint:"Cerita rekaan/khayalan"},{word:"AMANAT",hint:"Pesan moral dalam cerita"},{word:"HIPERBOLA",hint:"Majas yang melebih-lebihkan"},{word:"PROTAGONIS",hint:"Tokoh utama cerita"},{word:"METAFORA",hint:"Majas perumpamaan langsung"}],
truefalse:[{s:"Fiksi adalah cerita berdasarkan fakta.",a:false},{s:"Amanat adalah pesan moral cerita.",a:true},{s:"Latar menjelaskan tempat dan waktu.",a:true},{s:"Personifikasi adalah majas melebih-lebihkan.",a:false},{s:"Kalimat langsung menggunakan tanda petik.",a:true},{s:"Alur adalah rangkaian peristiwa.",a:true}],
matching:[{pairs:[["fiksi","cerita rekaan"],["nonfiksi","berdasarkan fakta"],["amanat","pesan moral"],["alur","rangkaian peristiwa"],["latar","tempat & waktu"]]}],
fillword:[{word:"ANTAGONIS",hint:"Tokoh jahat dalam cerita",reveal:[0,4]},{word:"PERSONIFIKASI",hint:"Majas benda seolah hidup",reveal:[0,1,7]},{word:"HIPERBOLA",hint:"Majas melebih-lebihkan",reveal:[0,5]},{word:"ALUR",hint:"Rangkaian peristiwa cerita",reveal:[0]}],
puzzle:[{words:["Dongeng","termasuk","teks","fiksi","karena","berisi","cerita","rekaan"],correct:"Dongeng termasuk teks fiksi karena berisi cerita rekaan"},{words:["Kalimat","langsung","menggunakan","tanda","petik"],correct:"Kalimat langsung menggunakan tanda petik"}],
materi:["<b>1. Fiksi vs Nonfiksi:</b> Fiksi = cerita rekaan. Nonfiksi = berdasarkan fakta.","<b>2. Unsur Intrinsik:</b> Tema, tokoh, latar, alur, amanat.","<b>3. Majas:</b> Hiperbola, personifikasi, metafora.","<b>4. Kalimat Langsung & Tidak Langsung:</b> Langsung = tanda petik. Tidak langsung = kata 'bahwa'."],
modul:["Pert 1: Fiksi vs Nonfiksi — Membaca dan membandingkan","Pert 2: Unsur Pembangun Cerita — Analisis kelompok","Pert 3: Gaya Bahasa — Majas & kalimat langsung","Pert 4: Proses Pembuatan Buku","Pert 5: Dari Ide Menjadi Kerangka","Pert 6: Menulis dan Berbagi Cerita"],
refleksi:["Dari membaca, menganalisis, dan menulis, mana yang paling kamu sukai?","Apa tantangan terbesar saat menulis ceritamu?","Apakah caramu membaca cerita berubah setelah belajar unsur cerita?","Pesan apa dari cerita yang ingin kamu bagikan?"],
media:"Proyektor untuk sampul buku. Akses perpustakaan digital."
},
{
name:"Bab 3: Ekspresi Diri Melalui Hobi",
categories:["Teks Prosedur","Imbuhan me-/-kan/-lah","Kalimat Perintah","Surat Pribadi"],
questions:[
[{q:"Teks prosedur bertujuan untuk...",options:["menghibur","memberikan petunjuk","menceritakan","menyampaikan pendapat"],answer:1},{q:"Struktur teks prosedur yang benar:",options:["pembuka, isi, penutup","judul, alat/bahan, langkah","tesis, argumen, penegasan","orientasi, komplikasi, resolusi"],answer:1},{q:"Ciri bahasa teks prosedur:",options:["kalimat perintah","kalimat tanya","kalimat seru","kalimat pasif"],answer:0},{q:"Contoh teks prosedur:",options:["dongeng","resep masakan","puisi","cerpen"],answer:1},{q:"Langkah prosedur harus...",options:["acak","berurutan","diulang","singkat saja"],answer:1}],
[{q:"'Membuat' dari kata dasar...",options:["buat","pembuat","dibuat","buatan"],answer:0},{q:"Fungsi imbuhan -kan:",options:["membentuk kata benda","memerintahkan","membentuk sifat","menanyakan"],answer:1},{q:"Fungsi -lah:",options:["memperhalus perintah","menanyakan","menegaskan","membantah"],answer:0},{q:"'Menggunting' berawalan...",options:["me-","meng-","men-","mem-"],answer:1},{q:"me- + lipat =",options:["melipat","memilipat","dilipat","terlipat"],answer:0}],
[{q:"Kalimat perintah diakhiri tanda...",options:["titik","tanya","seru","koma"],answer:2},{q:"Manakah kalimat perintah?",options:["Apakah kamu suka?","Dia bermain","Tutuplah pintu!","Hari cerah"],answer:2},{q:"'Jangan berlari!' termasuk...",options:["ajakan","harapan","larangan","berita"],answer:2},{q:"'Mari bersihkan!' termasuk...",options:["larangan","ajakan","harapan","berita"],answer:1},{q:"Kata 'jangan' menandakan...",options:["perintah biasa","ajakan","larangan","harapan"],answer:2}],
[{q:"Surat pribadi ditujukan kepada...",options:["perusahaan","perorangan/teman","instansi","umum"],answer:1},{q:"Bagian awal surat pribadi:",options:["isi surat","tempat & tanggal","tanda tangan","penutup"],answer:1},{q:"Surat pribadi menggunakan bahasa...",options:["formal","santai/akrab","ilmiah","resmi"],answer:1},{q:"Salam pembuka surat pribadi:",options:["Dengan hormat","Hai, Rina!","Kepada Yth.","Perihal:"],answer:1},{q:"Tanda tangan ditulis di...",options:["awal","tengah","akhir surat","amplop"],answer:2}]
],
scramble:[{word:"PROSEDUR",hint:"Teks berisi petunjuk langkah-langkah"},{word:"MELIPAT",hint:"me- + lipat"},{word:"LARANGAN",hint:"Kalimat yang melarang sesuatu"},{word:"PRIBADI",hint:"Surat untuk orang dekat"}],
truefalse:[{s:"Teks prosedur berisi langkah-langkah berurutan.",a:true},{s:"Imbuhan -lah digunakan untuk bertanya.",a:false},{s:"'Mari' menandakan kalimat larangan.",a:false},{s:"Surat pribadi menggunakan bahasa santai.",a:true},{s:"Kalimat perintah diakhiri tanda titik.",a:false},{s:"Resep masakan adalah contoh teks prosedur.",a:true}],
matching:[{pairs:[["me- + lipat","melipat"],["me- + sapu","menyapu"],["me- + potong","memotong"],["me- + tulis","menulis"],["me- + gambar","menggambar"]]}],
fillword:[{word:"PROSEDUR",hint:"Teks berisi petunjuk",reveal:[0,4]},{word:"MENYAPU",hint:"me- + sapu",reveal:[0,1,2]},{word:"PERINTAH",hint:"Kalimat yang menyuruh",reveal:[0,5]}],
puzzle:[{words:["Siapkan","bahan","lalu","gunting","kertas","dengan","rapi"],correct:"Siapkan bahan lalu gunting kertas dengan rapi"},{words:["Jangan","berlari","di","dalam","kelas"],correct:"Jangan berlari di dalam kelas"}],
materi:["<b>1. Teks Prosedur:</b> Teks petunjuk. Struktur: judul, alat/bahan, langkah.","<b>2. Imbuhan me-/-kan/-lah:</b> me- (aktif), -kan (perintah), -lah (memperhalus).","<b>3. Kalimat Perintah:</b> Perintah, ajakan, larangan, harapan.","<b>4. Surat Pribadi:</b> Untuk orang dekat, bahasa santai."],
modul:["Pert 1: Apa Hobimu? — Membaca teks, imbuhan me-","Pert 2: Berbagi Cerita Hobi — Presentasi","Pert 3: Mengenal Teks Prosedur","Pert 4: Praktik Membuat Origami","Pert 5: Merancang Teks Prosedur Hobiku","Pert 6: Menulis Final dan Pameran Karya"],
refleksi:["Hobi teman mana yang ingin kamu coba?","Apa bagian tersulit saat menulis langkah-langkah?","Apakah kamu bangga bisa mengajarkan hobimu?","Keterampilan apa yang paling berguna?"],
media:"Video tutorial prosedur. Kertas origami untuk praktik."
},
{
name:"Bab 4: Belajar Berwirausaha",
categories:["Ide Pokok","Idiom","Wawancara 5W+1H","Laporan"],
questions:[
[{q:"Ide pokok adalah...",options:["kalimat penjelas","gagasan utama paragraf","judul teks","kata kunci"],answer:1},{q:"Ide pokok terdapat di...",options:["kalimat utama","kalimat penjelas","judul","penutup"],answer:0},{q:"Setiap paragraf memiliki... ide pokok.",options:["dua","tiga","satu","empat"],answer:2},{q:"Paragraf ide pokok di awal disebut...",options:["induktif","deduktif","campuran","naratif"],answer:1},{q:"Cara menemukan ide pokok:",options:["baca judul saja","cari kalimat paling umum","hitung kata","lihat gambar"],answer:1}],
[{q:"'Mental baja' artinya...",options:["terbuat dari baja","kuat dan tangguh","keras kepala","marah"],answer:1},{q:"'Banting tulang' artinya...",options:["patah tulang","bekerja keras","malas","bermain"],answer:1},{q:"'Gulung tikar' artinya...",options:["tidur","bangkrut","pindah","liburan"],answer:1},{q:"'Keras kepala' artinya...",options:["kepalanya sakit","sulit dinasihati","kuat","pintar"],answer:1},{q:"'Buah tangan' artinya...",options:["buah segar","oleh-oleh","tangan kotor","makanan"],answer:1}],
[{q:"5W+1H terdiri dari...",options:["What, Who, When, Where, Why, How","Apa, Siapa, Kapan, Di mana, Mengapa, Bagaimana","Kedua benar","Tidak ada benar"],answer:2},{q:"'Mengapa' menanyakan...",options:["waktu","tempat","sebab/alasan","cara"],answer:2},{q:"'Bagaimana' menanyakan...",options:["waktu","orang","tempat","cara/proses"],answer:3},{q:"Narasumber adalah...",options:["pewawancara","orang yang diwawancarai","reporter","penonton"],answer:1},{q:"Sebelum wawancara harus...",options:["langsung bertanya","siapkan daftar pertanyaan","hafal jawaban","tulis laporan"],answer:1}],
[{q:"Laporan wawancara ditulis dalam bentuk...",options:["puisi","teks narasi","rumus","tabel saja"],answer:1},{q:"Paragraf pembuka laporan berisi...",options:["langkah","perkenalan narasumber","penutup","daftar pustaka"],answer:1},{q:"Laporan yang baik harus...",options:["berisi opini saja","informasi akurat","sangat singkat","bahasa gaul"],answer:1},{q:"Kalimat laporan harus...",options:["acak","runtut dan jelas","sangat panjang","singkatan"],answer:1},{q:"Judul laporan sebaiknya...",options:["sangat panjang","menarik dan informatif","tanpa kapital","tidak ada"],answer:1}]
],
scramble:[{word:"IDIOM",hint:"Ungkapan bermakna kiasan"},{word:"WAWANCARA",hint:"Kegiatan tanya jawab dengan narasumber"},{word:"NARASUMBER",hint:"Orang yang diwawancarai"},{word:"DEDUKTIF",hint:"Paragraf dengan ide pokok di awal"}],
truefalse:[{s:"Ide pokok adalah gagasan utama paragraf.",a:true},{s:"'Banting tulang' artinya patah tulang.",a:false},{s:"Wawancara menggunakan 5W+1H.",a:true},{s:"Idiom bermakna sama dengan kata-katanya.",a:false},{s:"Setiap paragraf memiliki satu ide pokok.",a:true},{s:"'Gulung tikar' artinya tidur.",a:false}],
matching:[{pairs:[["banting tulang","bekerja keras"],["gulung tikar","bangkrut"],["naik daun","terkenal"],["keras kepala","sulit dinasihati"],["buah tangan","oleh-oleh"]]}],
fillword:[{word:"WAWANCARA",hint:"Kegiatan tanya jawab",reveal:[0,4]},{word:"IDIOM",hint:"Ungkapan bermakna kiasan",reveal:[0]},{word:"NARASUMBER",hint:"Orang yang diwawancarai",reveal:[0,4,8]}],
puzzle:[{words:["Nadya","bekerja","keras","sehingga","usahanya","berhasil"],correct:"Nadya bekerja keras sehingga usahanya berhasil"},{words:["Siapa","yang","menjadi","narasumber","wawancara"],correct:"Siapa yang menjadi narasumber wawancara"}],
materi:["<b>1. Ide Pokok:</b> Gagasan utama paragraf dalam kalimat utama.","<b>2. Idiom:</b> Ungkapan bermakna kiasan (banting tulang = bekerja keras).","<b>3. Wawancara:</b> Tanya jawab menggunakan 5W+1H.","<b>4. Laporan Wawancara:</b> Mengubah hasil tanya jawab menjadi narasi."],
modul:["Pert 1: Menemukan Ide Pokok","Pert 2: Makna Idiom — Permainan jodohkan","Pert 3: Merancang Pertanyaan 5W+1H","Pert 4: Simulasi Wawancara","Pert 5: Mengolah Hasil Wawancara","Pert 6: Laporan Final"],
refleksi:["Sifat pengusaha apa yang ingin kamu tiru?","Apa tantangan terbesar melakukan wawancara?","Apakah kamu lebih menghargai pedagang sekarang?","Jika punya usaha, usaha apa yang kamu inginkan?"],
media:"Video wawancara pengusaha sukses. Buku siswa teks biografi."
},
{
name:"Bab 5: Menjadi Warga Dunia",
categories:["Fakta & Opini","Analisis Iklan","Singkatan & Akronim","Riset & Kata Kunci"],
questions:[
[{q:"'Jakarta adalah ibu kota Indonesia' adalah...",options:["opini","fakta","pendapat","himbauan"],answer:1},{q:"Manakah opini?",options:["Indonesia punya 34 provinsi","Menurut saya Indonesia terbaik","Ibu kota Jakarta","Hari ini Senin"],answer:1},{q:"Fakta adalah pernyataan yang...",options:["bisa dibuktikan","berdasarkan perasaan","pendapat pribadi","imajinasi"],answer:0},{q:"'Makanan ini lezat' merupakan...",options:["fakta","opini","pertanyaan","perintah"],answer:1},{q:"Kata yang sering ada dalam opini:",options:["adalah","memiliki","menurut saya","terdapat"],answer:2}],
[{q:"Iklan bertujuan untuk...",options:["menghibur","membujuk membeli","memberitahu berita","mengajar"],answer:1},{q:"Manakah fakta dalam iklan?",options:["Produk paling bagus","Roti harga Rp 5.000","Semua orang suka","Hidup lebih senang"],answer:1},{q:"'Minuman paling segar!' adalah...",options:["fakta","opini iklan","harga","komposisi"],answer:1},{q:"Opini penjual menggunakan kata...",options:["adalah","memiliki","terbaik, paling","terdapat"],answer:2},{q:"Saat melihat iklan harus...",options:["langsung beli","berpikir kritis","percaya semua","menonton saja"],answer:1}],
[{q:"SD merupakan...",options:["akronim","singkatan","kepanjangan","suara"],answer:1},{q:"Akronim dilafalkan sebagai...",options:["huruf per huruf","satu kata utuh","pelan-pelan","tidak dilafalkan"],answer:1},{q:"'SMP' kepanjangannya...",options:["Sekolah Menengah Pendidikan","Sekolah Menengah Pertama","Sistem Menengah Pelajar","Stasiun Menengah"],answer:1},{q:"Singkatan dilafalkan dengan...",options:["satu kata","huruf per huruf","irama","melodi"],answer:1},{q:"Contoh akronim:",options:["Dr.","Puskesmas","Kota","Rp"],answer:1}],
[{q:"Kata kunci adalah...",options:["kata pertama","kata paling penting","kata terakhir","kata benda"],answer:1},{q:"Fungsi kata kunci saat riset:",options:["menambah waktu","menemukan info cepat","membuat lagu","menulis puisi"],answer:1},{q:"Riset kata kunci tepat menghemat...",options:["uang","waktu dan energi","rumah","makanan"],answer:1},{q:"Saat hasil terlalu banyak, kita...",options:["menyerah","tambah kata kunci spesifik","buka semua","tidur"],answer:1},{q:"Informasi baik dari riset:",options:["banyak sekali","akurat dan terpercaya","sumber apa saja","yang pertama"],answer:1}]
],
scramble:[{word:"FAKTA",hint:"Pernyataan yang bisa dibuktikan"},{word:"OPINI",hint:"Pendapat/perasaan seseorang"},{word:"AKRONIM",hint:"Singkatan yang dilafalkan sebagai kata"},{word:"IKLAN",hint:"Media untuk membujuk membeli"}],
truefalse:[{s:"Fakta bisa dibuktikan kebenarannya.",a:true},{s:"Opini selalu berdasarkan data.",a:false},{s:"SD adalah akronim.",a:false},{s:"Puskesmas adalah akronim.",a:true},{s:"Iklan hanya berisi fakta.",a:false},{s:"Kata kunci membantu riset lebih cepat.",a:true}],
matching:[{pairs:[["fakta","bisa dibuktikan"],["opini","pendapat pribadi"],["singkatan","huruf per huruf"],["akronim","satu kata"],["kata kunci","menemukan info"]]}],
fillword:[{word:"SINGKATAN",hint:"Dilafalkan huruf per huruf",reveal:[0,4]},{word:"AKRONIM",hint:"Dilafalkan sebagai satu kata",reveal:[0,3]},{word:"FAKTA",hint:"Bisa dibuktikan kebenarannya",reveal:[0]}],
puzzle:[{words:["Iklan","berisi","fakta","dan","opini","untuk","membujuk"],correct:"Iklan berisi fakta dan opini untuk membujuk"},{words:["Kata","kunci","membantu","menemukan","informasi","cepat"],correct:"Kata kunci membantu menemukan informasi cepat"}],
materi:["<b>1. Fakta & Opini:</b> Fakta = dibuktikan. Opini = pendapat/perasaan.","<b>2. Analisis Iklan:</b> Identifikasi fakta (harga) dan opini (terbaik).","<b>3. Singkatan & Akronim:</b> Singkatan = huruf per huruf. Akronim = satu kata.","<b>4. Riset Kata Kunci:</b> Gunakan kata penting untuk menemukan info cepat."],
modul:["Pert 1: Fakta atau Opini?","Pert 2: Membedah Iklan","Pert 3: Singkatan & Akronim","Pert 4: Riset Cerdas","Pert 5: Menulis Email","Pert 6: Pameran Informasi"],
refleksi:["Informasi digital apa yang ingin kamu pelajari?","Bagaimana membedakan hoaks dari berita akurat?","Apa tantangan riset dengan kata kunci?","Satu aturan etika digital yang akan kamu terapkan?"],
media:"Video iklan TV/media sosial. Komputer untuk praktik riset."
},
{
name:"Bab 6: Cinta Indonesia",
categories:["Huruf Kapital","Brosur & Scanning","Kalimat Perintah","Pengumuman"],
questions:[
[{q:"Huruf kapital digunakan untuk...",options:["semua kata","nama diri dan awal kalimat","kata sifat","kata kerja"],answer:1},{q:"Penulisan yang benar:",options:["museum nasional","Museum Nasional","museum Nasional","MUSEUM nasional"],answer:1},{q:"Nama tempat yang benar:",options:["kota solo","Kota Solo","kota Solo","KOTA SOLO"],answer:1},{q:"Awal kalimat harus huruf...",options:["kecil","kapital","miring","tebal"],answer:1},{q:"Penulisan nama hari yang benar:",options:["hari senin","Hari Senin","hari Senin","HARI senin"],answer:1}],
[{q:"Brosur bertujuan untuk...",options:["menghibur","memberikan info ringkas","bercerita panjang","menulis puisi"],answer:1},{q:"Teknik scanning adalah membaca untuk...",options:["memahami keseluruhan","mencari info spesifik","menghibur diri","menghafal"],answer:1},{q:"Saat scanning, mata...",options:["kata per kata","melompat mencari kata kunci","bawah ke atas","menutup mata"],answer:1},{q:"Brosur biasanya memuat...",options:["cerita panjang","gambar dan info singkat","puisi","novel"],answer:1},{q:"Scanning berguna untuk...",options:["menghemat waktu","menulis cerita","bermain","menghafal"],answer:0}],
[{q:"'Jagalah kebersihan!' termasuk...",options:["tanya","ajakan","perintah","berita"],answer:2},{q:"'Dilarang menyentuh!' termasuk...",options:["ajakan","larangan","harapan","berita"],answer:1},{q:"'Ayo kunjungi museum!' termasuk...",options:["larangan","harapan","ajakan","berita"],answer:2},{q:"'Hendaklah bersikap sopan' termasuk...",options:["larangan","ajakan","harapan","berita"],answer:2},{q:"Manakah kalimat larangan?",options:["Ayo belajar!","Jangan buang sampah!","Mari bermain!","Dia tidur"],answer:1}],
[{q:"Pengumuman bertujuan untuk...",options:["menghibur","memberitahu info resmi","bercerita","berpuisi"],answer:1},{q:"Bagian penting pengumuman:",options:["judul, isi, pembuat","tema, alur, amanat","bahan, langkah","tesis, argumen"],answer:0},{q:"Bahasa pengumuman harus...",options:["puitis","jelas dan singkat","panjang","idiom"],answer:1},{q:"Pengumuman ditujukan kepada...",options:["satu orang","khalayak/banyak orang","hewan","benda"],answer:1},{q:"Pengumuman memuat unsur...",options:["5W+1H","majas","rima","dialog"],answer:0}]
],
scramble:[{word:"KAPITAL",hint:"Huruf besar untuk nama dan awal kalimat"},{word:"SCANNING",hint:"Membaca cepat mencari info spesifik"},{word:"BROSUR",hint:"Media informasi ringkas"},{word:"PENGUMUMAN",hint:"Teks untuk memberitahu banyak orang"}],
truefalse:[{s:"Nama orang ditulis huruf kapital di awal.",a:true},{s:"Scanning adalah membaca kata per kata.",a:false},{s:"Brosur berisi informasi yang panjang.",a:false},{s:"Pengumuman ditujukan kepada banyak orang.",a:true},{s:"'Jangan' menandakan kalimat ajakan.",a:false},{s:"Huruf kapital digunakan di awal kalimat.",a:true}],
matching:[{pairs:[["perintah","Tutuplah pintu!"],["larangan","Jangan berlari!"],["ajakan","Mari bermain!"],["harapan","Hendaklah sopan!"],["pengumuman","info resmi"]]}],
fillword:[{word:"KAPITAL",hint:"Huruf besar",reveal:[0,3]},{word:"PENGUMUMAN",hint:"Teks memberitahu banyak orang",reveal:[0,5]},{word:"BROSUR",hint:"Media informasi ringkas",reveal:[0]}],
puzzle:[{words:["Museum","Nasional","terletak","di","Kota","Jakarta"],correct:"Museum Nasional terletak di Kota Jakarta"},{words:["Jangan","membuang","sampah","sembarangan"],correct:"Jangan membuang sampah sembarangan"}],
materi:["<b>1. Huruf Kapital:</b> Untuk nama diri, tempat, awal kalimat, judul.","<b>2. Brosur & Scanning:</b> Brosur = info ringkas. Scanning = baca cepat.","<b>3. Kalimat Perintah:</b> Ajakan, harapan, larangan.","<b>4. Pengumuman:</b> Info resmi. Struktur: judul, isi, pembuat."],
modul:["Pert 1: Aturan Bahasa — Huruf kapital","Pert 2: Perintah, Ajakan, Harapan","Pert 3: Membaca Brosur — Scanning","Pert 4: Membuat Pengumuman","Pert 5: Proyek Museum Mini","Pert 6: Pameran dan Pengumuman"],
refleksi:["Tempat bersejarah apa yang ingin kamu kunjungi?","Mengapa perlu belajar sejarah bangsa?","Keterampilan apa paling berguna dari bab ini?","Jika bisa buat aturan museum, apa itu?"],
media:"Google Maps untuk tur virtual museum. Proyektor untuk brosur."
},
{
name:"Bab 7: Sayangi Bumi",
categories:["Sebab-Akibat","Ringkasan","Imbuhan pe-an","Teks Eksposisi"],
questions:[
[{q:"Kata penghubung sebab-akibat:",options:["dan, atau","karena, sehingga, akibatnya","tetapi, sedangkan","yang, ini"],answer:1},{q:"'Hutan gundul ____ sering banjir'",options:["dan","tetapi","sehingga","sedangkan"],answer:2},{q:"'Banjir terjadi ____ sampah menyumbat.'",options:["sehingga","dan","karena","tetapi"],answer:2},{q:"'Penebangan liar menyebabkan...'",options:["udara bersih","hutan gundul","hujan deras","bumi dingin"],answer:1},{q:"Diagram sebab-akibat membantu...",options:["menggambar","memahami hubungan peristiwa","bermain","bernyanyi"],answer:1}],
[{q:"Ringkasan adalah...",options:["menyalin seluruh teks","menyajikan inti secara singkat","menambah info","mengubah jadi puisi"],answer:1},{q:"Langkah pertama meringkas:",options:["menulis langsung","membaca dan temukan ide pokok","menghapus","menghias"],answer:1},{q:"Ringkasan yang baik harus...",options:["lebih panjang","singkat tapi mencakup ide pokok","sama persis","acak"],answer:1},{q:"Ringkasan tidak boleh mengubah...",options:["panjang kalimat","makna/ide pokok asli","gaya bahasa","format"],answer:1},{q:"Paragraf ide pokok di akhir = paragraf...",options:["deduktif","induktif","campuran","naratif"],answer:1}],
[{q:"'Penghijauan' dari kata dasar...",options:["hijau","menghijau","kehijauan","penghijau"],answer:0},{q:"Imbuhan pe-an pada 'pengelolaan' berarti...",options:["tempat","proses mengelola","orang","alat"],answer:1},{q:"Fungsi pe-an: membentuk kata...",options:["kerja","sifat","benda (proses/hal)","hubung"],answer:2},{q:"'Pencemaran' dari kata dasar...",options:["cemar","mencemari","tercemar","dicemari"],answer:0},{q:"'Pemanasan' dari kata dasar...",options:["panas","memanas","kepanasan","dipanasi"],answer:0}],
[{q:"Teks eksposisi bertujuan...",options:["menghibur","meyakinkan dengan argumen","menceritakan","memberi petunjuk"],answer:1},{q:"Struktur teks eksposisi:",options:["orientasi, komplikasi, resolusi","tesis, argumentasi, penegasan ulang","judul, bahan, langkah","pembuka, isi, penutup"],answer:1},{q:"Tesis adalah...",options:["argumen pendukung","pernyataan pendapat awal","kesimpulan","data"],answer:1},{q:"Argumen kuat didukung oleh...",options:["opini saja","fakta dan data","dongeng","mimpi"],answer:1},{q:"'Oleh karena itu, kurangi plastik.' Bagian...",options:["tesis","argumentasi","penegasan ulang","orientasi"],answer:2}]
],
scramble:[{word:"PENGHIJAUAN",hint:"Proses menanam pohon (pe-an + hijau)"},{word:"EKSPOSISI",hint:"Teks untuk meyakinkan pembaca"},{word:"PENCEMARAN",hint:"Proses terjadinya cemar"},{word:"RINGKASAN",hint:"Inti teks secara singkat"}],
truefalse:[{s:"'Karena' menunjukkan hubungan sebab-akibat.",a:true},{s:"Ringkasan harus lebih panjang dari asli.",a:false},{s:"Imbuhan pe-an membentuk kata benda.",a:true},{s:"Tesis adalah kesimpulan eksposisi.",a:false},{s:"'Sehingga' menunjukkan akibat.",a:true},{s:"'Penghijauan' dari kata 'menghijau'.",a:false}],
matching:[{pairs:[["sebab","karena"],["akibat","sehingga"],["pe-an + hijau","penghijauan"],["pe-an + cemar","pencemaran"],["tesis","pendapat awal"]]}],
fillword:[{word:"PENGHIJAUAN",hint:"pe-an + hijau",reveal:[0,1,2,8]},{word:"EKSPOSISI",hint:"Teks meyakinkan pembaca",reveal:[0,4]},{word:"SEHINGGA",hint:"Kata hubung akibat",reveal:[0,4]}],
puzzle:[{words:["Hutan","gundul","sehingga","sering","terjadi","banjir"],correct:"Hutan gundul sehingga sering terjadi banjir"},{words:["Oleh","karena","itu","mari","kurangi","plastik"],correct:"Oleh karena itu mari kurangi plastik"}],
materi:["<b>1. Sebab-Akibat:</b> Kata hubung: karena, sehingga, akibatnya.","<b>2. Ringkasan:</b> Menyajikan inti teks secara singkat.","<b>3. Imbuhan pe-an:</b> Membentuk kata benda bermakna proses.","<b>4. Teks Eksposisi:</b> Tesis, argumentasi, penegasan ulang."],
modul:["Pert 1: Permainan Sebab-Akibat","Pert 2: Meringkas Informasi","Pert 3: Ide Pokok & Pengelolaan Sampah","Pert 4: Teks Eksposisi & Imbuhan pe-an","Pert 5: Kampanye Hari Bumi","Pert 6: Menulis Eksposisi Final"],
refleksi:["Isu lingkungan apa yang membuatmu khawatir?","Cara paling ampuh mengajak teman peduli lingkungan?","Apa bagian tersulit menulis eksposisi?","Satu hal yang akan kamu ubah untuk bumi?"],
media:"Video dokumenter polusi. Diagram sebab-akibat. Poster Hari Bumi."
}
];

const chapNames=chapters.map(c=>c.name);
let currentChapter=0,currentGameType=0,currentQ=0,score=0,total=0,answered=false,shuffledItems=[];
let currentMode=0;
const modeInfos=["Jawab soal sendiri dan kumpulkan skor tertinggi!","Bergantian menjawab dengan pasanganmu. Siapa yang lebih banyak benar?","Diskusikan jawaban bersama kelompokmu sebelum memilih!"];
const gameTypeNames=["Quiz","Acak Kata","Benar/Salah","Berpasangan","Bermain Kata","Puzzle"];

function shuffle(a){const b=[...a];for(let i=b.length-1;i>0;i--){const j=Math.floor(Math.random()*(i+1));[b[i],b[j]]=[b[j],b[i]]}return b}

function switchChapter(idx){
currentChapter=idx;
document.querySelectorAll('.chap-btn').forEach((b,i)=>{b.className=`chap-btn px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900 ${i===idx?'chap-active':'bg-white text-amber-900'}`});
document.getElementById('chapter-title').textContent=chapNames[idx];
startGame();
updateInfoSections();
}

function switchMode(idx){
currentMode=idx;
document.querySelectorAll('.mode-btn').forEach((b,i)=>{b.className=`mode-btn px-4 py-2 rounded-full text-sm font-semibold border-2 border-amber-600 ${i===idx?'mode-active':'bg-white text-amber-800'}`});
document.getElementById('mode-info').textContent=modeInfos[idx];
}

function switchGameType(idx){
currentGameType=idx;
document.querySelectorAll('.game-type-btn').forEach((b,i)=>{b.className=`game-type-btn px-3 py-1.5 rounded-full text-xs font-bold border-2 border-amber-900 ${i===idx?'game-type-active':'bg-white text-amber-900'}`});
startGame();
}

function startGame(){
currentQ=0;score=0;total=0;answered=false;
updateScore();
const ch=chapters[currentChapter];
if(currentGameType===0){
const allQ=ch.questions.flat();
shuffledItems=shuffle(allQ).slice(0,10);
renderQuiz();
}else if(currentGameType===1){
shuffledItems=shuffle(ch.scramble||[]);
renderScramble();
}else if(currentGameType===2){
shuffledItems=shuffle(ch.truefalse||[]);
renderTrueFalse();
}else if(currentGameType===3){
renderMatching();
}else if(currentGameType===4){
shuffledItems=shuffle(ch.fillword||[]);
renderFillWord();
}else if(currentGameType===5){
shuffledItems=shuffle(ch.puzzle||[]);
renderPuzzle();
}
}

// QUIZ
function renderQuiz(){
const area=document.getElementById('game-area');
if(currentQ>=shuffledItems.length){showComplete();return}
const q=shuffledItems[currentQ];answered=false;
document.getElementById('feedback').textContent='';
document.getElementById('next-btn').classList.add('hidden');
area.innerHTML=`<div class="fade-in"><p class="text-sm text-gray-500 mb-1">Soal ${currentQ+1}/${shuffledItems.length}</p><h2 class="text-xl font-bold mb-5" style="font-family:Fraunces,serif">${q.q}</h2><div class="grid grid-cols-1 sm:grid-cols-2 gap-3">${q.options.map((o,i)=>`<button class="option-btn border-2 border-gray-200 rounded-xl px-4 py-3 text-left font-medium hover:border-amber-400" onclick="checkQuiz(${i})">${o}</button>`).join('')}</div></div>`;
}
function checkQuiz(idx){
if(answered)return;answered=true;total++;
const q=shuffledItems[currentQ];
const btns=document.querySelectorAll('.option-btn');
btns.forEach(b=>b.disabled=true);
btns[q.answer].classList.add('correct');
const fb=document.getElementById('feedback');
if(idx===q.answer){score++;fb.innerHTML='<span class="text-emerald-600">✓ Benar!</span>'}
else{btns[idx].classList.add('incorrect');fb.innerHTML='<span class="text-red-500">✗ Belum tepat.</span>'}
updateScore();document.getElementById('next-btn').classList.remove('hidden');
}

// SCRAMBLE (Acak Kata)
let scrambleAnswer=[];
function renderScramble(){
const area=document.getElementById('game-area');
if(currentQ>=shuffledItems.length){showComplete();return}
const item=shuffledItems[currentQ];answered=false;scrambleAnswer=[];
document.getElementById('feedback').textContent='';
document.getElementById('next-btn').classList.add('hidden');
const letters=shuffle(item.word.split(''));
area.innerHTML=`<div class="fade-in"><p class="text-sm text-gray-500 mb-1">Soal ${currentQ+1}/${shuffledItems.length}</p><p class="text-amber-700 italic mb-2">💡 ${item.hint}</p><div id="scramble-result" class="flex flex-wrap gap-1 min-h-[3rem] bg-gray-50 rounded-xl p-3 mb-4 items-center justify-center"></div><div id="scramble-letters" class="flex flex-wrap gap-2 justify-center">${letters.map((l,i)=>`<button class="letter-btn bg-amber-100 hover:bg-amber-200 text-amber-900 font-bold text-lg w-10 h-10 rounded-lg shadow" onclick="pickLetter(this,'${l}',${i})">${l}</button>`).join('')}</div><div class="text-center mt-3"><button class="text-sm text-gray-500 underline" onclick="resetScramble()">🔄 Reset</button></div></div>`;
}
function pickLetter(btn,letter){
if(answered)return;
btn.classList.add('used');
scrambleAnswer.push(letter);
const res=document.getElementById('scramble-result');
res.innerHTML=scrambleAnswer.map(l=>`<span class="bg-white border-2 border-amber-400 rounded-lg w-9 h-9 flex items-center justify-center font-bold text-lg">${l}</span>`).join('');
const item=shuffledItems[currentQ];
if(scrambleAnswer.length===item.word.length){
answered=true;total++;
const fb=document.getElementById('feedback');
if(scrambleAnswer.join('')===item.word){score++;fb.innerHTML='<span class="text-emerald-600">✓ Benar! Jawabannya: '+item.word+'</span>'}
else{fb.innerHTML='<span class="text-red-500">✗ Jawaban yang benar: '+item.word+'</span>'}
updateScore();document.getElementById('next-btn').classList.remove('hidden');
}
}
function resetScramble(){if(!answered){scrambleAnswer=[];renderScramble()}}

// TRUE/FALSE (Benar/Salah)
function renderTrueFalse(){
const area=document.getElementById('game-area');
if(currentQ>=shuffledItems.length){showComplete();return}
const item=shuffledItems[currentQ];answered=false;
document.getElementById('feedback').textContent='';
document.getElementById('next-btn').classList.add('hidden');
area.innerHTML=`<div class="fade-in"><p class="text-sm text-gray-500 mb-1">Soal ${currentQ+1}/${shuffledItems.length}</p><h2 class="text-xl font-bold mb-6 text-center" style="font-family:Fraunces,serif">"${item.s}"</h2><div class="flex gap-4 justify-center"><button class="option-btn border-2 border-emerald-300 bg-emerald-50 rounded-xl px-8 py-4 font-bold text-lg hover:border-emerald-500" onclick="checkTF(true)">✅ Benar</button><button class="option-btn border-2 border-red-300 bg-red-50 rounded-xl px-8 py-4 font-bold text-lg hover:border-red-500" onclick="checkTF(false)">❌ Salah</button></div></div>`;
}
function checkTF(val){
if(answered)return;answered=true;total++;
const item=shuffledItems[currentQ];
const fb=document.getElementById('feedback');
const btns=document.querySelectorAll('.option-btn');
btns.forEach(b=>b.disabled=true);
if(val===item.a){score++;fb.innerHTML='<span class="text-emerald-600">✓ Benar!</span>';btns[val?0:1].classList.add('correct')}
else{fb.innerHTML='<span class="text-red-500">✗ Jawaban: '+(item.a?'Benar':'Salah')+'</span>';btns[val?0:1].classList.add('incorrect');btns[val?1:0].classList.add('correct')}
updateScore();document.getElementById('next-btn').classList.remove('hidden');
}

// MATCHING (Berpasangan)
let matchState={selected:null,matched:0,pairs:[]};
function renderMatching(){
const ch=chapters[currentChapter];
const data=ch.matching&&ch.matching[0]?ch.matching[0]:{pairs:[]};
matchState={selected:null,matched:0,pairs:data.pairs};
answered=false;score=0;total=0;
document.getElementById('feedback').textContent='';
document.getElementById('next-btn').classList.add('hidden');
const left=shuffle(data.pairs.map((p,i)=>({text:p[0],idx:i,side:'l'})));
const right=shuffle(data.pairs.map((p,i)=>({text:p[1],idx:i,side:'r'})));
const area=document.getElementById('game-area');
area.innerHTML=`<div class="fade-in"><p class="text-sm text-gray-500 mb-3 text-center">Cocokkan pasangan yang benar!</p><div class="grid grid-cols-2 gap-4"><div class="space-y-2">${left.map(l=>`<button class="match-card w-full border-2 border-amber-200 rounded-xl px-4 py-3 text-left font-medium bg-amber-50" data-side="l" data-idx="${l.idx}" onclick="pickMatch(this)">${l.text}</button>`).join('')}</div><div class="space-y-2">${right.map(r=>`<button class="match-card w-full border-2 border-blue-200 rounded-xl px-4 py-3 text-left font-medium bg-blue-50" data-side="r" data-idx="${r.idx}" onclick="pickMatch(this)">${r.text}</button>`).join('')}</div></div></div>`;
updateScore();
}
function pickMatch(btn){
if(btn.classList.contains('matched'))return;
const side=btn.dataset.side,idx=parseInt(btn.dataset.idx);
if(matchState.selected===null){
matchState.selected={el:btn,side,idx};
btn.classList.add('selected');
}else{
if(matchState.selected.side===side){
matchState.selected.el.classList.remove('selected');
matchState.selected={el:btn,side,idx};
btn.classList.add('selected');
}else{
total++;
if(matchState.selected.idx===idx){
score++;
matchState.selected.el.classList.remove('selected');
matchState.selected.el.classList.add('matched');
btn.classList.add('matched');
matchState.matched++;
document.getElementById('feedback').innerHTML='<span class="text-emerald-600">✓ Cocok!</span>';
if(matchState.matched===matchState.pairs.length){
setTimeout(()=>{document.getElementById('feedback').innerHTML='<span class="text-emerald-600">🎉 Semua cocok! Skor: '+score+'/'+total+'</span>'},300);
}
}else{
matchState.selected.el.classList.remove('selected');
matchState.selected.el.classList.add('incorrect');
btn.classList.add('incorrect');
document.getElementById('feedback').innerHTML='<span class="text-red-500">✗ Tidak cocok!</span>';
setTimeout(()=>{matchState.selected.el.classList.remove('incorrect');btn.classList.remove('incorrect')},600);
}
matchState.selected=null;
updateScore();
}
}
}

// FILL WORD (Bermain Kata)
let fillAnswer=[];
function renderFillWord(){
const area=document.getElementById('game-area');
if(currentQ>=shuffledItems.length){showComplete();return}
const item=shuffledItems[currentQ];answered=false;fillAnswer=[];
document.getElementById('feedback').textContent='';
document.getElementById('next-btn').classList.add('hidden');
const display=item.word.split('').map((ch,i)=>{
if(item.reveal.includes(i))return`<span class="bg-amber-200 border-2 border-amber-400 rounded w-8 h-10 flex items-center justify-center font-bold text-lg">${ch}</span>`;
return`<span class="bg-gray-100 border-2 border-gray-300 rounded w-8 h-10 flex items-center justify-center font-bold text-lg fill-slot" data-pos="${i}">_</span>`;
});
const hidden=item.word.split('').filter((_,i)=>!item.reveal.includes(i));
const letters=shuffle(hidden);
area.innerHTML=`<div class="fade-in"><p class="text-sm text-gray-500 mb-1">Soal ${currentQ+1}/${shuffledItems.length}</p><p class="text-amber-700 italic mb-3">💡 ${item.hint}</p><div class="flex flex-wrap gap-1 justify-center mb-4">${display.join('')}</div><div id="fill-letters" class="flex flex-wrap gap-2 justify-center mt-4">${letters.map((l,i)=>`<button class="letter-btn bg-blue-100 hover:bg-blue-200 text-blue-900 font-bold text-lg w-9 h-9 rounded-lg shadow" onclick="pickFill(this,'${l}')">${l}</button>`).join('')}</div><div class="text-center mt-3"><button class="text-sm text-gray-500 underline" onclick="resetFill()">🔄 Reset</button></div></div>`;
}
function pickFill(btn,letter){
if(answered)return;
btn.classList.add('used');
fillAnswer.push(letter);
const item=shuffledItems[currentQ];
const slots=document.querySelectorAll('.fill-slot');
const hiddenCount=item.word.length-item.reveal.length;
if(fillAnswer.length<=slots.length){slots[fillAnswer.length-1].textContent=letter}
if(fillAnswer.length===hiddenCount){
answered=true;total++;
const hidden=item.word.split('').filter((_,i)=>!item.reveal.includes(i));
const fb=document.getElementById('feedback');
if(fillAnswer.join('')===hidden.join('')){score++;fb.innerHTML='<span class="text-emerald-600">✓ Benar! '+item.word+'</span>'}
else{fb.innerHTML='<span class="text-red-500">✗ Jawaban: '+item.word+'</span>'}
updateScore();document.getElementById('next-btn').classList.remove('hidden');
}
}
function resetFill(){if(!answered){fillAnswer=[];renderFillWord()}}

// PUZZLE (Susun Kalimat)
let puzzleAnswer=[];
function renderPuzzle(){
const area=document.getElementById('game-area');
if(currentQ>=shuffledItems.length){showComplete();return}
const item=shuffledItems[currentQ];answered=false;puzzleAnswer=[];
document.getElementById('feedback').textContent='';
document.getElementById('next-btn').classList.add('hidden');
const words=shuffle([...item.words]);
area.innerHTML=`<div class="fade-in"><p class="text-sm text-gray-500 mb-1">Soal ${currentQ+1}/${shuffledItems.length}</p><p class="text-amber-700 italic mb-3">🧩 Susun kata menjadi kalimat yang benar!</p><div id="puzzle-result" class="flex flex-wrap gap-2 min-h-[3rem] bg-gray-50 rounded-xl p-3 mb-4 items-center"></div><div id="puzzle-words" class="flex flex-wrap gap-2 justify-center">${words.map((w,i)=>`<button class="puzzle-word bg-purple-100 hover:bg-purple-200 text-purple-900 font-semibold px-3 py-2 rounded-lg shadow text-sm" onclick="pickPuzzle(this,'${w.replace(/'/g,"\\'")}')">${w}</button>`).join('')}</div><div class="flex gap-3 justify-center mt-3"><button class="text-sm text-gray-500 underline" onclick="resetPuzzle()">🔄 Reset</button><button class="text-sm bg-amber-500 text-white px-4 py-1 rounded-full font-semibold" onclick="checkPuzzle()">Cek Jawaban</button></div></div>`;
}
function pickPuzzle(btn,word){
if(answered)return;
btn.classList.add('placed');
puzzleAnswer.push(word);
const res=document.getElementById('puzzle-result');
res.innerHTML=puzzleAnswer.map(w=>`<span class="bg-white border border-purple-300 rounded-lg px-2 py-1 text-sm font-medium">${w}</span>`).join('');
}
function checkPuzzle(){
if(answered)return;
const item=shuffledItems[currentQ];
answered=true;total++;
const fb=document.getElementById('feedback');
if(puzzleAnswer.join(' ')===item.correct){score++;fb.innerHTML='<span class="text-emerald-600">✓ Benar!</span>'}
else{fb.innerHTML='<span class="text-red-500">✗ Jawaban: '+item.correct+'</span>'}
updateScore();document.getElementById('next-btn').classList.remove('hidden');
}
function resetPuzzle(){if(!answered){puzzleAnswer=[];renderPuzzle()}}

function showComplete(){
const area=document.getElementById('game-area');
area.innerHTML=`<div class="text-center fade-in"><h2 class="text-2xl font-bold mb-2" style="font-family:Fraunces,serif">🎉 Selesai!</h2><p class="text-lg">Skor: <strong>${score}/${total}</strong></p><p class="text-sm text-gray-500 mt-1">${score>=total*.8?'Luar biasa! 🌟':score>=total*.5?'Bagus! Terus berlatih! 💪':'Jangan menyerah! 🔄'}</p><button class="mt-4 px-5 py-2 bg-amber-500 text-white rounded-full font-semibold hover:bg-amber-600 transition" onclick="startGame()">Main Lagi 🔄</button></div>`;
document.getElementById('feedback').textContent='';
document.getElementById('next-btn').classList.add('hidden');
}

function nextQuestion(){
currentQ++;
if(currentGameType===0)renderQuiz();
else if(currentGameType===1)renderScramble();
else if(currentGameType===2)renderTrueFalse();
else if(currentGameType===4)renderFillWord();
else if(currentGameType===5)renderPuzzle();
}

function updateScore(){document.getElementById('score-display').textContent=`Skor: ${score} / ${total}`}

function updateInfoSections(){
const ch=chapters[currentChapter];
document.getElementById('materi-content').innerHTML=(ch.materi||[]).map((m,i)=>{
const colors=['amber','emerald','blue','purple','rose'];
return`<div class="border-l-4 border-${colors[i%5]}-400 pl-4 py-2"><p class="text-gray-700 text-sm">${m}</p></div>`;
}).join('');
document.getElementById('modul-sub-dynamic').textContent=`${chapNames[currentChapter]} | 18 JP (6 Pertemuan)`;
document.getElementById('modul-items').innerHTML=(ch.modul||[]).map(m=>`<div class="bg-gray-50 rounded-lg p-3"><p class="text-sm text-gray-700">${m}</p></div>`).join('');
document.getElementById('refleksi-items').innerHTML=(ch.refleksi||[]).map((r,i)=>{
const bgs=['bg-amber-50','bg-emerald-50','bg-blue-50','bg-purple-50'];
return`<div class="${bgs[i%4]} rounded-lg p-4"><p class="font-medium text-sm">${i+1}. ${r}</p></div>`;
}).join('');
document.getElementById('media-info-dynamic').textContent=ch.media||'';
}

const sections=['game','materi','media','modul','refleksi'];
const tabIds=['tab-game','tab-materi','tab-media','tab-modul','tab-refleksi'];
function switchSection(name){
sections.forEach(s=>document.getElementById('section-'+s).classList.toggle('hidden',s!==name));
tabIds.forEach((id,i)=>{
const btn=document.querySelector(`[data-template-id="${id}"]`);
btn.classList.toggle('tab-active',sections[i]===name);
if(sections[i]!==name){btn.classList.add('bg-white','text-gray-700');btn.classList.remove('tab-active')}
else{btn.classList.remove('bg-white','text-gray-700')}
});
}

startGame();
updateInfoSections();
lucide.createIcons();
</script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'a0f983a47256a5b9',t:'MTc4MjExMzA3Ni4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script>
</body></html>
