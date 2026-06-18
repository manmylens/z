<html lang="ms" class="scroll-smooth">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  
  <!-- Google Fonts & Tailwind CSS -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;700;900&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- Lucide Icons CDN -->
  <script src="https://unpkg.com/lucide@latest"></script>

  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            serif: ['Cinzel', 'serif'],
            sans: ['Plus Jakarta Sans', 'sans-serif'],
          },
          colors: {
            gold: {
              DEFAULT: '#d4af37',
              light: '#f3e5ab',
              dark: '#aa8c2c'
            }
          }
        }
      }
    }
  </script>

  <style>
    /* Premium Smooth Scrollbar */
    ::-webkit-scrollbar {
      width: 6px;
      height: 6px;
    }
    ::-webkit-scrollbar-track {
      background: #090909;
    }
    ::-webkit-scrollbar-thumb {
      background: #d4af37;
      border-radius: 10px;
    }
    ::-webkit-scrollbar-thumb:hover {
      background: #f3e5ab;
    }

    /* Slider Hide Scrollbar for Elegant view but keep functionality */
    .no-scrollbar::-webkit-scrollbar {
      display: none;
    }
    .no-scrollbar {
      -ms-overflow-style: none;
      scrollbar-width: none;
    }
  </style>
</head>
<body class="bg-[#050505] text-[#eaeaea] font-sans antialiased selection:bg-gold selection:text-black">

  <!-- NOTIFIKASI TOAST CUSTOM -->
  <div id="toast-notification" class="fixed bottom-6 right-6 z-50 transform translate-y-20 opacity-0 pointer-events-none transition-all duration-500 bg-gold text-black px-6 py-4 rounded shadow-2xl font-bold tracking-wider text-xs uppercase flex items-center gap-2 border border-yellow-300">
    <i data-lucide="sparkles" class="animate-spin w-4 h-4"></i>
    <span id="toast-text">Tindakan Berjaya!</span>
  </div>

  <!-- HEADER NAVBAR -->
  <header class="absolute top-0 left-0 right-0 z-40 bg-gradient-to-b from-black/80 to-transparent">
    <div class="max-w-7xl mx-auto px-6 py-6 flex justify-between items-center">
      <div class="flex items-center gap-3">
        <div class="w-9 h-9 flex items-center justify-center rounded-full border border-gold/40 bg-black/40">
          <i data-lucide="camera" class="text-gold w-4 h-4"></i>
        </div>
        <span class="font-serif text-lg font-semibold tracking-[0.25em] text-white uppercase">manmy_lens</span>
      </div>
      
      <nav class="hidden md:flex items-center gap-10 text-[11px] font-semibold tracking-[0.2em] text-zinc-300 uppercase">
        <a href="#wedding-gallery" class="hover:text-gold transition-colors duration-300">Galeri</a>
        <a href="#services" class="hover:text-gold transition-colors duration-300">Pakej Kami</a>
        <a href="#contact" class="hover:text-gold transition-colors duration-300">Hubungi</a>
      </nav>

      <div>
        <button id="admin-action-btn" onclick="toggleAdminAction()" class="flex items-center gap-1.5 bg-white/5 hover:bg-gold text-zinc-300 hover:text-black px-4 py-2 rounded border border-zinc-800 hover:border-transparent text-[10px] font-bold tracking-widest uppercase transition-all duration-350">
          <i data-lucide="lock" class="w-3 h-3"></i> <span>Admin</span>
        </button>
      </div>
    </div>
  </header>

  <!-- CINEMATIC HERO SECTION -->
  <section class="relative min-h-screen flex items-center justify-center px-6 overflow-hidden">
    <div class="absolute inset-0 z-0">
      <div class="absolute inset-0 bg-gradient-to-t from-[#050505] via-[#050505]/40 to-black/50 z-10"></div>
      <img 
        src="https://images.unsplash.com/photo-1519741497674-611481863552?auto=format&fit=crop&q=90&w=1920" 
        alt="Cinematic Wedding Backdrop" 
        class="w-full h-full object-cover object-center filter brightness-90 saturate-95"
        onerror="this.src='https://images.unsplash.com/photo-1519741497674-611481863552?auto=format&fit=crop&q=80&w=1200'"
      >
    </div>

    <!-- Elegant Bokeh Overlays -->
    <div class="absolute inset-0 pointer-events-none z-10 mix-blend-screen opacity-35">
      <div class="absolute top-1/4 left-1/3 w-96 h-96 bg-amber-500/10 rounded-full filter blur-[120px] animate-pulse"></div>
      <div class="absolute bottom-1/3 right-1/4 w-[500px] h-[500px] bg-gold/10 rounded-full filter blur-[150px]"></div>
    </div>

    <div class="max-w-5xl mx-auto text-center relative z-20 space-y-8 pt-20">
      <div class="inline-flex items-center gap-2 px-4 py-1 rounded-full bg-black/40 backdrop-blur-md border border-gold/20 text-[10px] tracking-[0.25em] text-gold uppercase font-bold">
        <i data-lucide="sparkles" class="w-3 h-3"></i>
        <span>Koleksi Fotografi Eksklusif</span>
      </div>

      <h1 class="font-serif text-5xl sm:text-7xl lg:text-8xl font-black tracking-tight text-white leading-none">
        Merakam Detik <br>
        <span class="text-transparent bg-clip-text bg-gradient-to-r from-amber-200 via-gold to-amber-100">
          Sekali Seumur Hidup
        </span>
      </h1>

      <p id="display-hero-subtitle" class="text-zinc-300 text-sm sm:text-base max-w-xl mx-auto font-sans leading-relaxed tracking-wide">
        <!-- Dinamik Subtitle -->
      </p>

      <div class="flex flex-col sm:flex-row items-center justify-center gap-6 pt-6">
        <a href="#wedding-gallery" class="bg-gold text-black hover:bg-amber-400 px-8 py-4 rounded text-xs font-bold tracking-[0.2em] uppercase transition-all duration-350 shadow-2xl shadow-gold/20">
          Teroka Karya
        </a>
        <a href="#contact" class="bg-black/40 hover:bg-white/5 text-white px-8 py-4 rounded text-xs font-semibold tracking-[0.2em] uppercase border border-white/20 transition-all duration-350">
          Hubungi Kami
        </a>
      </div>

      <div class="pt-12 flex justify-center animate-bounce">
        <a href="#wedding-gallery" class="text-zinc-500 hover:text-gold transition-colors">
          <i data-lucide="arrow-down" class="w-5 h-5"></i>
        </a>
      </div>
    </div>
  </section>

  <!-- DASHBOARD PENGURUSAN ADMIN (PASS: 041006) -->
  <section id="admin-dashboard-section" class="hidden bg-zinc-950 border-y border-gold/30 py-10 px-6">
    <div class="max-w-6xl mx-auto space-y-12">
      
      <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 pb-3 border-b border-zinc-900">
        <div class="flex items-center gap-2 text-gold font-bold text-lg">
          <i data-lucide="settings" class="w-5 h-5"></i>
          <span class="uppercase tracking-widest text-sm">Dashboard Pengurusan Mutlak</span>
        </div>
        <button 
          onclick="openResetConfirmModal()"
          class="bg-zinc-900 hover:bg-red-900/45 text-xs text-zinc-400 hover:text-red-200 px-4 py-2 rounded border border-zinc-800 hover:border-red-900/30 transition-all"
        >
          Set Semula Ke Tetapan Asal
        </button>
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-10">
        
        <!-- Bahagian 1: Pengeditan Galeri Gambar -->
        <div class="bg-zinc-900 p-6 rounded border border-zinc-800 space-y-6">
          <div class="flex items-center justify-between">
            <h3 class="text-white font-bold text-xs uppercase tracking-wider text-zinc-400">
              1. Pengurusan Gambar Galeri
            </h3>
            <div class="flex bg-zinc-950 p-1 rounded border border-zinc-800 text-[10px]">
              <button id="src-gallery-btn" onclick="setUploadSource('gallery')" class="px-3 py-1 rounded transition-all bg-gold text-black font-bold">
                <i data-lucide="upload" class="inline w-3 h-3 mr-1"></i> Galeri Telefon
              </button>
              <button id="src-url-btn" onclick="setUploadSource('url')" class="px-3 py-1 rounded transition-all text-zinc-400">
                <i data-lucide="link" class="inline w-3 h-3 mr-1"></i> Pautan URL
              </button>
            </div>
          </div>

          <div class="space-y-4">
            <div>
              <label class="block text-[10px] font-bold text-zinc-500 uppercase tracking-widest mb-1.5">Klasifikasi Galeri Sasaran</label>
              <select id="admin-img-target" class="w-full p-3 bg-zinc-950 border border-zinc-800 rounded text-sm text-white focus:outline-none focus:border-gold">
                <option value="indoor">Indoor Wedding Series</option>
                <option value="outdoor">Outdoor Wedding Series</option>
              </select>
            </div>

            <!-- Upload Galeri Tempatan -->
            <div id="source-gallery-uploader" class="border-2 border-dashed border-zinc-800 hover:border-gold/50 rounded-xl p-8 text-center transition-colors relative cursor-pointer">
              <input 
                type="file" 
                accept="image/*"
                onchange="handleLocalFile(event)"
                class="absolute inset-0 w-full h-full opacity-0 cursor-pointer"
              />
              <div class="space-y-3">
                <div class="w-12 h-12 bg-gold/10 text-gold rounded-full flex items-center justify-center mx-auto">
                  <i data-lucide="upload" class="w-5 h-5"></i>
                </div>
                <p class="text-xs font-bold text-white">Ambil dari Galeri Telefon</p>
                <p class="text-[10px] text-zinc-500">Sesuai untuk iOS & Android. Gambar akan disimpan dalam storan.</p>
              </div>
            </div>

            <!-- Upload Melalui URL -->
            <form id="source-url-uploader" class="hidden space-y-4" onsubmit="handleAddImageViaUrl(event)">
              <div>
                <label class="block text-[10px] font-bold text-zinc-500 uppercase tracking-widest mb-1.5">Pautan URL Gambar</label>
                <input 
                  id="admin-img-url-input"
                  type="url" 
                  placeholder="https://images.unsplash.com/..." 
                  class="w-full p-3 bg-zinc-950 border border-zinc-800 rounded text-sm text-white focus:outline-none focus:border-gold"
                />
              </div>
              <button 
                type="submit"
                class="w-full py-2.5 bg-white text-black hover:bg-gold font-bold rounded text-xs uppercase tracking-widest transition-colors flex items-center justify-center gap-1.5"
              >
                <i data-lucide="plus" class="w-4 h-4"></i> Tambah Gambar URL
              </button>
            </form>
          </div>
        </div>

        <!-- Bahagian 2: Pengeditan Teks Hero & Maklumat Hubungan -->
        <div class="bg-zinc-900 p-6 rounded border border-zinc-800 space-y-6">
          <h3 class="text-white font-bold text-xs uppercase tracking-wider text-zinc-400">
            2. Kemas Kini Teks Hero & Maklumat Hubungan
          </h3>
          <div class="space-y-4">
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-[10px] font-bold text-zinc-500 uppercase tracking-widest mb-1">Tajuk Utama Hero</label>
                <input 
                  id="input-hero-title"
                  type="text"
                  oninput="updateStateField('heroTitle', this.value)"
                  class="w-full p-3 bg-zinc-950 border border-zinc-800 rounded text-xs text-white focus:outline-none focus:border-gold"
                />
              </div>
              <div>
                <label class="block text-[10px] font-bold text-zinc-500 uppercase tracking-widest mb-1">Huraian Ringkas Hero</label>
                <textarea 
                  id="input-hero-subtitle"
                  oninput="updateStateField('heroSubtitle', this.value)"
                  class="w-full p-3 bg-zinc-950 border border-zinc-800 rounded text-xs text-white focus:outline-none focus:border-gold"
                  rows="2"
                ></textarea>
              </div>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-[10px] font-bold text-zinc-500 uppercase tracking-widest mb-1">No. Telefon Hubungi</label>
                <input 
                  id="input-contact-phone"
                  type="text"
                  oninput="updateStateField('contactPhone', this.value)"
                  class="w-full p-3 bg-zinc-950 border border-zinc-800 rounded text-xs text-white focus:outline-none focus:border-gold"
                />
              </div>
              <div>
                <label class="block text-[10px] font-bold text-zinc-500 uppercase tracking-widest mb-1">E-Mel Studio</label>
                <input 
                  id="input-contact-email"
                  type="email"
                  oninput="updateStateField('contactEmail', this.value)"
                  class="w-full p-3 bg-zinc-950 border border-zinc-800 rounded text-xs text-white focus:outline-none focus:border-gold"
                />
              </div>
            </div>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
              <div>
                <label class="block text-[10px] font-bold text-zinc-500 uppercase tracking-widest mb-1">Lokasi Studio / Operasi</label>
                <input 
                  id="input-contact-location"
                  type="text"
                  oninput="updateStateField('contactLocation', this.value)"
                  class="w-full p-3 bg-zinc-950 border border-zinc-800 rounded text-xs text-white focus:outline-none focus:border-gold"
                />
              </div>
              <div>
                <label class="block text-[10px] font-bold text-zinc-500 uppercase tracking-widest mb-1">Pautan Instagram (URL)</label>
                <input 
                  id="input-instagram-url"
                  type="url"
                  oninput="updateStateField('instagramUrl', this.value)"
                  class="w-full p-3 bg-zinc-950 border border-zinc-800 rounded text-xs text-white focus:outline-none focus:border-gold"
                />
              </div>
            </div>

            <div class="bg-zinc-950 p-3 rounded text-[11px] text-gold flex items-start gap-2 border border-gold/10">
              <i data-lucide="info" class="shrink-0 w-3.5 h-3.5 mt-0.5"></i>
              <span>Semua perubahan disimpan serta merta ke dalam pelayar peranti ini secara selamat!</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Bahagian 3: Pengurusan Semua Pakej Harga Secara Langsung -->
      <div class="bg-zinc-900 p-6 rounded border border-zinc-800">
        <div class="flex items-center gap-2 mb-6 pb-2 border-b border-zinc-800">
          <i data-lucide="dollar-sign" class="text-gold w-4 h-4"></i>
          <h3 class="text-white font-bold text-xs uppercase tracking-wider text-zinc-400">
            3. Pengurusan & Suntingan Pakej (Akad Nikah, Same Day, Sanding, Tunang)
          </h3>
        </div>

        <div class="space-y-8" id="admin-packages-container">
          <!-- Diisi secara dinamik oleh JS -->
        </div>
        <p class="text-[10px] text-zinc-500 mt-6 text-center">
          *Semua pindaan harga dan spesifikasi di atas akan dikemas kini secara langsung di bahagian bawah.
        </p>
      </div>

    </div>
  </section>

  <!-- LUXURY PORTFOLIO SECTION -->
  <section id="wedding-gallery" class="py-32 px-6 bg-gradient-to-b from-[#050505] to-[#0c0c0c] scroll-mt-6">
    <div class="max-w-7xl mx-auto space-y-24">
      
      <div class="text-center space-y-4 max-w-2xl mx-auto">
        <span class="text-gold text-[10px] font-bold uppercase tracking-[0.3em]">
          Galeri Karya Seni
        </span>
        <h2 class="font-serif text-3xl sm:text-5xl font-black text-white">Siri Perkahwinan</h2>
        <div class="h-[1px] w-12 bg-gold mx-auto my-6"></div>
        <p class="text-zinc-400 text-xs sm:text-sm tracking-wide leading-relaxed">
          Diterjemahkan menerusi perincian pencahayaan lembut dan persekitaran semula jadi yang menceritakan setiap memori cinta dalam nuansa mewah.
        </p>
      </div>

      <!-- ROW 1: INDOOR WEDDING SERIES -->
      <div class="space-y-6">
        <div class="flex flex-col sm:flex-row sm:items-end justify-between gap-4 border-b border-zinc-900 pb-6">
          <div>
            <h3 class="font-serif text-2xl font-bold text-white tracking-wide">Indoor Wedding Series</h3>
            <p class="text-zinc-500 text-xs tracking-wide">Keindahan butiran hiasan, busana eksklusif, potret dewan, dan momen studio.</p>
          </div>
          
          <!-- Slider Nav Controls -->
          <div class="flex items-center gap-3">
            <button 
              onclick="slideLeft('indoor-slider')"
              class="p-2.5 bg-zinc-950 hover:bg-gold text-zinc-500 hover:text-black rounded-full border border-zinc-900 hover:border-transparent transition-all duration-300"
              aria-label="Slide Kiri"
            >
              <i data-lucide="chevron-left" class="w-4 h-4"></i>
            </button>
            <button 
              onclick="slideRight('indoor-slider')"
              class="p-2.5 bg-zinc-950 hover:bg-gold text-zinc-500 hover:text-black rounded-full border border-zinc-900 hover:border-transparent transition-all duration-300"
              aria-label="Slide Kanan"
            >
              <i data-lucide="chevron-right" class="w-4 h-4"></i>
            </button>
          </div>
        </div>

        <!-- Slider Container -->
        <div 
          id="indoor-slider" 
          class="flex gap-6 overflow-x-auto pb-6 pt-2 scroll-smooth snap-x snap-mandatory no-scrollbar"
        >
          <!-- Gambar diisi secara dinamik -->
        </div>
      </div>

      <!-- ROW 2: OUTDOOR WEDDING SERIES -->
      <div class="space-y-6 pt-8">
        <div class="flex flex-col sm:flex-row sm:items-end justify-between gap-4 border-b border-zinc-900 pb-6">
          <div>
            <h3 class="font-serif text-2xl font-bold text-white tracking-wide">Outdoor Wedding Series</h3>
            <p class="text-zinc-500 text-xs tracking-wide">Momen romantis di alam terbuka dengan pancaran cahaya matahari terbenam.</p>
          </div>
          
          <!-- Slider Nav Controls -->
          <div class="flex items-center gap-3">
            <button 
              onclick="slideLeft('outdoor-slider')"
              class="p-2.5 bg-zinc-950 hover:bg-gold text-zinc-500 hover:text-black rounded-full border border-zinc-900 hover:border-transparent transition-all duration-300"
              aria-label="Slide Kiri"
            >
              <i data-lucide="chevron-left" class="w-4 h-4"></i>
            </button>
            <button 
              onclick="slideRight('outdoor-slider')"
              class="p-2.5 bg-zinc-950 hover:bg-gold text-zinc-500 hover:text-black rounded-full border border-zinc-900 hover:border-transparent transition-all duration-300"
              aria-label="Slide Kanan"
            >
              <i data-lucide="chevron-right" class="w-4 h-4"></i>
            </button>
          </div>
        </div>

        <!-- Slider Container -->
        <div 
          id="outdoor-slider" 
          class="flex gap-6 overflow-x-auto pb-6 pt-2 scroll-smooth snap-x snap-mandatory no-scrollbar"
        >
          <!-- Gambar diisi secara dinamik -->
        </div>
      </div>

    </div>
  </section>

  <!-- PAKEJ KAMI SECTION WITH SLIDERS -->
  <section id="services" class="py-32 px-6 bg-[#030303] border-t border-zinc-900/50">
    <div class="max-w-7xl mx-auto space-y-24">
      
      <div class="text-center space-y-4 max-w-xl mx-auto">
        <span class="text-gold text-[10px] font-bold uppercase tracking-[0.3em]">
          Skim Pelaburan Memori
        </span>
        <h2 class="font-serif text-3xl sm:text-5xl font-black text-white">Butiran Pakej Kreatif</h2>
        <div class="h-[1px] w-12 bg-gold mx-auto my-6"></div>
        <p class="text-zinc-500 text-xs sm:text-sm tracking-widest uppercase">Slide ke tepi untuk melayari setiap pilihan pakej kami.</p>
      </div>

      <div class="space-y-16" id="packages-display-section">
        <!-- Diisi secara dinamik oleh JavaScript mengikut kategori -->
      </div>

      <div class="text-center">
        <p class="text-zinc-500 text-xs">
          * Hubungi wakil kami di bawah untuk perbincangan tempahan dan semakan ketersediaan tarikh.
        </p>
      </div>
    </div>
  </section>

  <!-- MINIMAL LUXURY CONTACT SECTION -->
  <section id="contact" class="py-32 px-6 bg-gradient-to-b from-[#030303] to-black">
    <div class="max-w-4xl mx-auto text-center space-y-16">
      
      <div class="space-y-4">
        <span class="text-gold text-[10px] font-bold uppercase tracking-[0.3em]">
          Perundingan Studio
        </span>
        <h2 class="font-serif text-3xl sm:text-5xl font-black text-white">
          Bincangkan Detik Istimewa Anda
        </h2>
        <div class="h-[1px] w-12 bg-gold mx-auto my-6"></div>
        <p class="text-zinc-400 text-xs sm:text-sm max-w-lg mx-auto leading-relaxed">
          Ketersediaan tarikh pengoperasian kami amat terhad bagi mengekalkan kualiti seni eksklusif setiap pelanggan. Hubungi kami secara peribadi menerusi rangkaian di bawah.
        </p>
      </div>

      <!-- Luxury Contact Network -->
      <div class="grid grid-cols-1 sm:grid-cols-3 gap-8 pt-6 text-center">
        
        <div class="bg-zinc-950 p-8 rounded border border-zinc-900 space-y-4 flex flex-col items-center justify-center hover:border-gold/20 transition-colors duration-350">
          <div class="w-10 h-10 rounded-full border border-zinc-800 flex items-center justify-center text-gold">
            <i data-lucide="phone" class="w-4 h-4"></i>
          </div>
          <h4 class="text-[10px] font-bold text-zinc-500 uppercase tracking-widest">WhatsApp</h4>
          <p id="display-contact-phone" class="text-white font-medium text-xs sm:text-sm"></p>
          <a 
            id="link-whatsapp"
            href="#"
            target="_blank"
            rel="noreferrer"
            class="text-[10px] text-gold hover:underline font-bold uppercase tracking-widest"
          >
            Buka WhatsApp &rarr;
          </a>
        </div>

        <div class="bg-zinc-950 p-8 rounded border border-zinc-900 space-y-4 flex flex-col items-center justify-center hover:border-[#d4af37]/20 transition-colors duration-350">
          <div class="w-10 h-10 rounded-full border border-zinc-800 flex items-center justify-center text-gold">
            <i data-lucide="mail" class="w-4 h-4"></i>
          </div>
          <h4 class="text-[10px] font-bold text-zinc-500 uppercase tracking-widest">E-Mel</h4>
          <p id="display-contact-email" class="text-white font-medium text-xs sm:text-sm"></p>
          <a 
            id="link-email"
            href="#"
            class="text-[10px] text-gold hover:underline font-bold uppercase tracking-widest"
          >
            Hantar E-Mel &rarr;
          </a>
        </div>

        <div class="bg-zinc-950 p-8 rounded border border-zinc-900 space-y-4 flex flex-col items-center justify-center hover:border-[#d4af37]/20 transition-colors duration-350">
          <div class="w-10 h-10 rounded-full border border-zinc-800 flex items-center justify-center text-gold">
            <i data-lucide="map-pin" class="w-4 h-4"></i>
          </div>
          <h4 class="text-[10px] font-bold text-zinc-500 uppercase tracking-widest">Lokasi Studio</h4>
          <p id="display-contact-location" class="text-white font-medium text-xs sm:text-sm"></p>
          <span class="text-[10px] text-zinc-500 font-bold uppercase tracking-wider">Sedia Ke Seluruh MY</span>
        </div>

      </div>

      <div class="pt-6 flex justify-center">
        <a 
          id="link-instagram"
          href="#" 
          target="_blank" 
          rel="noreferrer"
          class="w-12 h-12 rounded-full border border-zinc-900 hover:border-gold text-zinc-400 hover:text-black hover:bg-gold flex items-center justify-center transition-all duration-350"
        >
          <i data-lucide="instagram" class="w-5 h-5"></i>
        </a>
      </div>

    </div>
  </section>

  <!-- LUXURY FOOTER -->
  <footer class="bg-black py-16 px-6 border-t border-zinc-950 text-center text-[10px] text-zinc-600 space-y-6">
    <div class="flex items-center justify-center gap-3">
      <i data-lucide="camera" class="text-gold w-3.5 h-3.5"></i>
      <span class="font-serif font-semibold tracking-[0.25em] text-zinc-400 uppercase">manmy_lens</span>
    </div>
    <p class="tracking-widest uppercase">&copy; <span id="current-year"></span> manmy_lens Photography. Hak Cipta Terpelihara.</p>
    <p class="text-[9px] text-zinc-800 max-w-xs mx-auto leading-relaxed">
      Karya eksklusif yang direka bentuk dengan penuh kehormatan bagi memastikan setiap detik agung anda bernafas selamanya.
    </p>
  </footer>

  <!-- LOGIN MODAL -->
  <div id="login-modal" class="hidden fixed inset-0 z-50 bg-black/90 backdrop-blur-md flex items-center justify-center px-4">
    <div class="bg-[#0d0d0d] p-8 rounded border border-zinc-900 max-w-sm w-full space-y-6 relative shadow-2xl">
      <button onclick="closeLoginModal()" class="absolute top-4 right-4 text-zinc-500 hover:text-white transition-colors">
        <i data-lucide="x" class="w-4 h-4"></i>
      </button>

      <div class="text-center space-y-2">
        <div class="w-12 h-12 bg-gold/10 text-gold rounded-full flex items-center justify-center mx-auto border border-gold/20">
          <i data-lucide="lock" class="w-5 h-5"></i>
        </div>
        <h3 class="font-serif text-lg font-bold text-white tracking-wide">Akses Pentadbiran</h3>
        <p class="text-[11px] text-zinc-500">Sila sahkan kelayakan akses anda untuk menyunting kandungan.</p>
      </div>

      <form onsubmit="handleLoginSubmit(event)" class="space-y-4">
        <div>
          <label class="block text-[10px] font-bold text-gold uppercase tracking-widest mb-1.5">Kata Laluan</label>
          <input 
            id="admin-password-input"
            type="password"
            placeholder="Masukkan kata laluan..."
            class="w-full p-3 bg-zinc-950 border border-zinc-900 rounded text-sm text-white focus:outline-none focus:border-gold"
            required
          />
          <p id="login-error-text" class="hidden text-red-500 text-[11px] mt-1.5 font-bold">Kata laluan salah!</p>
          <p class="text-[10px] text-zinc-500 mt-3 font-semibold tracking-wider text-center">Hanya untuk kegunaan admin</p>
        </div>

        <button 
          type="submit"
          class="w-full py-3 bg-gold hover:bg-amber-400 text-black font-bold rounded text-xs uppercase tracking-widest transition-colors"
        >
          Sahkan Akses
        </button>
      </form>
    </div>
  </div>

  <!-- CONFIRM RESET CUSTOM MODAL (NO WINDOW.CONFIRM) -->
  <div id="confirm-reset-modal" class="hidden fixed inset-0 z-50 bg-black/95 backdrop-blur-md flex items-center justify-center px-4">
    <div class="bg-[#0f0f0d] border border-red-900/40 p-8 rounded max-w-sm w-full space-y-6 text-center shadow-2xl">
      <div class="w-12 h-12 bg-red-950/40 text-red-400 rounded-full flex items-center justify-center mx-auto border border-red-900/30">
        <i data-lucide="refresh-cw" class="w-5 h-5"></i>
      </div>
      <div class="space-y-2">
        <h3 class="font-serif text-lg font-bold text-white uppercase tracking-wider">Set Semula Semua Data?</h3>
        <p class="text-xs text-zinc-400 leading-relaxed">Pakej, pautan, deskripsi, dan gambar yang telah anda tambah akan dipadamkan dan digantikan dengan data asal kilang.</p>
      </div>
      <div class="flex gap-3">
        <button 
          onclick="closeResetConfirmModal()" 
          class="flex-1 py-2.5 bg-zinc-900 hover:bg-zinc-800 text-xs font-bold uppercase tracking-wider rounded border border-zinc-800 transition-colors"
        >
          Batal
        </button>
        <button 
          onclick="confirmResetData()" 
          class="flex-1 py-2.5 bg-red-600 hover:bg-red-700 text-white text-xs font-bold uppercase tracking-wider rounded transition-colors"
        >
          Ya, Set Semula
        </button>
      </div>
    </div>
  </div>

  <!-- JAVASCRIPT STATE & RENDERING ENGINE -->
  <script>
    // Inisialisasi Tarikh Terkini di Footer
    document.getElementById('current-year').textContent = new Date().getFullYear();

    // Nilai Sedia Ada (Default Fallbacks)
    const DEFAULT_INDOOR_IMAGES = [
      { id: 'in1', url: 'https://images.unsplash.com/photo-1519225495810-7512c696505a?auto=format&fit=crop&q=80&w=800' },
      { id: 'in2', url: 'https://images.unsplash.com/photo-1606800052052-a08af7148866?auto=format&fit=crop&q=80&w=800' },
      { id: 'in3', url: 'https://images.unsplash.com/photo-1511285560929-80b456fea0bc?auto=format&fit=crop&q=80&w=800' },
      { id: 'in4', url: 'https://images.unsplash.com/photo-1583939003579-730e3918a45a?auto=format&fit=crop&q=80&w=800' },
      { id: 'in5', url: 'https://images.unsplash.com/photo-1549417229-aa67d3263c09?auto=format&fit=crop&q=80&w=800' },
      { id: 'in6', url: 'https://images.unsplash.com/photo-1515934751635-c81c6bc9a2d8?auto=format&fit=crop&q=80&w=800' },
      { id: 'in7', url: 'https://images.unsplash.com/photo-1522673607200-164d1b6ce486?auto=format&fit=crop&q=80&w=800' },
      { id: 'in8', url: 'https://images.unsplash.com/photo-1532712938310-34cb3982ef74?auto=format&fit=crop&q=80&w=800' },
      { id: 'in9', url: 'https://images.unsplash.com/photo-1502602898657-3e91760cbb34?auto=format&fit=crop&q=80&w=800' },
      { id: 'in10', url: 'https://images.unsplash.com/photo-1519741497674-611481863552?auto=format&fit=crop&q=80&w=800' }
    ];

    const DEFAULT_OUTDOOR_IMAGES = [
      { id: 'out1', url: 'https://images.unsplash.com/photo-1507504038482-76210f54ce65?auto=format&fit=crop&q=80&w=800' },
      { id: 'out2', url: 'https://images.unsplash.com/photo-1465495976277-4387d4b0b4c6?auto=format&fit=crop&q=80&w=800' },
      { id: 'out3', url: 'https://images.unsplash.com/photo-1523438885200-e635ba2c371e?auto=format&fit=crop&q=80&w=800' },
      { id: 'out4', url: 'https://images.unsplash.com/photo-1544005313-94ddf0286df2?auto=format&fit=crop&q=80&w=800' },
      { id: 'out5', url: 'https://images.unsplash.com/photo-1494972308805-463bc619d34e?auto=format&fit=crop&q=80&w=800' },
      { id: 'out6', url: 'https://images.unsplash.com/photo-1510076857177-74700b0934db?auto=format&fit=crop&q=80&w=800' },
      { id: 'out7', url: 'https://images.unsplash.com/photo-1513151233558-d860c5398176?auto=format&fit=crop&q=80&w=800' },
      { id: 'out8', url: 'https://images.unsplash.com/photo-1472653455541-5983387491d2?auto=format&fit=crop&q=80&w=800' },
      { id: 'out9', url: 'https://images.unsplash.com/photo-1482440308425-276ad0f28b19?auto=format&fit=crop&q=80&w=800' },
      { id: 'out10', url: 'https://images.unsplash.com/photo-1519741497674-611481863552?auto=format&fit=crop&q=80&w=800' }
    ];

    const DEFAULT_SERVICES_V5 = [
      { id: 'nikah_1', category: 'akad_nikah', title: 'Akad Nikah Classic', price: 'RM 1,000', features: ['1 Photographer Utama', '3 Jam Liputan Majlis', 'Potret Keluarga & Outdoor Mini', 'Penyimpanan Google Drive', '50 Foto Suntingan Professional'] },
      { id: 'nikah_2', category: 'akad_nikah', title: 'Akad Nikah Exclusive', price: 'RM 1,400', features: ['1 Photographer Utama', '5 Jam Liputan Majlis', 'Potret Keluarga & Outdoor Mini', '1 Premium Photo Album (8x12)', 'Pendrive Eksklusif manmy_lens'] },

      { id: 'sameday_1', category: 'nikah_sanding', title: 'Same Day Essential', price: 'RM 1,800', features: ['1 Photographer Utama', '6 Jam Liputan Majlis', 'Potret Keluarga & Sesi Outdoor', 'Penyimpanan Google Drive', '100 Foto Suntingan Professional'] },
      { id: 'sameday_2', category: 'nikah_sanding', title: 'Same Day Signature', price: 'RM 2,200', features: ['2 Photographers Utama', '8 Jam Liputan Majlis', 'Sesi Outdoor Nikah & Sanding', '1 Premium Photo Album (8x12)', 'Pendrive Eksklusif manmy_lens'] },
      { id: 'sameday_3', category: 'nikah_sanding', title: 'Same Day Majestic', price: 'RM 2,800', features: ['2 Photographers Utama', '10 Jam Liputan Sepenuh Hari', 'Sesi Outdoor Eksklusif', '2 Premium Photo Albums (8x12 & 10x15)', 'Eksklusif Wooden Photo Box'] },

      { id: 'sanding_1', category: 'sanding_bertandang', title: 'Sanding Basic', price: 'RM 1,200', features: ['1 Photographer Utama', '4 Jam Liputan Persandingan', 'Sesi Outdoor Mini', 'Penyimpanan Google Drive', '60 Foto Suntingan Professional'] },
      { id: 'sanding_2', category: 'sanding_bertandang', title: 'Sanding Signature', price: 'RM 1,500', features: ['1 Photographer Utama', '5 Jam Liputan Persandingan', 'Sesi Outdoor Persandingan', '1 Premium Photo Album (8x12)', 'Pendrive Eksklusif manmy_lens'] },
      { id: 'sanding_3', category: 'sanding_bertandang', title: 'Sanding Premium', price: 'RM 1,900', features: ['2 Photographers Utama', '6 Jam Liputan Persandingan', 'Sesi Outdoor Istimewa', '1 Premium Photo Album (8x12)', 'Custom Photo Frame (12x18)'] },

      { id: 'tunang_1', category: 'tunang', title: 'Tunang Signature', price: 'RM 850', features: ['1 Photographer', '3 Jam Liputan Majlis', 'Sesi Outdoor Mini Bertunang', '1 Premium Pocket Album', '50 Foto Suntingan Professional'] }
    ];

    // Global State
    let state = {
      heroTitle: localStorage.getItem('manmy_hero_title_v5_final') || 'Merakam Detik Sekali Seumur Hidup',
      heroSubtitle: localStorage.getItem('manmy_hero_sub_v5_final') || 'Fotografi perkahwinan berpiawaian tinggi dengan sentuhan editorial yang mengabadikan emosi dan cinta abadi anda di Kuala Kedah dan seluruh Malaysia.',
      contactPhone: localStorage.getItem('manmy_phone_v5_final') || '+60 11-2345 6789',
      contactEmail: localStorage.getItem('manmy_email_v5_final') || 'hello.manmylens@gmail.com',
      contactLocation: localStorage.getItem('manmy_location_v5_final') || 'Kuala Kedah, Kedah',
      instagramUrl: localStorage.getItem('manmy_instagram_v5_final') || 'https://instagram.com',
      indoorImages: JSON.parse(localStorage.getItem('manmy_indoor_images_v5_final')) || DEFAULT_INDOOR_IMAGES,
      outdoorImages: JSON.parse(localStorage.getItem('manmy_outdoor_images_v5_final')) || DEFAULT_OUTDOOR_IMAGES,
      services: JSON.parse(localStorage.getItem('manmy_services_v5_final')) || DEFAULT_SERVICES_V5,
      isAdminMode: false,
      uploadSource: 'gallery'
    };

    // Fungsi Papar Toast Notification
    function showToast(message) {
      const toast = document.getElementById('toast-notification');
      document.getElementById('toast-text').innerText = message;
      toast.classList.remove('translate-y-20', 'opacity-0', 'pointer-events-none');
      toast.classList.add('translate-y-0', 'opacity-100');
      
      setTimeout(() => {
        toast.classList.remove('translate-y-0', 'opacity-100');
        toast.classList.add('translate-y-20', 'opacity-0', 'pointer-events-none');
      }, 3000);
    }

    // Menguruskan Penyimpanan Ke LocalStorage
    function syncToStorage() {
      localStorage.setItem('manmy_hero_title_v5_final', state.heroTitle);
      localStorage.setItem('manmy_hero_sub_v5_final', state.heroSubtitle);
      localStorage.setItem('manmy_phone_v5_final', state.contactPhone);
      localStorage.setItem('manmy_email_v5_final', state.contactEmail);
      localStorage.setItem('manmy_location_v5_final', state.contactLocation);
      localStorage.setItem('manmy_instagram_v5_final', state.instagramUrl);
      localStorage.setItem('manmy_indoor_images_v5_final', JSON.stringify(state.indoorImages));
      localStorage.setItem('manmy_outdoor_images_v5_final', JSON.stringify(state.outdoorImages));
      localStorage.setItem('manmy_services_v5_final', JSON.stringify(state.services));
    }

    // Memuat Naik Gambar Melalui Fail Tempatan
    function handleLocalFile(event) {
      const file = event.target.files[0];
      if (!file) return;

      if (file.size > 2 * 1024 * 1024) {
        showToast("Ralat: Fail melebihi had saiz 2MB.");
        return;
      }

      const reader = new FileReader();
      reader.onloadend = () => {
        const base64String = reader.result;
        const newImg = {
          id: 'img_' + Date.now(),
          url: base64String
        };

        const target = document.getElementById('admin-img-target').value;
        if (target === 'indoor') {
          state.indoorImages.push(newImg);
        } else {
          state.outdoorImages.push(newImg);
        }
        
        syncToStorage();
        renderGallery();
        showToast(`Gambar berjaya ditambah ke ${target}!`);
        event.target.value = null; // reset input
      };
      reader.readAsDataURL(file);
    }

    // Tambah Gambar Melalui URL Pautan Web
    function handleAddImageViaUrl(e) {
      e.preventDefault();
      const urlInput = document.getElementById('admin-img-url-input');
      const url = urlInput.value.trim();
      if (!url) return;

      const newImg = {
        id: 'img_' + Date.now(),
        url: url
      };

      const target = document.getElementById('admin-img-target').value;
      if (target === 'indoor') {
        state.indoorImages.push(newImg);
      } else {
        state.outdoorImages.push(newImg);
      }

      syncToStorage();
      renderGallery();
      showToast(`Gambar pautan berjaya ditambah ke ${target}!`);
      urlInput.value = '';
    }

    // Padam Gambar Dari Galeri
    function deleteImage(id, type) {
      if (type === 'indoor') {
        state.indoorImages = state.indoorImages.filter(img => img.id !== id);
      } else {
        state.outdoorImages = state.outdoorImages.filter(img => img.id !== id);
      }
      syncToStorage();
      renderGallery();
      showToast('Gambar telah dipadam.');
    }

    // Kemas kini State Secara Langsung (Hero & Hubungan)
    function updateStateField(field, value) {
      state[field] = value;
      syncToStorage();
      
      // Update element tertentu yang terjejas terus untuk prestasi pantas
      if (field === 'heroSubtitle') {
        document.getElementById('display-hero-subtitle').innerText = value;
      } else if (field === 'contactPhone') {
        document.getElementById('display-contact-phone').innerText = value;
        updateWhatsAppLink();
      } else if (field === 'contactEmail') {
        document.getElementById('display-contact-email').innerText = value;
        document.getElementById('link-email').href = `mailto:${value}`;
      } else if (field === 'contactLocation') {
        document.getElementById('display-contact-location').innerText = value;
      } else if (field === 'instagramUrl') {
        document.getElementById('link-instagram').href = value;
      }
    }

    // Kemas kini Pakej Kreatif Secara Langsung Dari Admin
    function updatePackageField(id, field, value) {
      state.services = state.services.map(srv => {
        if (srv.id === id) {
          if (field === 'features') {
            return { ...srv, features: value.split('\n') };
          }
          return { ...srv, [field]: value };
        }
        return srv;
      });
      syncToStorage();
      renderServices();
    }

    // Navigasi Slider Gelongsor
    function slideLeft(id) {
      const el = document.getElementById(id);
      if (el) el.scrollLeft -= 400;
    }

    function slideRight(id) {
      const el = document.getElementById(id);
      if (el) el.scrollLeft += 400;
    }

    // Menyediakan Pautan WhatsApp Berpandukan Nombor Dinamik
    function updateWhatsAppLink() {
      const phoneDigits = state.contactPhone.replace(/[^0-9]/g, '');
      const link = `https://wa.me/${phoneDigits ? phoneDigits : '601123456789'}?text=Hi%20manmy_lens!%20Saya%20berhasrat%20untuk%20menyemak%20slot%20dan%20pakej%20fotografi%20wedding%20saya.`;
      document.getElementById('link-whatsapp').href = link;
    }

    // Menukar kaedah upload imej dalam dashboard
    function setUploadSource(source) {
      state.uploadSource = source;
      const galleryBtn = document.getElementById('src-gallery-btn');
      const urlBtn = document.getElementById('src-url-btn');
      const galleryUploader = document.getElementById('source-gallery-uploader');
      const urlUploader = document.getElementById('source-url-uploader');

      if (source === 'gallery') {
        galleryBtn.className = "px-3 py-1 rounded transition-all bg-gold text-black font-bold";
        urlBtn.className = "px-3 py-1 rounded transition-all text-zinc-400";
        galleryUploader.classList.remove('hidden');
        urlUploader.classList.add('hidden');
      } else {
        urlBtn.className = "px-3 py-1 rounded transition-all bg-gold text-black font-bold";
        galleryBtn.className = "px-3 py-1 rounded transition-all text-zinc-400";
        urlUploader.classList.remove('hidden');
        galleryUploader.classList.add('hidden');
      }
    }

    // Menguruskan Modal Login
    function toggleAdminAction() {
      if (state.isAdminMode) {
        // Log out terus jika sudah aktif
        state.isAdminMode = false;
        document.getElementById('admin-dashboard-section').classList.add('hidden');
        const adminBtn = document.getElementById('admin-action-btn');
        adminBtn.innerHTML = `<i data-lucide="lock" class="w-3 h-3"></i> <span>Admin</span>`;
        adminBtn.className = "flex items-center gap-1.5 bg-white/5 hover:bg-gold text-zinc-300 hover:text-black px-4 py-2 rounded border border-zinc-800 hover:border-transparent text-[10px] font-bold tracking-widest uppercase transition-all duration-350";
        lucide.createIcons();
        renderGallery(); // update to hide trash icons
        showToast('Telah log keluar dari mod admin.');
      } else {
        // Papar modal login
        document.getElementById('login-modal').classList.remove('hidden');
        document.getElementById('admin-password-input').focus();
      }
    }

    function closeLoginModal() {
      document.getElementById('login-modal').classList.add('hidden');
      document.getElementById('admin-password-input').value = '';
      document.getElementById('login-error-text').classList.add('hidden');
    }

    function handleLoginSubmit(e) {
      e.preventDefault();
      const passInput = document.getElementById('admin-password-input');
      const errorText = document.getElementById('login-error-text');

      if (passInput.value === '041006') {
        state.isAdminMode = true;
        closeLoginModal();
        
        // Papar Dashboard
        document.getElementById('admin-dashboard-section').classList.remove('hidden');
        
        // Kemaskini Butang Navigasi Atas
        const adminBtn = document.getElementById('admin-action-btn');
        adminBtn.innerHTML = `<i data-lucide="log-out" class="w-3 h-3"></i> <span>Log Keluar</span>`;
        adminBtn.className = "flex items-center gap-1.5 bg-red-950/45 hover:bg-red-900/60 text-red-200 px-4 py-2 rounded border border-red-900/30 text-[10px] font-bold tracking-widest uppercase transition-all";
        lucide.createIcons();

        // Populate Dashboard Inputs
        document.getElementById('input-hero-title').value = state.heroTitle;
        document.getElementById('input-hero-subtitle').value = state.heroSubtitle;
        document.getElementById('input-contact-phone').value = state.contactPhone;
        document.getElementById('input-contact-email').value = state.contactEmail;
        document.getElementById('input-contact-location').value = state.contactLocation;
        document.getElementById('input-instagram-url').value = state.instagramUrl;

        // Render Dashboard Package Editors
        renderAdminPackagesEditor();
        renderGallery(); // update to show trash icons
        showToast('Akses Pentadbir Disahkan!');
      } else {
        errorText.classList.remove('hidden');
        passInput.value = '';
        passInput.focus();
      }
    }

    // Pengurusan Modal Reset Custom
    function openResetConfirmModal() {
      document.getElementById('confirm-reset-modal').classList.remove('hidden');
    }

    function closeResetConfirmModal() {
      document.getElementById('confirm-reset-modal').classList.add('hidden');
    }

    function confirmResetData() {
      closeResetConfirmModal();
      
      // Kembalikan ke tetapan asal kilang
      state.heroTitle = 'Merakam Detik Sekali Seumur Hidup';
      state.heroSubtitle = 'Fotografi perkahwinan berpiawaian tinggi dengan sentuhan editorial yang mengabadikan emosi dan cinta abadi anda di Kuala Kedah dan seluruh Malaysia.';
      state.contactPhone = '+60 11-2345 6789';
      state.contactEmail = 'hello.manmylens@gmail.com';
      state.contactLocation = 'Kuala Kedah, Kedah';
      state.instagramUrl = 'https://instagram.com';
      state.indoorImages = [...DEFAULT_INDOOR_IMAGES];
      state.outdoorImages = [...DEFAULT_OUTDOOR_IMAGES];
      state.services = [...DEFAULT_SERVICES_V5];

      syncToStorage();
      
      // Populate Semula Semua Input & Render Semua Komponen
      document.getElementById('input-hero-title').value = state.heroTitle;
      document.getElementById('input-hero-subtitle').value = state.heroSubtitle;
      document.getElementById('input-contact-phone').value = state.contactPhone;
      document.getElementById('input-contact-email').value = state.contactEmail;
      document.getElementById('input-contact-location').value = state.contactLocation;
      document.getElementById('input-instagram-url').value = state.instagramUrl;

      renderAll();
      showToast('Semua data berjaya diset semula.');
    }

    // ==========================================
    // SEKSYEN RENDERING DINAMIK (UI GENERATION)
    // ==========================================

    function renderAll() {
      // 1. Render Hero Section
      document.getElementById('display-hero-subtitle').innerText = state.heroSubtitle;

      // 2. Render Gallery
      renderGallery();

      // 3. Render Services (Pakej Kami)
      renderServices();

      // 4. Render Maklumat Hubungan
      document.getElementById('display-contact-phone').innerText = state.contactPhone;
      document.getElementById('display-contact-email').innerText = state.contactEmail;
      document.getElementById('display-contact-location').innerText = state.contactLocation;
      document.getElementById('link-email').href = `mailto:${state.contactEmail}`;
      document.getElementById('link-instagram').href = state.instagramUrl;
      updateWhatsAppLink();

      // 5. Render Admin Packages Editor (Jika Mod Admin Aktif)
      if (state.isAdminMode) {
        renderAdminPackagesEditor();
      }

      // Re-trigger Lucide Icons
      lucide.createIcons();
    }

    // Render Gambar Galeri (Indoor & Outdoor)
    function renderGallery() {
      const indoorContainer = document.getElementById('indoor-slider');
      const outdoorContainer = document.getElementById('outdoor-slider');

      // Indoor Gallery Render
      if (state.indoorImages.length === 0) {
        indoorContainer.innerHTML = `
          <div class="w-full text-center py-16 bg-zinc-950/40 rounded border border-dashed border-zinc-900 text-zinc-600 text-xs">
            Galeri indoor kosong. Log masuk admin untuk menambah gambar.
          </div>
        `;
      } else {
        indoorContainer.innerHTML = state.indoorImages.map((img, index) => `
          <div class="relative group flex-shrink-0 w-[80vw] sm:w-[460px] h-[320px] sm:h-[380px] rounded overflow-hidden snap-center border border-zinc-900/60 hover:border-gold/30 transition-all duration-500 shadow-2xl">
            <img 
              src="${img.url}" 
              alt="Indoor Wedding ${index + 1}" 
              class="w-full h-full object-cover filter brightness-95 group-hover:scale-102 transition-all duration-700 ease-out"
              onerror="this.src='https://images.unsplash.com/photo-1519741497674-611481863552?auto=format&fit=crop&q=80&w=800'"
            />
            
            <div class="absolute top-4 left-4 bg-black/80 backdrop-blur-md px-3 py-1 rounded text-[10px] font-bold text-gold tracking-wider border border-zinc-800">
              INDOOR ${index + 1} / ${state.indoorImages.length}
            </div>

            ${state.isAdminMode ? `
              <button 
                onclick="deleteImage('${img.id}', 'indoor')"
                class="absolute top-4 right-4 bg-red-950 hover:bg-red-800 text-red-200 p-2 rounded transition-colors z-20 border border-red-900/40"
              >
                <i data-lucide="trash-2" class="w-3.5 h-3.5"></i>
              </button>
            ` : ''}

            <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end p-6">
              <p class="text-gold text-[10px] font-bold tracking-[0.15em] uppercase">
                manmy_lens &copy; High-End Editorial
              </p>
            </div>
          </div>
        `).join('');
      }

      // Outdoor Gallery Render
      if (state.outdoorImages.length === 0) {
        outdoorContainer.innerHTML = `
          <div class="w-full text-center py-16 bg-zinc-950/40 rounded border border-dashed border-zinc-900 text-zinc-600 text-xs">
            Galeri outdoor kosong. Log masuk admin untuk menambah gambar.
          </div>
        `;
      } else {
        outdoorContainer.innerHTML = state.outdoorImages.map((img, index) => `
          <div class="relative group flex-shrink-0 w-[80vw] sm:w-[460px] h-[320px] sm:h-[380px] rounded overflow-hidden snap-center border border-zinc-900/60 hover:border-gold/30 transition-all duration-500 shadow-2xl">
            <img 
              src="${img.url}" 
              alt="Outdoor Wedding ${index + 1}" 
              class="w-full h-full object-cover filter brightness-95 group-hover:scale-102 transition-all duration-700 ease-out"
              onerror="this.src='https://images.unsplash.com/photo-1519741497674-611481863552?auto=format&fit=crop&q=80&w=800'"
            />
            
            <div class="absolute top-4 left-4 bg-black/80 backdrop-blur-md px-3 py-1 rounded text-[10px] font-bold text-gold tracking-wider border border-zinc-800">
              OUTDOOR ${index + 1} / ${state.outdoorImages.length}
            </div>

            ${state.isAdminMode ? `
              <button 
                onclick="deleteImage('${img.id}', 'outdoor')"
                class="absolute top-4 right-4 bg-red-950 hover:bg-red-800 text-red-200 p-2 rounded transition-colors z-20 border border-red-900/40"
              >
                <i data-lucide="trash-2" class="w-3.5 h-3.5"></i>
              </button>
            ` : ''}

            <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end p-6">
              <p class="text-gold text-[10px] font-bold tracking-[0.15em] uppercase">
                manmy_lens &copy; High-End Editorial
              </p>
            </div>
          </div>
        `).join('');
      }

      lucide.createIcons();
    }

    // Render Pakej Jualan Mengikut Kategori & Slider
    function renderServices() {
      const container = document.getElementById('packages-display-section');
      
      const categories = [
        { key: 'akad_nikah', label: 'Akad Nikah', num: '01', sliderId: 'nikah-services-slider' },
        { key: 'nikah_sanding', label: 'Nikah & Sanding (Same Day)', num: '02', sliderId: 'nikahsanding-services-slider' },
        { key: 'sanding_bertandang', label: 'Sanding @ Bertandang', num: '03', sliderId: 'sanding-services-slider' },
        { key: 'tunang', label: 'Tunang', num: '04', sliderId: 'tunang-services-slider' }
      ];

      container.innerHTML = categories.map(cat => {
        const filtered = state.services.filter(s => s.category === cat.key);
        
        return `
          <div class="space-y-6">
            <div class="flex items-center justify-between border-b border-zinc-900 pb-4">
              <div class="flex items-center gap-3">
                <span class="text-gold text-xs font-black uppercase tracking-widest bg-zinc-900 px-3 py-1 rounded border border-zinc-800">${cat.num}</span>
                <h3 class="font-serif text-xl sm:text-2xl font-bold text-white tracking-wide">${cat.label}</h3>
              </div>
              <div class="flex items-center gap-2">
                <button 
                  onclick="slideLeft('${cat.sliderId}')"
                  class="p-2 bg-zinc-900 hover:bg-gold text-zinc-400 hover:text-black rounded-full border border-zinc-800 transition-all duration-300"
                >
                  <i data-lucide="chevron-left" class="w-3.5 h-3.5"></i>
                </button>
                <button 
                  onclick="slideRight('${cat.sliderId}')"
                  class="p-2 bg-zinc-900 hover:bg-gold text-zinc-400 hover:text-black rounded-full border border-zinc-800 transition-all duration-300"
                >
                  <i data-lucide="chevron-right" class="w-3.5 h-3.5"></i>
                </button>
              </div>
            </div>

            <!-- Slider Pakej -->
            <div 
              id="${cat.sliderId}" 
              class="flex gap-6 overflow-x-auto pb-4 pt-2 scroll-smooth snap-x snap-mandatory no-scrollbar"
            >
              ${filtered.map(srv => `
                <div class="bg-[#080808] p-8 rounded border border-zinc-900 hover:border-gold/20 transition-all duration-500 relative flex flex-col justify-between group flex-shrink-0 w-[85vw] sm:w-[380px] snap-center">
                  <div class="space-y-6">
                    <div>
                      <h4 class="font-serif text-lg font-bold text-white group-hover:text-gold transition-colors duration-300">
                        ${srv.title}
                      </h4>
                      <div class="mt-3 flex items-baseline gap-1">
                        <span class="text-xl font-serif font-semibold text-gold">${srv.price}</span>
                      </div>
                    </div>
                    <ul class="space-y-3 border-t border-zinc-900 pt-6">
                      ${srv.features.map(feat => `
                        <li class="flex items-start gap-3 text-xs text-zinc-400 leading-relaxed">
                          <i data-lucide="check-circle-2" class="text-gold shrink-0 mt-0.5 w-3.5 h-3.5"></i>
                          <span>${feat}</span>
                        </li>
                      `).join('')}
                    </ul>
                  </div>
                </div>
              `).join('')}
            </div>
          </div>
        `;
      }).join('');

      lucide.createIcons();
    }

    // Render Editor Pakej Dinamik Pada Dashboard Admin
    function renderAdminPackagesEditor() {
      const container = document.getElementById('admin-packages-container');
      const categories = [
        { key: 'akad_nikah', label: 'Akad Nikah' },
        { key: 'nikah_sanding', label: 'Nikah & Sanding (Same Day)' },
        { key: 'sanding_bertandang', label: 'Sanding @ Bertandang' },
        { key: 'tunang', label: 'Tunang' }
      ];

      container.innerHTML = categories.map(cat => {
        const filtered = state.services.filter(s => s.category === cat.key);
        
        return `
          <div class="space-y-4">
            <h4 class="text-gold text-xs font-bold uppercase tracking-wider border-l-2 border-gold pl-2">${cat.label}</h4>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
              ${filtered.map(srv => `
                <div class="bg-zinc-950 p-4 rounded border border-zinc-800 space-y-3 text-xs">
                  <div class="font-bold text-zinc-400">ID: ${srv.id}</div>
                  <div>
                    <label class="block text-[9px] font-bold text-zinc-500 uppercase tracking-wider mb-1">Nama Pakej</label>
                    <input 
                      type="text" 
                      value="${srv.title}" 
                      oninput="updatePackageField('${srv.id}', 'title', this.value)" 
                      class="w-full p-2 bg-zinc-900 border border-zinc-800 rounded text-white focus:border-gold focus:outline-none" 
                    />
                  </div>
                  <div>
                    <label class="block text-[9px] font-bold text-zinc-500 uppercase tracking-wider mb-1">Harga (RM)</label>
                    <input 
                      type="text" 
                      value="${srv.price}" 
                      oninput="updatePackageField('${srv.id}', 'price', this.value)" 
                      class="w-full p-2 bg-zinc-900 border border-zinc-800 rounded text-gold font-bold focus:border-gold focus:outline-none" 
                    />
                  </div>
                  <div>
                    <label class="block text-[9px] font-bold text-zinc-500 uppercase tracking-wider mb-1">Kelebihan / Spesifikasi (Satu baris, satu kelebihan)</label>
                    <textarea 
                      oninput="updatePackageField('${srv.id}', 'features', this.value)" 
                      class="w-full p-2 bg-zinc-900 border border-zinc-800 rounded text-white focus:border-gold focus:outline-none h-24 font-sans" 
                    >${srv.features.join('\n')}</textarea>
                  </div>
                </div>
              `).join('')}
            </div>
          </div>
        `;
      }).join('');
    }

    // Cetusan Mula Laman Web
    window.onload = function() {
      renderAll();
    };
  </script>
</body>
</html>
