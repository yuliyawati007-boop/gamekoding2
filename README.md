# gamekoding2
Edukasi
<!doctype html>
<html lang="id">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Berpikir Komputasional - Media Pembelajaran Interaktif</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdn.jsdelivr.net/npm/lucide@0.263.0/dist/umd/lucide.min.js"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <script src="/_sdk/data_sdk.js"></script>
  <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html, body {
            height: 100%;
            width: 100%;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow: hidden;
        }

        #app-wrapper {
            width: 100%;
            height: 100%;
            overflow: auto;
        }

        @keyframes slideInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes scaleIn {
            from {
                opacity: 0;
                transform: scale(0.8);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.05); }
        }

        .animate-slide-in {
            animation: slideInDown 0.8s ease-out;
        }

        .animate-fade-in {
            animation: fadeIn 0.8s ease-out;
        }

        .animate-scale-in {
            animation: scaleIn 0.6s ease-out;
        }

        .animate-pulse-btn {
            animation: pulse 0.8s infinite;
        }

        button {
            transition: all 0.3s ease;
        }

        button:hover {
            transform: translateY(-2px);
        }

        button:active {
            transform: translateY(0);
        }

        .tab-button.active {
            border-bottom: 3px solid #1e40af;
            font-weight: bold;
            color: #1e40af;
        }

        .drag-item {
            cursor: grab;
            padding: 10px 15px;
            background: #dbeafe;
            border: 2px solid #3b82f6;
            border-radius: 6px;
            margin: 5px;
            user-select: none;
        }

        .drag-item.dragging {
            opacity: 0.5;
            cursor: grabbing;
        }

        .drop-zone {
            min-height: 50px;
            border: 2px dashed #93c5fd;
            border-radius: 6px;
            padding: 10px;
            margin: 10px 0;
            background: #f0f9ff;
        }

        .drop-zone.dragover {
            background: #dbeafe;
            border-color: #3b82f6;
        }

        .certificate {
            background: linear-gradient(135deg, #1e40af 0%, #1e3a8a 100%);
            color: white;
            padding: 40px;
            border-radius: 15px;
            text-align: center;
            box-shadow: 0 10px 40px rgba(0,0,0,0.3);
        }

        .certificate-border {
            border: 4px solid #fbbf24;
            padding: 30px;
            border-radius: 10px;
        }

        .progress-bar {
            height: 8px;
            background: #e0e7ff;
            border-radius: 10px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, #3b82f6 0%, #1e40af 100%);
            transition: width 0.3s ease;
        }

        .success-animation {
            animation: scaleIn 0.6s ease-out;
        }
    </style>
  <style>body { box-sizing: border-box; }</style>
  <script src="https://cdn.tailwindcss.com/3.4.17" type="text/javascript"></script>
 </head>
 <body class="bg-gradient-to-br from-blue-50 to-indigo-100" style="background-image: url('https://i.imgur.com/WChOjFr.jpeg'); background-size: cover; background-attachment: fixed;">
  <div id="app-wrapper" class="w-full h-full overflow-auto">
   <!-- SPLASH SCREEN -->
   <div id="splash-screen" class="fixed inset-0 bg-gradient-to-br from-blue-600 to-blue-800 flex flex-col items-center justify-center z-50" style="background-image: url('https://i.imgur.com/WChOjFr.jpeg'); background-size: cover; background-blend-mode: overlay;">
    <div class="text-center animate-fade-in">
     <div class="text-6xl font-bold text-white mb-6 animate-slide-in">
      💻
     </div>
     <h1 class="text-5xl font-bold text-white mb-4 animate-slide-in">Berpikir Komputasional</h1>
     <p class="text-xl text-blue-100 mb-12 animate-fade-in">Media Pembelajaran Interaktif</p><button onclick="startApp()" class="bg-yellow-400 hover:bg-yellow-300 text-blue-900 font-bold py-4 px-12 rounded-lg text-lg animate-scale-in animate-pulse-btn"> 🚀 MULAI </button>
     <p class="text-blue-200 text-xs mt-8">Kelas X | Informatika</p>
    </div>
   </div><!-- HOME BUTTON (Permanen) --> <button id="home-btn" onclick="goHome()" class="fixed top-4 left-4 bg-blue-600 hover:bg-blue-700 text-white p-3 rounded-full z-40 hidden shadow-lg" title="Kembali ke Beranda"> <i data-lucide="home" style="width: 24px; height: 24px;"></i> </button> <!-- MAIN MENU -->
   <div id="main-menu" class="hidden w-full h-full p-8 overflow-auto">
    <div class="max-w-7xl mx-auto">
     <!-- Header -->
     <div class="text-center mb-12">
      <h1 class="text-4xl font-bold text-blue-900 mb-2">Selamat Datang</h1>
      <p class="text-blue-600">Pilih menu pembelajaran di bawah ini</p>
     </div><!-- Menu Cards -->
     <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-12">
      <div onclick="goToSection('beranda')" class="bg-white p-8 rounded-lg shadow-lg hover:shadow-2xl cursor-pointer border-l-4 border-blue-600">
       <div class="text-4xl mb-4">
        🏠
       </div>
       <h2 class="text-2xl font-bold text-blue-900 mb-2">BERANDA</h2>
       <p class="text-gray-600">Informasi tentang pembelajaran berpikir komputasional</p>
      </div>
      <div onclick="goToSection('materi')" class="bg-white p-8 rounded-lg shadow-lg hover:shadow-2xl cursor-pointer border-l-4 border-green-600">
       <div class="text-4xl mb-4">
        📚
       </div>
       <h2 class="text-2xl font-bold text-blue-900 mb-2">MATERI</h2>
       <p class="text-gray-600">Pelajari konsep-konsep berpikir komputasional</p>
      </div>
      <div onclick="goToSection('simulasi')" class="bg-white p-8 rounded-lg shadow-lg hover:shadow-2xl cursor-pointer border-l-4 border-purple-600">
       <div class="text-4xl mb-4">
        🧪
       </div>
       <h2 class="text-2xl font-bold text-blue-900 mb-2">SIMULASI</h2>
       <p class="text-gray-600">Uji pemahaman dengan 10 soal interaktif</p>
      </div>
      <div onclick="goToSection('kuis')" class="bg-white p-8 rounded-lg shadow-lg hover:shadow-2xl cursor-pointer border-l-4 border-orange-600">
       <div class="text-4xl mb-4">
        🎮
       </div>
       <h2 class="text-2xl font-bold text-blue-900 mb-2">KUIS</h2>
       <p class="text-gray-600">4 permainan edukatif dengan level progresif</p>
      </div>
     </div><!-- Settings Section -->
     <div class="bg-white p-6 rounded-lg shadow-lg mb-8">
      <div class="flex items-center justify-between mb-6">
       <h3 class="text-xl font-bold text-blue-900 flex items-center gap-2"><i data-lucide="settings" style="width: 24px; height: 24px;"></i> Pengaturan</h3>
      </div>
      <div class="space-y-4">
       <div class="flex items-center justify-between">
        <label class="text-gray-700 font-semibold">🔊 Musik Latar</label> <button id="music-toggle" onclick="toggleMusic()" class="bg-blue-600 hover:bg-blue-700 text-white px-6 py-2 rounded-lg font-semibold"> ON </button>
       </div>
       <div class="flex items-center gap-4">
        <label class="text-gray-700 font-semibold w-24">🔉 Volume</label> <input type="range" id="volume-slider" min="0" max="100" value="50" class="flex-1 cursor-pointer" oninput="setVolume(this.value)"> <span id="volume-display" class="text-gray-700 font-semibold w-12 text-right">50%</span>
       </div>
      </div>
     </div><!-- Student Name Input -->
     <div class="bg-gradient-to-r from-blue-600 to-blue-700 p-8 rounded-lg text-white text-center">
      <p class="text-lg mb-4">Masukkan nama Anda untuk memulai pembelajaran:</p><input type="text" id="student-name" placeholder="Nama Anda" class="w-full max-w-md px-4 py-3 rounded-lg text-blue-900 font-semibold text-center mb-4" maxlength="50"> <button onclick="saveStudentName()" class="bg-yellow-400 hover:bg-yellow-300 text-blue-900 font-bold py-2 px-8 rounded-lg"> ✓ Simpan Nama </button>
     </div>
    </div>
   </div><!-- BERANDA SECTION -->
   <div id="beranda-section" class="hidden w-full h-full p-8 overflow-auto">
    <div class="max-w-4xl mx-auto">
     <h1 class="text-4xl font-bold text-blue-900 mb-6">📖 Beranda - Berpikir Komputasional</h1>
     <div class="bg-white p-8 rounded-lg shadow-lg mb-6">
      <div class="prose max-w-none">
       <h2 class="text-2xl font-bold text-blue-800 mb-4">Selamat Datang di Media Pembelajaran Interaktif!</h2>
       <div class="space-y-6">
        <div class="bg-blue-50 p-6 rounded-lg border-l-4 border-blue-600">
         <h3 class="text-xl font-bold text-blue-900 mb-2">🎯 Tujuan Pembelajaran</h3>
         <ul class="list-disc list-inside text-gray-700 space-y-2">
          <li>Memahami konsep dasar berpikir komputasional dalam menyelesaikan masalah sehari-hari</li>
          <li>Mengidentifikasi masalah dan memecahnya menjadi bagian-bagian kecil (dekomposisi)</li>
          <li>Menemukan pola dan hubungan dari suatu permasalahan</li>
          <li>Menyusun langkah-langkah penyelesaian masalah secara logis dan sistematis (algoritma)</li>
         </ul>
        </div>
        <div class="bg-green-50 p-6 rounded-lg border-l-4 border-green-600">
         <h3 class="text-xl font-bold text-blue-900 mb-2">💡 Apa itu Berpikir Komputasional?</h3>
         <p class="text-gray-700 mb-3">Berpikir komputasional adalah cara berpikir untuk menyelesaikan masalah dengan menggunakan prinsip-prinsip ilmu komputer. Bukan hanya tentang programming, tetapi tentang cara berpikir logis dan sistematis.</p>
         <p class="text-gray-700">Ini melibatkan empat pilar utama: dekomposisi, pengenalan pola, abstraksi, dan algoritma.</p>
        </div>
        <div class="bg-purple-50 p-6 rounded-lg border-l-4 border-purple-600">
         <h3 class="text-xl font-bold text-blue-900 mb-2">🚀 Panduan Pembelajaran</h3>
         <ol class="list-decimal list-inside text-gray-700 space-y-2">
          <li><strong>Baca Materi:</strong> Pelajari konsep-konsep di menu Materi</li>
          <li><strong>Latihan Simulasi:</strong> Kerjakan 10 soal di menu Simulasi untuk uji pemahaman</li>
          <li><strong>Mainkan Kuis:</strong> Tantang diri Anda dengan 4 permainan edukatif</li>
          <li><strong>Raih Sertifikat:</strong> Dapatkan sertifikat setelah menyelesaikan latihan</li>
         </ol>
        </div>
        <div class="bg-yellow-50 p-6 rounded-lg border-l-4 border-yellow-600">
         <h3 class="text-xl font-bold text-blue-900 mb-2">📊 Fitur Pembelajaran</h3>
         <ul class="list-disc list-inside text-gray-700 space-y-1">
          <li>Materi interaktif dengan tab dan reveal animation</li>
          <li>Simulasi dengan tiga tipe soal: Drag &amp; Drop, Multiple Choice, dan Mark the Word</li>
          <li>Empat permainan kuis dengan level progresif</li>
          <li>Sistem skor dan sertifikat pencapaian</li>
          <li>Audio effects dan musik latar yang dapat disesuaikan</li>
         </ul>
        </div>
       </div>
      </div>
     </div><button onclick="goToSection('materi')" class="bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-8 rounded-lg text-lg w-full"> 📚 Mulai Belajar Materi → </button>
    </div>
   </div><!-- MATERI SECTION -->
   <div id="materi-section" class="hidden w-full h-full p-8 overflow-auto">
    <div class="max-w-4xl mx-auto">
     <h1 class="text-4xl font-bold text-blue-900 mb-6">📚 Materi - Berpikir Komputasional</h1><!-- Tab Navigation -->
     <div class="flex flex-wrap gap-2 mb-8 border-b-2 border-gray-200">
      <button class="tab-button active px-6 py-3 font-semibold text-blue-900" onclick="switchTab('tab1')"> 🧠 Konsep Dasar </button> <button class="tab-button px-6 py-3 font-semibold text-blue-900" onclick="switchTab('tab2')"> 🔍 Dekomposisi </button> <button class="tab-button px-6 py-3 font-semibold text-blue-900" onclick="switchTab('tab3')"> 🎨 Pengenalan Pola </button> <button class="tab-button px-6 py-3 font-semibold text-blue-900" onclick="switchTab('tab4')"> ⚙️ Algoritma </button>
     </div><!-- Tab Content -->
     <div id="tab1" class="tab-content bg-white p-8 rounded-lg shadow-lg mb-8">
      <h2 class="text-2xl font-bold text-blue-900 mb-4">🧠 Konsep Dasar Berpikir Komputasional</h2>
      <div class="space-y-4 text-gray-700">
       <p>Berpikir komputasional adalah kemampuan untuk memecahkan masalah menggunakan konsep-konsep dari ilmu komputer. Ini bukan hanya tentang coding, tetapi tentang:</p>
       <div class="bg-blue-50 p-4 rounded-lg">
        <p><strong>✓ Berpikir secara logis:</strong> Menganalisis masalah dengan cara yang terstruktur</p>
       </div>
       <div class="bg-blue-50 p-4 rounded-lg">
        <p><strong>✓ Berpikir sistematik:</strong> Mengikuti langkah-langkah yang teratur</p>
       </div>
       <div class="bg-blue-50 p-4 rounded-lg">
        <p><strong>✓ Berpikir kreatif:</strong> Menemukan solusi-solusi inovatif</p>
       </div>
       <p class="mt-6"><strong>Empat Pilar Berpikir Komputasional:</strong></p>
       <ol class="list-decimal list-inside space-y-2">
        <li><strong>Dekomposisi:</strong> Memecah masalah besar menjadi bagian-bagian kecil</li>
        <li><strong>Pengenalan Pola:</strong> Menemukan kesamaan atau pola dalam masalah</li>
        <li><strong>Abstraksi:</strong> Mengabaikan detail yang tidak penting</li>
        <li><strong>Algoritma:</strong> Merancang solusi langkah demi langkah</li>
       </ol>
      </div>
     </div>
     <div id="tab2" class="tab-content hidden bg-white p-8 rounded-lg shadow-lg mb-8">
      <h2 class="text-2xl font-bold text-blue-900 mb-4">🔍 Dekomposisi</h2>
      <div class="space-y-4 text-gray-700">
       <p><strong>Dekomposisi</strong> adalah teknik memecah masalah kompleks menjadi bagian-bagian yang lebih sederhana dan mudah dipahami.</p>
       <div class="bg-green-50 p-4 rounded-lg">
        <p><strong>Contoh 1:</strong> Membuat Sandwich</p>
        <ul class="list-disc list-inside ml-4 mt-2">
         <li>Siapkan roti dan isian</li>
         <li>Oleskan mayones di roti</li>
         <li>Letakkan isian di atas mayones</li>
         <li>Tutup dengan roti kedua</li>
         <li>Potong diagonal</li>
        </ul>
       </div>
       <div class="bg-green-50 p-4 rounded-lg">
        <p><strong>Contoh 2:</strong> Mengatur Ruangan</p>
        <ul class="list-disc list-inside ml-4 mt-2">
         <li>Membersihkan lantai</li>
         <li>Merapikan furnitur</li>
         <li>Menata barang-barang</li>
         <li>Membersihkan debu</li>
        </ul>
       </div>
       <p class="mt-6"><strong>Keuntungan Dekomposisi:</strong></p>
       <ul class="list-disc list-inside space-y-1">
        <li>Masalah menjadi lebih mudah dipahami</li>
        <li>Dapat menyelesaikan satu bagian pada satu waktu</li>
        <li>Memudahkan kolaborasi dalam tim</li>
        <li>Mengurangi kesalahan</li>
       </ul>
      </div>
     </div>
     <div id="tab3" class="tab-content hidden bg-white p-8 rounded-lg shadow-lg mb-8">
      <h2 class="text-2xl font-bold text-blue-900 mb-4">🎨 Pengenalan Pola (Pattern Recognition)</h2>
      <div class="space-y-4 text-gray-700">
       <p><strong>Pengenalan Pola</strong> adalah kemampuan untuk menemukan kesamaan, kemiripan, atau urutan dalam suatu masalah.</p>
       <div class="bg-purple-50 p-4 rounded-lg">
        <p><strong>Contoh Pola Angka:</strong></p>
        <p class="ml-4 mt-2 font-mono">2, 4, 6, 8, 10, ?</p>
        <p class="ml-4 text-sm">Pola: Bertambah 2 setiap kali → Jawaban: 12</p>
       </div>
       <div class="bg-purple-50 p-4 rounded-lg">
        <p><strong>Contoh Pola Visual:</strong></p>
        <p class="ml-4 mt-2">🔴 🔵 🟡 🔴 🔵 🟡 🔴 ?</p>
        <p class="ml-4 text-sm">Pola: 3 warna berulang → Jawaban: 🔵</p>
       </div>
       <p class="mt-6"><strong>Mengapa Pengenalan Pola Penting?</strong></p>
       <ul class="list-disc list-inside space-y-1">
        <li>Membantu memprediksi solusi</li>
        <li>Menghemat waktu dan usaha</li>
        <li>Dapat digunakan kembali untuk masalah serupa</li>
        <li>Meningkatkan efisiensi</li>
       </ul>
      </div>
     </div>
     <div id="tab4" class="tab-content hidden bg-white p-8 rounded-lg shadow-lg mb-8">
      <h2 class="text-2xl font-bold text-blue-900 mb-4">⚙️ Algoritma</h2>
      <div class="space-y-4 text-gray-700">
       <p><strong>Algoritma</strong> adalah serangkaian langkah-langkah logis dan sistematis untuk menyelesaikan masalah atau mencapai tujuan tertentu.</p>
       <div class="bg-orange-50 p-4 rounded-lg">
        <p><strong>Ciri-ciri Algoritma yang Baik:</strong></p>
        <ul class="list-disc list-inside ml-4 mt-2 space-y-1">
         <li>Jelas dan spesifik</li>
         <li>Terurut dengan baik</li>
         <li>Dapat diikuti untuk mendapatkan hasil yang sama</li>
         <li>Berhenti pada suatu titik</li>
        </ul>
       </div>
       <div class="bg-orange-50 p-4 rounded-lg">
        <p><strong>Contoh Algoritma: Mencari Kunci yang Hilang</strong></p>
        <ol class="list-decimal list-inside ml-4 mt-2 space-y-1">
         <li>Ingat kembali tempat terakhir menggunakan kunci</li>
         <li>Cari di sekitar tempat itu terlebih dahulu</li>
         <li>Jika tidak ditemukan, periksa kamar tidur</li>
         <li>Jika masih tidak ditemukan, periksa dapur</li>
         <li>Ulangi pencarian di tempat-tempat lain</li>
         <li>Jika sudah ditemukan, selesai</li>
        </ol>
       </div>
       <p class="mt-6"><strong>Representasi Algoritma:</strong></p>
       <ul class="list-disc list-inside space-y-1">
        <li>Pseudocode: Bahasa mirip manusia</li>
        <li>Flowchart: Diagram alur</li>
        <li>Code: Bahasa pemrograman</li>
       </ul>
      </div>
     </div><button onclick="goToSection('simulasi')" class="bg-purple-600 hover:bg-purple-700 text-white font-bold py-3 px-8 rounded-lg text-lg w-full"> 🧪 Lanjut ke Simulasi → </button>
    </div>
   </div><!-- SIMULASI SECTION -->
   <div id="simulasi-section" class="hidden w-full h-full p-8 overflow-auto">
    <div class="max-w-4xl mx-auto">
     <h1 class="text-4xl font-bold text-blue-900 mb-4">🧪 Simulasi - Uji Pemahaman</h1><!-- Progress Bar -->
     <div class="mb-6">
      <div class="flex justify-between items-center mb-2">
       <span class="text-sm font-semibold text-gray-700">Soal <span id="current-question">1</span>/10</span> <span class="text-sm font-semibold text-gray-700" id="score-display">Skor: 0</span>
      </div>
      <div class="progress-bar">
       <div id="progress-fill" class="progress-fill" style="width: 10%;"></div>
      </div>
     </div>
     <div id="simulation-container" class="bg-white p-8 rounded-lg shadow-lg mb-8">
      <!-- Questions will be inserted here -->
     </div>
     <div class="flex gap-4">
      <button id="prev-sim-btn" onclick="previousSimQuestion()" class="flex-1 bg-gray-400 hover:bg-gray-500 text-white font-bold py-3 px-6 rounded-lg"> ← Sebelumnya </button> <button id="next-sim-btn" onclick="nextSimQuestion()" class="flex-1 bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-6 rounded-lg"> Selanjutnya → </button>
     </div><button id="submit-sim-btn" onclick="submitSimulation()" class="w-full bg-green-600 hover:bg-green-700 text-white font-bold py-3 px-6 rounded-lg mt-4 hidden"> ✓ Selesai &amp; Lihat Hasil </button>
    </div>
   </div><!-- KUIS SECTION -->
   <div id="kuis-section" class="hidden w-full h-full p-8 overflow-auto">
    <div class="max-w-4xl mx-auto">
     <h1 class="text-4xl font-bold text-blue-900 mb-6">🎮 Kuis - 4 Permainan Edukatif</h1>
     <div id="kuis-menu" class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
      <div onclick="startQuiz(1)" class="bg-white p-8 rounded-lg shadow-lg hover:shadow-2xl cursor-pointer border-l-4 border-blue-600">
       <div class="text-4xl mb-4">
        🧩
       </div>
       <h3 class="text-xl font-bold text-blue-900 mb-2">Kuis 1: Pilih Jawaban Benar</h3>
       <p class="text-gray-600 mb-4">Jawab pertanyaan pilihan ganda tentang berpikir komputasional</p>
       <div class="text-sm text-gray-500">
        5 Level Progresif
       </div>
      </div>
      <div onclick="startQuiz(2)" class="bg-white p-8 rounded-lg shadow-lg hover:shadow-2xl cursor-pointer border-l-4 border-green-600">
       <div class="text-4xl mb-4">
        🎯
       </div>
       <h3 class="text-xl font-bold text-blue-900 mb-2">Kuis 2: Mengurutkan Langkah</h3>
       <p class="text-gray-600 mb-4">Urutkan langkah-langkah algoritma dengan benar</p>
       <div class="text-sm text-gray-500">
        4 Level Progresif
       </div>
      </div>
      <div onclick="startQuiz(3)" class="bg-white p-8 rounded-lg shadow-lg hover:shadow-2xl cursor-pointer border-l-4 border-purple-600">
       <div class="text-4xl mb-4">
        🔍
       </div>
       <h3 class="text-xl font-bold text-blue-900 mb-2">Kuis 3: Temukan Pola</h3>
       <p class="text-gray-600 mb-4">Temukan pola dan lanjutkan deret berikutnya</p>
       <div class="text-sm text-gray-500">
        5 Level Progresif
       </div>
      </div>
      <div onclick="startQuiz(4)" class="bg-white p-8 rounded-lg shadow-lg hover:shadow-2xl cursor-pointer border-l-4 border-orange-600">
       <div class="text-4xl mb-4">
        🏆
       </div>
       <h3 class="text-xl font-bold text-blue-900 mb-2">Kuis 4: Challenge Master</h3>
       <p class="text-gray-600 mb-4">Tantangan kombinasi dari semua konsep</p>
       <div class="text-sm text-gray-500">
        3 Level Progresif
       </div>
      </div>
     </div>
     <div id="quiz-game" class="hidden">
      <!-- Quiz content will be inserted here -->
     </div>
    </div>
   </div><!-- CERTIFICATE SECTION -->
   <div id="certificate-section" class="hidden w-full h-full p-8 overflow-auto flex items-center justify-center">
    <div class="w-full max-w-2xl">
     <div class="certificate animate-scale-in">
      <div class="certificate-border">
       <p class="text-sm tracking-widest mb-4">SERTIFIKAT PENCAPAIAN</p>
       <h2 class="text-3xl font-bold mb-8">Selamat! 🎉</h2>
       <div class="my-8 border-2 border-white py-4">
        <p class="text-sm opacity-90 mb-2">Atas Nama</p>
        <p class="text-3xl font-bold" id="cert-name">Nama Siswa</p>
       </div>
       <p class="mb-6">Telah Menyelesaikan Program Pembelajaran Interaktif</p>
       <h3 class="text-2xl font-bold mb-6">Berpikir Komputasional</h3>
       <div class="grid grid-cols-3 gap-4 mb-8 text-center">
        <div>
         <p class="text-sm opacity-90">Nilai Simulasi</p>
         <p class="text-2xl font-bold" id="cert-sim-score">-</p>
        </div>
        <div>
         <p class="text-sm opacity-90">Nilai Kuis</p>
         <p class="text-2xl font-bold" id="cert-quiz-score">-</p>
        </div>
        <div>
         <p class="text-sm opacity-90">Total Nilai</p>
         <p class="text-2xl font-bold" id="cert-total-score">-</p>
        </div>
       </div>
       <p class="text-xs opacity-90 mb-4">Diberikan pada: <span id="cert-date">-</span></p>
       <p class="text-xs opacity-90">Pengembang: Suci Mega Dian Sari | Tahun 2026</p>
      </div>
     </div><button onclick="downloadCertificate()" class="w-full bg-yellow-400 hover:bg-yellow-300 text-blue-900 font-bold py-3 px-6 rounded-lg mt-8 mb-4"> 📥 Download Sertifikat </button> <button onclick="goHome()" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-6 rounded-lg"> 🏠 Kembali ke Beranda </button>
    </div>
   </div>
  </div><!-- Audio Elements -->
  <audio id="click-sound" preload="auto">
   <source src="data:audio/wav;base64,UklGRiYAAABXQVZFZm10IBAAAAABAAEAQB8AAAB9AAACABAAZGF0YQIAAAAAAA==" type="audio/wav">
  </audio>
  <audio id="background-music" loop preload="auto">
   <source src="data:audio/wav;base64,UklGRiYAAABXQVZFZm10IBAAAAABAAEAQB8AAAB9AAACABAAZGF0YQIAAAAAAA==" type="audio/wav">
  </audio>
  <audio id="success-sound" preload="auto">
   <source src="data:audio/wav;base64,UklGRiYAAABXQVZFZm10IBAAAAABAAEAQB8AAAB9AAACABAAZGF0YQIAAAAAAA==" type="audio/wav">
  </audio>
  <script>
        let isMusicOn = true;
        let currentVolume = 0.5;
        let currentStudent = { name: '', simScore: 0, quizScores: [] };
        let simulationAnswers = [];
        let currentSimQuestion = 0;
        let currentQuizType = 0;
        let currentQuizLevel = 0;
        let currentQuizScore = 0;

        // Initialize UI
        lucide.createIcons();

        // Data SDK Handler
        const dataHandler = {
            onDataChanged(data) {
                console.log('Data updated:', data);
            }
        };

        // Initialize Data SDK
        (async () => {
            const initResult = await window.dataSdk.init(dataHandler);
            if (!initResult.isOk) {
                console.error('Failed to initialize Data SDK');
            }
        })();

        // Simulation Questions
        const simulationQuestions = [
            {
                type: 'multiple-choice',
                question: '1. Apa yang dimaksud dengan dekomposisi dalam berpikir komputasional?',
                options: [
                    'Memecah masalah besar menjadi bagian-bagian kecil',
                    'Menggabungkan beberapa masalah menjadi satu',
                    'Mengulangi proses yang sama berkali-kali',
                    'Mengabaikan detail yang tidak penting'
                ],
                correct: 0
            },
            {
                type: 'mark-the-word',
                question: '2. Identifikasi pilar berpikir komputasional yang benar:',
                text: 'Dekomposisi, Pengenalan Pola, Abstraksi, Algoritma, Coding',
                words: [0, 1, 2, 3],
                correctWords: [0, 1, 2, 3]
            },
            {
                type: 'drag-the-word',
                question: '3. Urutkan langkah-langkah membuat roti panggang:',
                items: ['Siapkan roti', 'Oleskan mentega', 'Panggang di oven', 'Sajikan di piring'],
                order: [0, 1, 2, 3]
            },
            {
                type: 'multiple-choice',
                question: '4. Contoh pengenalan pola yang benar adalah:',
                options: [
                    '2, 4, 6, 8, 10 (Pola: bertambah 2)',
                    'Acak tanpa urutan',
                    'Hanya satu elemen',
                    'Tidak ada hubungan'
                ],
                correct: 0
            },
            {
                type: 'mark-the-word',
                question: '5. Pilih ciri-ciri algoritma yang baik:',
                text: 'Jelas, Spesifik, Terurut, Kompleks, Tidak Tentu',
                words: [0, 1, 2, 3, 4],
                correctWords: [0, 1, 2]
            },
            {
                type: 'drag-the-word',
                question: '6. Urutkan tahap penyelesaian masalah:',
                items: ['Analisis', 'Solusi', 'Implementasi', 'Evaluasi'],
                order: [0, 1, 2, 3]
            },
            {
                type: 'multiple-choice',
                question: '7. Berpikir komputasional paling penting untuk:',
                options: [
                    'Memecahkan masalah secara logis dan sistematis',
                    'Hanya untuk programmer',
                    'Bermain game komputer',
                    'Tidak berguna dalam kehidupan'
                ],
                correct: 0
            },
            {
                type: 'mark-the-word',
                question: '8. Mana yang bukan pilar berpikir komputasional:',
                text: 'Dekomposisi, Coding, Abstraksi, Algoritma, Debugging',
                words: [0, 1, 2, 3, 4],
                correctWords: [1, 4]
            },
            {
                type: 'drag-the-word',
                question: '9. Urutkan proses debug program:',
                items: ['Jalankan program', 'Temukan error', 'Perbaiki', 'Test lagi'],
                order: [0, 1, 2, 3]
            },
            {
                type: 'multiple-choice',
                question: '10. Aspek terpenting dalam algoritma adalah:',
                options: [
                    'Efisien dan sistematis',
                    'Panjang dan rumit',
                    'Menggunakan teknik terbaru',
                    'Hanya untuk ahli'
                ],
                correct: 0
            }
        ];

        // Quiz Data
        const quizzes = {
            1: {
                name: 'Pilih Jawaban Benar',
                levels: [
                    {
                        question: 'Apa kepanjangan dari pilar pertama berpikir komputasional?',
                        options: ['Dekomposisi', 'Desain', 'Debugging', 'Database'],
                        correct: 0
                    },
                    {
                        question: 'Pengenalan pola membantu dalam:',
                        options: ['Memprediksi solusi', 'Menghemat waktu', 'Meningkatkan efisiensi', 'Semua benar'],
                        correct: 3
                    },
                    {
                        question: 'Algoritma adalah:',
                        options: ['Bahasa pemrograman', 'Langkah-langkah sistematis', 'Komputer', 'Bug'],
                        correct: 1
                    },
                    {
                        question: 'Dekomposisi paling penting untuk:',
                        options: ['Masalah sederhana', 'Masalah kompleks', 'Masalah mudah', 'Masalah kecil'],
                        correct: 1
                    },
                    {
                        question: 'Abstraksi dalam berpikir komputasional adalah:',
                        options: ['Menambah detail', 'Mengabaikan detail penting', 'Fokus pada aspek penting', 'Membuang informasi'],
                        correct: 2
                    }
                ]
            },
            2: {
                name: 'Mengurutkan Langkah',
                levels: [
                    {
                        question: 'Urutkan langkah membuat kopi:',
                        items: ['Siapkan cangkir', 'Seduh kopi', 'Tuang air panas', 'Minum'],
                        correct: [0, 2, 1, 3]
                    },
                    {
                        question: 'Urutkan langkah login ke website:',
                        items: ['Buka browser', 'Klik login', 'Isi password', 'Tekan Enter'],
                        correct: [0, 2, 1, 3]
                    },
                    {
                        question: 'Urutkan langkah mencuci tangan:',
                        items: ['Ambil sabun', 'Bilas dengan air', 'Gosok tangan', 'Keringkan'],
                        correct: [0, 2, 1, 3]
                    },
                    {
                        question: 'Urutkan langkah debug program:',
                        items: ['Jalankan', 'Temukan error', 'Perbaiki code', 'Test hasil'],
                        correct: [0, 1, 2, 3]
                    }
                ]
            },
            3: {
                name: 'Temukan Pola',
                levels: [
                    {
                        question: '2, 4, 6, 8, ?',
                        options: ['9', '10', '12', '11'],
                        correct: 1
                    },
                    {
                        question: '1, 1, 2, 3, 5, 8, ?',
                        options: ['11', '12', '13', '14'],
                        correct: 2
                    },
                    {
                        question: 'A, B, C, D, E, F, ?',
                        options: ['G', 'H', 'I', 'J'],
                        correct: 0
                    },
                    {
                        question: '100, 90, 80, 70, ?',
                        options: ['50', '60', '65', '55'],
                        correct: 1
                    },
                    {
                        question: '2, 6, 12, 20, ?',
                        options: ['28', '30', '32', '35'],
                        correct: 2
                    }
                ]
            },
            4: {
                name: 'Challenge Master',
                levels: [
                    {
                        question: 'Dekomposisi membantu untuk:',
                        options: ['Membuat masalah lebih rumit', 'Memecah masalah besar', 'Mengabaikan masalah', 'Menggabungkan masalah'],
                        correct: 1
                    },
                    {
                        question: 'Pola dalam deret 5, 10, 15, 20 adalah:',
                        options: ['Bertambah 5', 'Bertambah 10', 'Bertambah 15', 'Berlipat ganda'],
                        correct: 0
                    },
                    {
                        question: 'Algoritma yang efisien adalah:',
                        options: ['Panjang', 'Kompleks', 'Sistematis dan cepat', 'Rumit'],
                        correct: 2
                    }
                ]
            }
        };

        // Functions
        function playClickSound() {
            if (isMusicOn) {
                try {
                    const sound = document.getElementById('click-sound');
                    sound.currentTime = 0;
                    sound.play().catch(() => {});
                } catch (e) {}
            }
        }

        function startApp() {
            playClickSound();
            document.getElementById('splash-screen').classList.add('hidden');
            document.getElementById('main-menu').classList.remove('hidden');
            document.getElementById('home-btn').classList.remove('hidden');
        }

        function goToSection(section) {
            playClickSound();
            document.querySelectorAll('[id$="-section"]').forEach(el => {
                if (!el.id.includes('splash')) el.classList.add('hidden');
            });
            
            if (section === 'beranda') document.getElementById('beranda-section').classList.remove('hidden');
            if (section === 'materi') document.getElementById('materi-section').classList.remove('hidden');
            if (section === 'simulasi') {
                document.getElementById('simulasi-section').classList.remove('hidden');
                loadSimulation();
            }
            if (section === 'kuis') document.getElementById('kuis-section').classList.remove('hidden');
        }

        function goHome() {
            playClickSound();
            document.querySelectorAll('[id$="-section"]').forEach(el => {
                if (!el.id.includes('splash')) el.classList.add('hidden');
            });
            document.getElementById('main-menu').classList.remove('hidden');
            currentSimQuestion = 0;
            simulationAnswers = [];
        }

        function toggleMusic() {
            playClickSound();
            isMusicOn = !isMusicOn;
            document.getElementById('music-toggle').textContent = isMusicOn ? 'ON' : 'OFF';
            document.getElementById('music-toggle').className = isMusicOn 
                ? 'bg-blue-600 hover:bg-blue-700 text-white px-6 py-2 rounded-lg font-semibold'
                : 'bg-gray-600 hover:bg-gray-700 text-white px-6 py-2 rounded-lg font-semibold';
        }

        function setVolume(value) {
            currentVolume = value / 100;
            document.getElementById('volume-display').textContent = value + '%';
        }

        function saveStudentName() {
            const name = document.getElementById('student-name').value.trim();
            if (name.length > 0) {
                currentStudent.name = name;
                playClickSound();
                alert(`Selamat datang, ${name}! Semoga pembelajaran bermanfaat.`);
                document.getElementById('student-name').value = '';
            } else {
                alert('Silakan masukkan nama Anda terlebih dahulu.');
            }
        }

        function switchTab(tabName) {
            playClickSound();
            document.querySelectorAll('.tab-content').forEach(tab => tab.classList.add('hidden'));
            document.querySelectorAll('.tab-button').forEach(btn => btn.classList.remove('active'));
            document.getElementById(tabName).classList.remove('hidden');
            event.target.classList.add('active');
        }

        function loadSimulation() {
            currentSimQuestion = 0;
            simulationAnswers = new Array(simulationQuestions.length).fill(null);
            displaySimQuestion();
        }

        function displaySimQuestion() {
            const q = simulationQuestions[currentSimQuestion];
            let html = `<h2 class="text-2xl font-bold text-blue-900 mb-6">${q.question}</h2>`;

            if (q.type === 'multiple-choice') {
                html += '<div class="space-y-3">';
                q.options.forEach((opt, idx) => {
                    const isSelected = simulationAnswers[currentSimQuestion] === idx;
                    html += `<button onclick="selectSimAnswer(${idx})" class="w-full p-4 text-left rounded-lg border-2 ${
                        isSelected ? 'bg-blue-200 border-blue-600' : 'bg-gray-100 border-gray-300 hover:border-blue-400'
                    } transition">
                        <div class="flex items-center gap-3">
                            <div class="w-6 h-6 rounded-full border-2 ${isSelected ? 'bg-blue-600 border-blue-600' : 'border-gray-400'}"></div>
                            ${opt}
                        </div>
                    </button>`;
                });
                html += '</div>';
            } else if (q.type === 'drag-the-word') {
                html += '<p class="text-gray-700 mb-4">Seret dan urutkan item-item di bawah:</p>';
                html += '<div class="drop-zone" id="drop-zone" style="min-height: 120px;">';
                (simulationAnswers[currentSimQuestion] || q.items).forEach((item, idx) => {
                    html += `<div class="drag-item" draggable="true" data-index="${idx}">${item}</div>`;
                });
                html += '</div>';
            } else if (q.type === 'mark-the-word') {
                html += `<p class="text-gray-700 mb-4">${q.text}</p>`;
                html += '<div class="space-y-2">';
                q.words.forEach((wordIdx, displayIdx) => {
                    const word = q.text.split(', ')[displayIdx];
                    const isMarked = simulationAnswers[currentSimQuestion]?.includes(displayIdx);
                    html += `<button onclick="toggleMarkWord(${displayIdx})" class="w-full p-3 text-left rounded-lg ${
                        isMarked ? 'bg-green-200 border-2 border-green-600' : 'bg-gray-100 border-2 border-gray-300'
                    }">
                        ✓ ${word}
                    </button>`;
                });
                html += '</div>';
            }

            document.getElementById('simulation-container').innerHTML = html;
            updateSimButtons();
            document.getElementById('progress-fill').style.width = ((currentSimQuestion + 1) / simulationQuestions.length * 100) + '%';
            document.getElementById('current-question').textContent = currentSimQuestion + 1;
        }

        function selectSimAnswer(idx) {
            playClickSound();
            simulationAnswers[currentSimQuestion] = idx;
            displaySimQuestion();
        }

        function toggleMarkWord(idx) {
            playClickSound();
            if (!simulationAnswers[currentSimQuestion]) simulationAnswers[currentSimQuestion] = [];
            if (simulationAnswers[currentSimQuestion].includes(idx)) {
                simulationAnswers[currentSimQuestion] = simulationAnswers[currentSimQuestion].filter(i => i !== idx);
            } else {
                simulationAnswers[currentSimQuestion].push(idx);
            }
            displaySimQuestion();
        }

        function nextSimQuestion() {
            if (currentSimQuestion < simulationQuestions.length - 1) {
                currentSimQuestion++;
                displaySimQuestion();
            }
        }

        function previousSimQuestion() {
            if (currentSimQuestion > 0) {
                currentSimQuestion--;
                displaySimQuestion();
            }
        }

        function updateSimButtons() {
            document.getElementById('prev-sim-btn').disabled = currentSimQuestion === 0;
            document.getElementById('prev-sim-btn').className = currentSimQuestion === 0 
                ? 'flex-1 bg-gray-300 text-gray-500 font-bold py-3 px-6 rounded-lg cursor-not-allowed'
                : 'flex-1 bg-gray-400 hover:bg-gray-500 text-white font-bold py-3 px-6 rounded-lg';
            
            if (currentSimQuestion === simulationQuestions.length - 1) {
                document.getElementById('next-sim-btn').classList.add('hidden');
                document.getElementById('submit-sim-btn').classList.remove('hidden');
            } else {
                document.getElementById('next-sim-btn').classList.remove('hidden');
                document.getElementById('submit-sim-btn').classList.add('hidden');
            }
        }

        function calculateSimScore() {
            let correct = 0;
            simulationQuestions.forEach((q, idx) => {
                if (q.type === 'multiple-choice' && simulationAnswers[idx] === q.correct) {
                    correct++;
                } else if (q.type === 'drag-the-word' && JSON.stringify(simulationAnswers[idx]) === JSON.stringify(q.order)) {
                    correct++;
                } else if (q.type === 'mark-the-word') {
                    const userMarked = (simulationAnswers[idx] || []).sort((a, b) => a - b);
                    const correct_marked = q.correctWords.sort((a, b) => a - b);
                    if (JSON.stringify(userMarked) === JSON.stringify(correct_marked)) {
                        correct++;
                    }
                }
            });
            return Math.round((correct / simulationQuestions.length) * 100);
        }

        async function submitSimulation() {
            const score = calculateSimScore();
            currentStudent.simScore = score;
            
            // Save to Canva Sheet
            const result = await window.dataSdk.create({
                student_name: currentStudent.name || 'Siswa Anonim',
                simulation_score: score,
                quiz_scores: currentStudent.quizScores.join(',') || '0',
                completion_time: new Date().toLocaleTimeString('id-ID'),
                completion_date: new Date().toLocaleDateString('id-ID')
            });

            if (result.isOk) {
                playClickSound();
                showCertificate();
            }
        }

        function startQuiz(quizType) {
            playClickSound();
            currentQuizType = quizType;
            currentQuizLevel = 0;
            currentQuizScore = 0;
            displayQuizQuestion();
        }

        function displayQuizQuestion() {
            const quiz = quizzes[currentQuizType];
            const level = quiz.levels[currentQuizLevel];
            
            let html = `<h2 class="text-2xl font-bold text-blue-900 mb-4">${quiz.name} - Level ${currentQuizLevel + 1}</h2>`;
            html += `<p class="text-gray-700 mb-6">${level.question}</p>`;

            if (level.options) {
                html += '<div class="space-y-3">';
                level.options.forEach((opt, idx) => {
                    html += `<button onclick="selectQuizAnswer(${idx}, ${level.correct})" class="w-full p-4 text-left bg-gray-100 hover:bg-blue-100 rounded-lg border-2 border-gray-300 transition">
                        ${opt}
                    </button>`;
                });
                html += '</div>';
            } else if (level.items) {
                html += '<div id="quiz-ordering" class="space-y-2">';
                level.items.forEach((item, idx) => {
                    html += `<div class="p-3 bg-blue-50 rounded-lg border-l-4 border-blue-600">${idx + 1}. ${item}</div>`;
                });
                html += '</div><button onclick="nextQuizLevel()" class="w-full mt-4 bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 rounded-lg">Lanjut</button>';
            }

            document.getElementById('quiz-game').innerHTML = html;
            document.getElementById('quiz-game').classList.remove('hidden');
            document.getElementById('kuis-menu').classList.add('hidden');
        }

        function selectQuizAnswer(selected, correct) {
            playClickSound();
            if (selected === correct) {
                currentQuizScore += 20;
                if (currentQuizLevel < quizzes[currentQuizType].levels.length - 1) {
                    setTimeout(() => {
                        currentQuizLevel++;
                        displayQuizQuestion();
                    }, 500);
                } else {
                    currentStudent.quizScores.push(currentQuizScore);
                    setTimeout(() => {
                        backToQuizMenu();
                    }, 500);
                }
            } else {
                alert('Jawaban kurang tepat, coba lagi!');
            }
        }

        function nextQuizLevel() {
            currentStudent.quizScores.push(currentQuizScore);
            backToQuizMenu();
        }

        function backToQuizMenu() {
            document.getElementById('quiz-game').classList.add('hidden');
            document.getElementById('kuis-menu').classList.remove('hidden');
        }

        function showCertificate() {
            document.querySelectorAll('[id$="-section"]').forEach(el => {
                if (!el.id.includes('splash')) el.classList.add('hidden');
            });
            
            document.getElementById('cert-name').textContent = currentStudent.name || 'Siswa Anonim';
            document.getElementById('cert-sim-score').textContent = currentStudent.simScore + '%';
            const avgQuizScore = currentStudent.quizScores.length > 0 
                ? Math.round(currentStudent.quizScores.reduce((a, b) => a + b) / currentStudent.quizScores.length)
                : 0;
            document.getElementById('cert-quiz-score').textContent = avgQuizScore + '%';
            const totalScore = Math.round((currentStudent.simScore + avgQuizScore) / 2);
            document.getElementById('cert-total-score').textContent = totalScore + '%';
            document.getElementById('cert-date').textContent = new Date().toLocaleDateString('id-ID');
            
            document.getElementById('certificate-section').classList.remove('hidden');
        }

        function downloadCertificate() {
            playClickSound();
            alert('Sertifikat telah disimpan! (Fitur download tersedia di browser Anda dengan menekan Ctrl+S)');
        }

        // Initialize Lucide icons when page loads
        window.addEventListener('load', () => {
            lucide.createIcons();
        });
    </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9fe019969645401a',t:'MTc3OTE2MjIzMy4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
