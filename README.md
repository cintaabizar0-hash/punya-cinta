<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Surat Lucu Buat Kamu! 🌟</title>
    <!-- Menggunakan Tailwind CSS untuk desain cepat & estetik -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <!-- Google Fonts untuk font yang imut -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@300..700&family=Quicksand:wght@500;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Quicksand', sans-serif;
            background-color: #ffeef2;
        }
        .font-cute {
            font-family: 'Fredoka', sans-serif;
        }
        /* Efek animasi melayang untuk elemen lucu */
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }
        .floating {
            animation: float 3s ease-in-out infinite;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col items-center justify-center p-4 text-slate-700 overflow-x-hidden selection:bg-pink-200">

    <!-- Kontainer Utama -->
    <div class="max-w-md w-full bg-white/80 backdrop-blur-md rounded-3xl p-6 shadow-xl border-4 border-pink-200 text-center relative my-8">
        
        <!-- Dekorasi Lucu di Pojok -->
        <div class="absolute -top-6 -left-4 text-3xl floating" style="animation-delay: 0s;">🌸</div>
        <div class="absolute -top-8 -right-4 text-3xl floating" style="animation-delay: 1s;">✨</div>
        <div class="absolute -bottom-6 -left-4 text-3xl floating" style="animation-delay: 1.5s;">🧸</div>
        <div class="absolute -bottom-6 -right-4 text-3xl floating" style="animation-delay: 0.5s;">🐱</div>

        <!-- Header / Judul -->
        <h1 class="text-2xl md:text-3xl font-cute text-pink-500 mb-2">Pesan Rahasia Buat Kamu! 💌</h1>
        <p class="text-xs text-slate-400 mb-6">Klik tombol play di bawah biar makin dramatis~</p>

        <!-- Widget Musik (Audio Player) -->
        <div class="bg-pink-50 rounded-2xl p-4 mb-6 border border-pink-100 flex flex-col items-center justify-center">
            <span class="text-sm font-semibold text-pink-600 mb-2 flex items-center gap-1">
                🎵 Now Playing: Cute Lofi Background
            </span>
            <!-- Ganti URL src di bawah ini dengan link lagu .mp3 pilihanmu jika punya sendiri -->
            <audio id="bg-music" loop class="w-full max-w-xs mt-1">
                <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
                Browser kamu tidak mendukung pemutar musik.
            </audio>
            <p class="text-[10px] text-slate-400 mt-2">P.S. Tekan tombol play manual ya karena aturan browser terbaru!</p>
        </div>

        <!-- Bagian 1: Catatan Pendek (Pop-up/Flip Cards) -->
        <div class="mb-6">
            <h2 class="text-left font-cute text-pink-400 text-sm mb-3 px-1">💬 Catatan Random Hari Ini:</h2>
            <div class="grid grid-cols-2 gap-3">
                <div onclick="alert('Kalo kamu capek, istirahat ya! Jangan malah kayang. 🤸‍♀️')" class="bg-yellow-100 hover:bg-yellow-200 transition p-3 rounded-xl cursor-pointer shadow-sm text-xs font-medium border border-yellow-200">
                    📌 Klik Aku Dong
                </div>
                <div onclick="alert('Mikirin kamu itu kayak minum kopi, bikin deg-degan tapi nagih. ☕️')" class="bg-blue-100 hover:bg-blue-200 transition p-3 rounded-xl cursor-pointer shadow-sm text-xs font-medium border border-blue-200">
                    💡 Fakta Unik
                </div>
            </div>
        </div>

        <!-- Bagian 2: Catatan Panjang (Surat Utama) -->
        <div class="bg-gradient-to-br from-amber-50 to-orange-50 rounded-2xl p-4 border border-orange-100 text-left mb-6 shadow-inner">
            <h3 class="font-cute text-orange-500 text-sm mb-2 flex items-center gap-1">📂 Surat Agak Panjang:</h3>
            <p class="text-xs leading-relaxed text-slate-600">
                Pada akhirnya, semua akan terlewati seperti hujan sederas apapun jatuhnya, ia tak pernah abadi akan ada jeda, dan langit akan cerah pada waktu nya. Semangat selalu ya! ☀️
            </p>
            <hr class="border-orange-200/50 my-3">
            <p class="text-xs leading-relaxed text-slate-600">
                Jangan lupa makan tepat waktu, jangan nunggu laper dulu baru makan. Kalau bumi berputar terlalu cepat buatmu, pelan-pelan aja jalannya, yang penting nyampe dengan selamat. Kamu hebat kok bisa bertahan sampai hari ini! 🦖✨
            </p>
        </div>

        <!-- Elemen Interaktif Ekstra: Tombol Lucu -->
        <div class="space-y-3">
            <p class="text-xs font-semibold text-slate-500">Apakah pesan ini membantu?</p>
            <div class="flex justify-center gap-4">
                <button onclick="playHappyEfek()" class="bg-emerald-400 hover:bg-emerald-500 text-white font-cute text-xs px-4 py-2 rounded-full transition shadow-md active:scale-95">
                    Banget! 💖
                </button>
                <button id="btn-no" onmouseover="pindahTombol()" class="bg-rose-400 hover:bg-rose-500 text-white font-cute text-xs px-4 py-2 rounded-full transition shadow-md absolute md:relative">
                    Enggak 😜
                </button>
            </div>
        </div>

        <!-- Footer -->
        <footer class="mt-8 text-[10px] text-slate-400">
            Dibuat dengan 💖 untuk menghibur harimu.
        </footer>
    </div>

    <!-- Script Interaktif Javascript -->
    <script>
        // Fungsi membuat tombol "Enggak" kabur saat didekati (Biar lucu!)
        function pindahTombol() {
            const btnNo = document.getElementById('btn-no');
            // Ubah posisi tombol secara acak di dalam layar
            const x = Math.random() * (window.innerWidth - btnNo.offsetWidth - 20);
            const y = Math.random() * (window.innerHeight - btnNo.offsetHeight - 20);
            
            btnNo.style.position = 'absolute';
            btnNo.style.left = `${x}px`;
            btnNo.style.top = `${y}px`;
        }

        // Efek ketika menekan tombol "Banget!"
        function playHappyEfek() {
            alert('Yay! Makasih yaaa~ Semoga harimu menyenangkan dan dipenuhi makanan enak! 🍕🍰🍟');
        }
    </script>
</body>
</html>
