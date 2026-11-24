<html lang="en" class="scroll-smooth">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>PineappleSMP | Lifesteal SMP</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Press+Start+2P&family=Silkscreen:wght@400;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
  <style>
    :root {
      --bg-obsidian: #0E0B04;
      --panel-dark: #191306;
      --panel-light: #261D09;
      --gold-primary: #FFD60A;
      --gold-amber: #F59E0B;
      --gold-border: rgba(255, 214, 10, 0.45);
    }

    * {
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
      background-color: #0E0B04;
      background-image:
        radial-gradient(circle at 18% 12%, rgba(255, 214, 10, 0.14) 0%, transparent 42%),
        radial-gradient(circle at 84% 24%, rgba(245, 158, 11, 0.12) 0%, transparent 45%),
        radial-gradient(circle at 50% 85%, rgba(250, 204, 21, 0.08) 0%, transparent 50%),
        linear-gradient(180deg, #0E0B04 0%, #151005 50%, #0B0802 100%);
      color: #FEF9C3;
      overflow-x: hidden;
      margin: 0;
    }

    .font-pixel {
      font-family: 'Press Start 2P', monospace;
      line-height: 1.45;
    }

    .font-silk {
      font-family: 'Silkscreen', monospace;
    }

    /* Minecraft 3D Beveled Golden Block Panel */
    .mc-panel {
      background: linear-gradient(180deg, rgba(38, 29, 9, 0.94) 0%, rgba(21, 16, 5, 0.97) 100%);
      border: 2px solid var(--gold-border);
      box-shadow:
        inset 0 2px 0 rgba(255, 238, 136, 0.22),
        inset 0 -3px 0 rgba(0, 0, 0, 0.65),
        0 10px 28px rgba(0, 0, 0, 0.55);
      transition: transform 0.2s ease, border-color 0.2s ease, box-shadow 0.2s ease;
    }

    .mc-panel:hover {
      border-color: rgba(255, 214, 10, 0.85);
      box-shadow:
        inset 0 2px 0 rgba(255, 238, 136, 0.32),
        inset 0 -3px 0 rgba(0, 0, 0, 0.7),
        0 14px 34px rgba(255, 214, 10, 0.14);
    }

    /* Tactile 3D Minecraft Button */
    .mc-btn {
      border-top: 2px solid rgba(255, 255, 255, 0.45);
      border-left: 2px solid rgba(255, 255, 255, 0.3);
      border-right: 2px solid rgba(0, 0, 0, 0.45);
      border-bottom: 4px solid rgba(0, 0, 0, 0.6);
      transition: transform 0.12s ease, filter 0.15s ease;
      cursor: pointer;
    }

    .mc-btn:hover {
      filter: brightness(1.07);
    }

    .mc-btn:active {
      transform: translateY(2px);
      border-bottom-width: 2px;
    }

    /* Golden Pineapple Pixel Block Divider */
    .mc-grass-divider {
      height: 10px;
      width: 100%;
      background-image: repeating-linear-gradient(
        90deg,
        #FFD60A 0px,
        #FFD60A 16px,
        #F59E0B 16px,
        #F59E0B 32px,
        #CA8A04 32px,
        #CA8A04 48px
      );
      border-top: 2px solid #FEF08A;
      border-bottom: 2px solid #422006;
      opacity: 0.85;
    }

    /* Top News Ticker Marquee */
    @keyframes tickerScroll {
      0% { transform: translateX(0); }
      100% { transform: translateX(-50%); }
    }

    .animate-ticker {
      display: flex;
      width: max-content;
      animation: tickerScroll 34s linear infinite;
    }

    .animate-ticker:hover {
      animation-play-state: paused;
    }

    /* Simple & Smooth Floating Watermark Text Motion */
    @keyframes floatWatermarkText {
      0%, 100% {
        transform: translateY(0px) scale(1);
        text-shadow: 0 0 14px rgba(255, 214, 10, 0.35);
      }
      50% {
        transform: translateY(-5px) scale(1.02);
        text-shadow: 0 4px 24px rgba(255, 214, 10, 0.7);
      }
    }

    .animate-watermark-text {
      display: inline-block;
      animation: floatWatermarkText 3.4s ease-in-out infinite;
    }

    /* Gentle Float for Mascot */
    @keyframes floatMascot {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-7px); }
    }

    .mascot-float {
      animation: floatMascot 3.8s ease-in-out infinite;
    }

    /* Floating Golden Sparkles */
    @keyframes sparkleFloat {
      0%, 100% { opacity: 0.25; transform: translateY(0) scale(1); }
      50% { opacity: 0.95; transform: translateY(-10px) scale(1.2); }
    }

    .sparkle-dot {
      animation: sparkleFloat 4s ease-in-out infinite;
    }

    /* Skyblock Mode Accent Overrides */
    body.mode-skyblock {
      background-image:
        radial-gradient(circle at 20% 10%, rgba(56, 189, 248, 0.16) 0%, transparent 45%),
        radial-gradient(circle at 82% 22%, rgba(255, 214, 10, 0.15) 0%, transparent 46%),
        radial-gradient(circle at 50% 85%, rgba(52, 211, 153, 0.08) 0%, transparent 50%),
        linear-gradient(180deg, #07111A 0%, #0D161E 50%, #080B0E 100%);
    }

    /* Custom Scrollbar */
    .custom-scroll::-webkit-scrollbar {
      width: 6px;
      height: 6px;
    }
    .custom-scroll::-webkit-scrollbar-track {
      background: #0D0A03;
    }
    .custom-scroll::-webkit-scrollbar-thumb {
      background: #CA8A04;
      border-radius: 9999px;
    }
  </style>
</head>
<body class="min-h-screen flex flex-col selection:bg-yellow-400 selection:text-stone-950">

  <!-- TOP SCROLLING NEWS TICKER -->
  <div class="bg-gradient-to-r from-yellow-400 via-amber-400 to-yellow-300 text-stone-950 border-b-2 border-amber-700 overflow-hidden py-1.5 text-[11px] sm:text-xs font-black uppercase tracking-wider select-none">
    <div id="top-ticker-track" class="animate-ticker">
      <div class="flex items-center gap-8 px-4">
        <span><i class="fa-solid fa-crown mr-1.5"></i>PINEAPPLE SMP — SEASON 1 LAUNCHED</span>
        <span>&bull;</span>
        <span><i class="fa-solid fa-cloud mr-1.5"></i>NEW: PINEAPPLE SKYBLOCK (JAVA ONLY): pineappleskyblock.playgg.pro:25127</span>
        <span>&bull;</span>
        <span><i class="fa-solid fa-bolt mr-1.5"></i>UPCOMING PVP EVENT ON 29 NOVEMBER 2026</span>
        <span>&bull;</span>
        <span><i class="fa-solid fa-desktop mr-1.5"></i>LIFESTEAL JAVA: basic.vitalcloud.in:19126</span>
        <span>&bull;</span>
        <span><i class="fa-solid fa-mobile-screen mr-1.5"></i>LIFESTEAL BEDROCK: basic.vitalcloud.in &bull; PORT: 19149</span>
        <span>&bull;</span>
        <span><i class="fa-brands fa-discord mr-1.5"></i>DISCORD: discord.gg/Vp9Ss592cq</span>
        <span>&bull;</span>
      </div>
      <div class="flex items-center gap-8 px-4" aria-hidden="true">
        <span><i class="fa-solid fa-crown mr-1.5"></i>PINEAPPLE SMP — SEASON 1 LAUNCHED</span>
        <span>&bull;</span>
        <span><i class="fa-solid fa-cloud mr-1.5"></i>NEW: PINEAPPLE SKYBLOCK (JAVA ONLY): pineappleskyblock.playgg.pro:25127</span>
        <span>&bull;</span>
        <span><i class="fa-solid fa-bolt mr-1.5"></i>UPCOMING PVP EVENT ON 29 NOVEMBER 2026</span>
        <span>&bull;</span>
        <span><i class="fa-solid fa-desktop mr-1.5"></i>LIFESTEAL JAVA: basic.vitalcloud.in:19126</span>
        <span>&bull;</span>
        <span><i class="fa-solid fa-mobile-screen mr-1.5"></i>LIFESTEAL BEDROCK: basic.vitalcloud.in &bull; PORT: 19149</span>
        <span>&bull;</span>
        <span><i class="fa-brands fa-discord mr-1.5"></i>DISCORD: discord.gg/Vp9Ss592cq</span>
        <span>&bull;</span>
      </div>
    </div>
  </div>

  <!-- STICKY NAVIGATION BAR -->
  <header class="sticky top-0 z-40 bg-[#120D04]/95 backdrop-blur-md border-b-2 border-yellow-500/40 shadow-xl">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 h-16 sm:h-[72px] flex items-center justify-between gap-2 sm:gap-3">
      
      <!-- Brand Logo: Box Pineapple Voxel-Emblem with Z-Black Sunglasses -->
      <a href="#" class="flex items-center gap-2.5 sm:gap-3 group shrink-0">
        <div class="w-10 h-10 sm:w-12 sm:h-12 rounded-xl bg-gradient-to-br from-yellow-300 via-amber-400 to-amber-600 p-1 border-2 border-yellow-200 shadow-[0_0_18px_rgba(255,214,10,0.45)] group-hover:scale-105 transition-transform">
          <svg viewBox="0 0 64 64" class="w-full h-full" xmlns="http://www.w3.org/2000/svg" aria-label="PineappleSMP Emblem Logo">
            <polygon points="32,2 58,12 54,48 32,62 10,48 6,12" fill="#1C1404" stroke="#FDE047" stroke-width="2.5" stroke-linejoin="round"/>
            <polygon points="32,3 25,17 39,17" fill="#15803D"/>
            <polygon points="32,4 28,17 36,17" fill="#22C55E"/>
            <polygon points="18,8 17,19 28,17" fill="#16A34A"/>
            <polygon points="46,8 36,17 47,19" fill="#15803D"/>
            <rect x="16" y="17" width="32" height="36" rx="4" fill="#FACC15" stroke="#451A03" stroke-width="2.2"/>
            <rect x="41" y="18" width="6" height="34" rx="2" fill="#B45309" opacity="0.5"/>
            <rect x="18" y="19" width="23" height="5" rx="2" fill="#FEF08A" opacity="0.7"/>
            <path d="M23 18 L23 52 M31 18 L31 52 M39 18 L39 52 M17 37 L47 37 M17 45 L47 45" stroke="#92400E" stroke-width="1.3" opacity="0.5"/>
            <rect x="12" y="25" width="4" height="3" fill="#09090B"/>
            <rect x="48" y="25" width="4" height="3" fill="#09090B"/>
            <polygon points="14,23 30,24.5 29,34 15.5,33" fill="#09090B" stroke="#000000" stroke-width="1.8" stroke-linejoin="round"/>
            <polygon points="34,24.5 50,23 48.5,33 35,34" fill="#09090B" stroke="#000000" stroke-width="1.8" stroke-linejoin="round"/>
            <rect x="29.5" y="24.5" width="5" height="2.8" fill="#09090B"/>
            <polygon points="17,25 21.5,25 18.5,32 15.5,32" fill="#FFFFFF" opacity="0.45"/>
            <polygon points="37,25 41.5,25 38.5,32 35.5,32" fill="#FFFFFF" opacity="0.45"/>
            <path d="M26 43 Q32 47 38 42" stroke="#451A03" stroke-width="2.4" fill="none" stroke-linecap="round"/>
            <circle cx="11" cy="14" r="1.5" fill="#FEF08A"/>
            <circle cx="53" cy="14" r="1.5" fill="#FEF08A"/>
          </svg>
        </div>
        <div>
          <div class="font-silk font-bold text-xs sm:text-base text-white tracking-wider leading-none">
            PINEAPPLE <span class="text-yellow-300">SMP</span>
          </div>
          <div id="nav-brand-subtitle" class="text-[9px] sm:text-[10px] font-extrabold text-amber-300 uppercase tracking-widest mt-1">
            LIFESTEAL SMP
          </div>
        </div>
      </a>

      <!-- Center Navigation Links -->
      <nav class="hidden lg:flex items-center gap-4 text-[11px] font-extrabold uppercase tracking-wider text-amber-100/85">
        <a href="#status" class="hover:text-yellow-300 transition-colors">Status</a>
        <a href="#events" id="nav-link-events" class="hover:text-yellow-300 transition-colors">Events</a>
        <a href="#features" class="hover:text-yellow-300 transition-colors">Features</a>
        <a href="#store" class="hover:text-yellow-300 transition-colors">Store</a>
        <a href="#partners" class="hover:text-yellow-300 transition-colors">Partners</a>
        <a href="#funders" class="hover:text-yellow-300 transition-colors">Funders</a>
        <a href="#join" class="hover:text-yellow-300 transition-colors">Join</a>
        <a href="#ai-support" class="hover:text-yellow-300 transition-colors">AI</a>
      </nav>

      <!-- Quick Copy IP Pill & Discord CTA -->
      <div class="flex items-center gap-2">
        <button type="button" id="nav-quick-copy-btn" onclick="copyCurrentModePrimaryIp()" class="hidden md:inline-flex items-center gap-2 px-3 py-1.5 rounded-xl bg-[#1E1707] hover:bg-[#2B210A] border border-yellow-400/50 text-xs font-mono font-bold text-yellow-300 transition-all active:scale-95 cursor-pointer" title="Click to copy Server IP">
          <span class="w-2 h-2 rounded-full bg-lime-400 animate-pulse"></span>
          <span id="nav-quick-ip-text">basic.vitalcloud.in:19126</span>
          <i class="fa-regular fa-copy text-[11px] text-amber-200"></i>
        </button>

        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="mc-btn bg-gradient-to-b from-indigo-500 to-indigo-700 text-white font-extrabold text-xs px-3 sm:px-3.5 py-2 rounded-xl flex items-center gap-1.5 uppercase tracking-wider shadow-md">
          <i class="fa-brands fa-discord text-sm"></i>
          <span class="hidden sm:inline">Discord</span>
        </a>
      </div>
    </div>
  </header>

  <main class="flex-1">

    <!-- ===================================================================== -->
    <!-- LIFESTEAL GAMEMODE PORTAL (100% EXISTING EXPERIENCE)                  -->
    <!-- ===================================================================== -->
    <div id="portal-lifesteal">
      <!-- LIFESTEAL HERO SECTION -->
      <section class="relative py-12 sm:py-16 max-w-7xl mx-auto px-4 sm:px-6 overflow-hidden">
        <div class="pointer-events-none absolute top-10 left-8 w-2 h-2 rotate-45 bg-yellow-300 sparkle-dot"></div>
        <div class="pointer-events-none absolute top-24 right-14 w-2.5 h-2.5 rotate-45 bg-amber-400 sparkle-dot" style="animation-delay: 1.2s;"></div>
        <div class="pointer-events-none absolute bottom-12 left-1/3 w-2 h-2 rotate-45 bg-yellow-200 sparkle-dot" style="animation-delay: 2.1s;"></div>

        <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
          <div class="lg:col-span-7 text-center lg:text-left space-y-5">
            <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-yellow-400/15 border border-yellow-400/60 text-yellow-300 text-xs font-black uppercase tracking-widest shadow-[0_0_20px_rgba(255,214,10,0.2)]">
              <i class="fa-solid fa-fire text-amber-400"></i>
              <span>LIFESTEAL SMP &bull; SEASON 1 LAUNCHED</span>
            </div>

            <h1 class="font-pixel text-3xl sm:text-5xl lg:text-[46px] text-white leading-tight drop-shadow-[0_4px_0_#78350F]">
              PINEAPPLE <span class="text-transparent bg-clip-text bg-gradient-to-r from-yellow-200 via-yellow-400 to-amber-500">SMP — LIFESTEAL</span>
            </h1>

            <p class="text-amber-100/90 text-sm sm:text-base max-w-2xl mx-auto lg:mx-0 leading-relaxed">
              Enter India's ultimate <strong class="text-yellow-300">Lifesteal SMP</strong> network powered by <strong class="text-yellow-300">VitalCloud</strong>. Steal hearts in intense crossplay PvP battles, gear up with custom Battle Kits, and compete in Season 1!
            </p>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3.5 pt-2 max-w-xl mx-auto lg:mx-0">
              <button type="button" onclick="copyToClipboard('basic.vitalcloud.in:19126', 'Copied Java IP: basic.vitalcloud.in:19126')" class="mc-btn bg-gradient-to-b from-yellow-300 via-yellow-400 to-amber-500 text-stone-950 p-3.5 rounded-2xl text-left flex items-center justify-between gap-3">
                <div>
                  <div class="text-[10px] font-black uppercase tracking-wider text-amber-950">Java Edition IP</div>
                  <div class="font-mono font-black text-xs sm:text-sm truncate">basic.vitalcloud.in:19126</div>
                </div>
                <div class="w-9 h-9 rounded-xl bg-stone-950/15 flex items-center justify-center shrink-0">
                  <i class="fa-regular fa-copy text-sm"></i>
                </div>
              </button>

              <button type="button" onclick="copyToClipboard('basic.vitalcloud.in', 'Copied Bedrock IP: basic.vitalcloud.in (Port: 19149)')" class="mc-btn bg-[#221906] hover:bg-[#2C2109] text-yellow-300 p-3.5 rounded-2xl text-left flex items-center justify-between gap-3">
                <div>
                  <div class="text-[10px] font-black uppercase tracking-wider text-amber-300">Bedrock IP &bull; Port 19149</div>
                  <div class="font-mono font-bold text-xs sm:text-sm truncate text-white">basic.vitalcloud.in</div>
                </div>
                <div class="w-9 h-9 rounded-xl bg-yellow-400/15 border border-yellow-400/40 flex items-center justify-center shrink-0">
                  <i class="fa-regular fa-copy text-sm text-yellow-300"></i>
                </div>
              </button>
            </div>
          </div>

          <div class="lg:col-span-5 flex flex-col items-center space-y-3.5">
            <!-- PROMINENT 3D MINECRAFT GAMEMODE SWITCHER RIGHT ABOVE SEASON 1 LAUNCHED & LOGO -->
            <div class="w-full max-w-sm bg-stone-950/95 p-1.5 rounded-2xl border-2 border-yellow-400/80 shadow-[0_0_25px_rgba(255,214,10,0.28)] grid grid-cols-2 gap-1.5" role="group" aria-label="Select Gamemode">
              <button type="button" onclick="switchGamemode('lifesteal')" class="mc-btn py-2.5 px-3 rounded-xl text-xs font-black uppercase tracking-wider bg-gradient-to-b from-yellow-300 via-yellow-400 to-amber-500 text-stone-950 flex items-center justify-center gap-1.5 shadow-md">
                <span>⚔️</span>
                <span>LIFESTEAL</span>
              </button>
              <button type="button" onclick="switchGamemode('skyblock')" class="py-2.5 px-2.5 rounded-xl text-xs font-extrabold uppercase tracking-wider text-amber-100 hover:text-white hover:bg-stone-900/90 flex items-center justify-center gap-1.5 transition-all cursor-pointer">
                <span>🏝️</span>
                <span>SKYBLOCK</span>
                <span class="text-[8px] font-black px-1.5 py-0.5 rounded bg-sky-400/20 text-sky-300 border border-sky-400/50 leading-none">JAVA ONLY</span>
              </button>
            </div>

            <!-- SEASON 1 LAUNCHED STATUS PILL DIRECTLY ABOVE MASCOT LOGO -->
            <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-yellow-400/15 border border-yellow-400/65 text-yellow-300 text-[10px] sm:text-[11px] font-black uppercase tracking-wider shadow-[0_0_16px_rgba(255,214,10,0.2)]">
              <span class="w-2 h-2 rounded-full bg-lime-400 animate-ping"></span>
              <span>SEASON 1 LAUNCHED &bull; JAVA + BEDROCK CROSSPLAY</span>
            </div>

            <div class="relative mascot-float">
              <div class="absolute -inset-5 bg-gradient-to-tr from-yellow-400/30 via-amber-400/20 to-yellow-200/30 rounded-full blur-2xl"></div>
              <div class="relative mc-panel p-6 sm:p-8 rounded-3xl border-2 border-yellow-400/85 flex flex-col items-center">
                <svg viewBox="0 0 200 210" class="w-48 h-48 sm:w-60 sm:h-60 drop-shadow-[0_16px_28px_rgba(0,0,0,0.8)]" xmlns="http://www.w3.org/2000/svg" aria-label="PineappleSMP Voxel Emblem Mascot Wearing Z-Black Sunglasses">
                  <polygon points="100,8 178,42 168,146 100,196 32,146 22,42" fill="#FACC15" stroke="#451A03" stroke-width="4" stroke-linejoin="round"/>
                  <polygon points="100,16 170,47 161,141 100,187 39,141 30,47" fill="#1A1204" stroke="#FDE047" stroke-width="2" stroke-linejoin="round"/>
                  <circle cx="38" cy="52" r="3" fill="#FEF08A"/>
                  <circle cx="162" cy="52" r="3" fill="#FEF08A"/>
                  <circle cx="46" cy="136" r="3" fill="#FACC15"/>
                  <circle cx="154" cy="136" r="3" fill="#FACC15"/>
                  <polygon points="164,24 167,31 174,34 167,37 164,44 161,37 154,34 161,31" fill="#FEF08A"/>
                  <polygon points="34,26 36,31 41,33 36,35 34,40 32,35 27,33 32,31" fill="#FDE047"/>
                  <polygon points="62,32 54,64 82,58" fill="#14532D" stroke="#052E16" stroke-width="2.5" stroke-linejoin="round"/>
                  <polygon points="138,32 118,58 146,64" fill="#14532D" stroke="#052E16" stroke-width="2.5" stroke-linejoin="round"/>
                  <polygon points="78,20 68,58 96,56" fill="#16A34A" stroke="#052E16" stroke-width="2.5" stroke-linejoin="round"/>
                  <polygon points="122,20 104,56 132,58" fill="#15803D" stroke="#052E16" stroke-width="2.5" stroke-linejoin="round"/>
                  <polygon points="100,12 83,56 117,56" fill="#22C55E" stroke="#052E16" stroke-width="3" stroke-linejoin="round"/>
                  <polygon points="100,16 93,54 107,54" fill="#86EFAC" opacity="0.5"/>
                  <rect x="48" y="54" width="94" height="106" rx="10" fill="#FACC15" stroke="#451A03" stroke-width="4.5"/>
                  <path d="M142 58 L152 65 L152 153 L142 158 Z" fill="#B45309" stroke="#451A03" stroke-width="3.5" stroke-linejoin="round"/>
                  <rect x="53" y="58" width="84" height="14" rx="5" fill="#FEF9C3" opacity="0.65"/>
                  <g stroke="#92400E" stroke-width="2" opacity="0.45">
                    <path d="M54 106 L74 126 L54 146 M74 106 L94 126 L74 146 M94 106 L114 126 L94 146 M114 106 L134 126 L114 146" fill="none"/>
                    <path d="M136 106 L116 126 L136 146 M116 106 L96 126 L116 146 M96 106 L76 126 L96 146 M76 106 L56 126 L76 146" fill="none"/>
                    <line x1="52" y1="106" x2="138" y2="106"/>
                  </g>
                  <g>
                    <polygon points="36,77 50,78 50,85 37,83" fill="#09090B" stroke="#000000" stroke-width="2"/>
                    <polygon points="140,78 156,76 155,83 140,85" fill="#09090B" stroke="#000000" stroke-width="2"/>
                    <polygon points="46,72 91,75 88,99 50,96" fill="#09090B" stroke="#000000" stroke-width="3.5" stroke-linejoin="round"/>
                    <polygon points="99,75 144,72 140,96 102,99" fill="#09090B" stroke="#000000" stroke-width="3.5" stroke-linejoin="round"/>
                    <polygon points="89,75 101,75 100,82 90,82" fill="#09090B" stroke="#000000" stroke-width="2"/>
                    <polygon points="55,76 66,76 58,93 52,93" fill="#FFFFFF" opacity="0.45"/>
                    <polygon points="70,77 75,77 67,93 62,93" fill="#FFFFFF" opacity="0.22"/>
                    <polygon points="108,76 119,76 111,93 105,93" fill="#FFFFFF" opacity="0.45"/>
                    <polygon points="123,77 128,77 120,93 115,93" fill="#FFFFFF" opacity="0.22"/>
                  </g>
                  <path d="M80 130 Q97 141 114 127" stroke="#451A03" stroke-width="4.5" fill="none" stroke-linecap="round"/>
                  <path d="M172 156 C172 150 164 148 160 154 C156 148 148 150 148 156 C148 164 160 171 160 171 C160 171 172 164 172 156 Z" fill="#EF4444" stroke="#450A0A" stroke-width="2.5"/>
                </svg>
                <div class="mt-2 flex items-center gap-2 text-xs font-black uppercase tracking-widest text-yellow-300">
                  <i class="fa-solid fa-heart text-rose-500"></i>
                  <span>Steal Hearts &bull; Rule Season 1</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <div class="mc-grass-divider my-2"></div>

      <!-- LIFESTEAL LIVE SERVER TELEMETRY & PLAYERS ONLINE -->
      <section id="status" class="py-14 max-w-7xl mx-auto px-4 sm:px-6">
        <div class="flex flex-col sm:flex-row sm:items-end justify-between gap-4 mb-8">
          <div>
            <div class="inline-flex items-center gap-2 px-3 py-1 rounded-lg bg-lime-400/15 border border-lime-400/50 text-lime-300 text-[11px] font-black uppercase tracking-widest mb-2">
              <span class="w-2 h-2 rounded-full bg-lime-400 animate-ping"></span>
              <span>Auto-Sync: Every 5s</span>
            </div>
            <h2 class="font-pixel text-2xl sm:text-3xl text-white">
              LIVE SERVER <span class="text-yellow-300">TELEMETRY</span>
            </h2>
            <p class="text-xs sm:text-sm text-amber-100/80 mt-1">
              Real-time multi-protocol status &amp; player roster <span id="last-updated-text" class="text-yellow-300 font-mono text-xs">(Syncing...)</span>
            </p>
          </div>

          <button type="button" onclick="fetchLiveServerStatus(true)" class="mc-btn bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black text-xs px-4 py-2.5 rounded-xl inline-flex items-center gap-2 uppercase tracking-wider self-start sm:self-auto">
            <i id="refresh-icon" class="fa-solid fa-arrows-rotate"></i>
            <span>Refresh Now</span>
          </button>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4 mb-6">
          <div class="mc-panel p-4 rounded-2xl">
            <div class="flex items-center justify-between text-xs text-amber-200 uppercase font-bold">
              <span>Server Status</span>
              <span id="ping-latency-badge" class="font-mono text-[10px] px-2 py-0.5 rounded bg-stone-950 text-yellow-300 border border-yellow-500/40">-- MS</span>
            </div>
            <div id="server-status-badge" class="font-bold flex items-center gap-2 text-base mt-2 text-yellow-300">
              <span id="server-status-dot" class="w-2.5 h-2.5 rounded-sm bg-yellow-400 animate-pulse"></span>
              <span id="server-status-text">CHECKING...</span>
            </div>
            <div id="server-version-text" class="text-[11px] text-amber-200/75 mt-1 font-mono">
              MC 1.20 - 1.21+ &bull; Crossplay
            </div>
          </div>

          <div class="mc-panel p-4 rounded-2xl">
            <div class="flex items-center justify-between text-xs text-amber-200 uppercase font-bold">
              <span>Players Online</span>
              <i class="fa-solid fa-users text-yellow-300"></i>
            </div>
            <div class="mt-2 flex items-baseline gap-1.5 font-mono">
              <span id="server-players-online" class="text-2xl font-black text-white">0</span>
              <span id="server-players-max" class="text-sm font-bold text-amber-300">/ 50</span>
            </div>
            <div id="server-players-status" class="text-[11px] text-amber-200/75 mt-1">
              Querying Java &amp; Bedrock...
            </div>
          </div>

          <div onclick="copyToClipboard('basic.vitalcloud.in:19126', 'Copied Java IP: basic.vitalcloud.in:19126')" class="mc-panel p-4 rounded-2xl cursor-pointer group">
            <div class="flex items-center justify-between text-xs text-amber-200 uppercase font-bold">
              <span>Java Edition</span>
              <i class="fa-regular fa-copy text-yellow-300 group-hover:scale-110 transition-transform"></i>
            </div>
            <div class="font-mono font-bold text-sm sm:text-base text-yellow-300 mt-2 truncate">
              basic.vitalcloud.in:19126
            </div>
            <div class="text-[11px] text-amber-200/75 mt-1">
              Click to copy Java address
            </div>
          </div>

          <div onclick="copyToClipboard('19149', 'Copied Bedrock Port: 19149')" class="mc-panel p-4 rounded-2xl cursor-pointer group">
            <div class="flex items-center justify-between text-xs text-amber-200 uppercase font-bold">
              <span>Bedrock Port</span>
              <i class="fa-regular fa-copy text-yellow-300 group-hover:scale-110 transition-transform"></i>
            </div>
            <div class="font-mono font-bold text-base text-yellow-300 mt-2">
              19149
            </div>
            <div class="text-[11px] text-amber-200/75 mt-1 font-mono truncate">
              IP: basic.vitalcloud.in
            </div>
          </div>
        </div>

        <div class="mc-panel p-4 sm:p-5 rounded-2xl">
          <div class="flex items-center justify-between gap-2 mb-3">
            <span class="text-xs font-extrabold uppercase tracking-wider text-yellow-300 flex items-center gap-2">
              <i class="fa-solid fa-gamepad"></i> Active Online Players
            </span>
            <span class="text-[11px] text-amber-200/75">Live 3D Heads</span>
          </div>
          <div id="card-players-list" class="flex flex-wrap items-center gap-2">
            <span class="text-xs text-amber-200/75 italic">Syncing live player roster...</span>
          </div>
        </div>
      </section>

      <div class="mc-grass-divider my-2"></div>

      <!-- UPCOMING EVENTS SECTION -->
      <section id="events" class="py-14 max-w-6xl mx-auto px-4 sm:px-6">
        <div class="mc-panel rounded-3xl p-6 sm:p-10 border-2 border-yellow-400/80 relative overflow-hidden">
          <div class="flex flex-col lg:flex-row lg:items-center justify-between gap-8">
            <div class="space-y-4 max-w-2xl">
              <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-rose-500/20 border border-rose-400/60 text-rose-300 text-xs font-black uppercase tracking-widest">
                <i class="fa-solid fa-trophy"></i> Official Server Tournament
              </div>
              <h2 class="font-pixel text-xl sm:text-3xl text-white leading-snug">
                Upcoming PvP Event on <span class="text-yellow-300">29 November 2026</span>
              </h2>
              <p class="text-amber-100/90 text-xs sm:text-sm leading-relaxed">
                Gear up for the biggest Lifesteal PvP showdown of Season 1! Open to both <strong class="text-yellow-300">Java &amp; Bedrock</strong> fighters. Battle in the official tournament arena for rare Season 1 rewards, Lifesteal hearts, and glory.
              </p>
              <div class="flex flex-wrap items-center gap-3 pt-1">
                <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="mc-btn bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black text-xs px-5 py-3 rounded-xl inline-flex items-center gap-2 uppercase tracking-wider">
                  <i class="fa-brands fa-discord text-base"></i>
                  <span>Register on Discord</span>
                </a>
                <span class="text-xs font-mono text-amber-200 bg-stone-950/80 px-3.5 py-2.5 rounded-xl border border-yellow-500/35">
                  <i class="fa-solid fa-clock text-yellow-300 mr-1.5"></i>29 Nov 2026 &bull; Crossplay Arena
                </span>
              </div>
            </div>

            <div class="grid grid-cols-4 gap-2.5 sm:gap-3 shrink-0">
              <div class="bg-stone-950/90 border-2 border-yellow-400/60 rounded-2xl p-3 sm:p-4 text-center min-w-[68px] sm:min-w-[82px]">
                <div id="event-cd-days" class="font-pixel text-lg sm:text-2xl text-yellow-300">00</div>
                <div class="text-[10px] font-extrabold uppercase tracking-wider text-amber-200 mt-1.5">Days</div>
              </div>
              <div class="bg-stone-950/90 border-2 border-yellow-400/60 rounded-2xl p-3 sm:p-4 text-center min-w-[68px] sm:min-w-[82px]">
                <div id="event-cd-hours" class="font-pixel text-lg sm:text-2xl text-yellow-300">00</div>
                <div class="text-[10px] font-extrabold uppercase tracking-wider text-amber-200 mt-1.5">Hours</div>
              </div>
              <div class="bg-stone-950/90 border-2 border-yellow-400/60 rounded-2xl p-3 sm:p-4 text-center min-w-[68px] sm:min-w-[82px]">
                <div id="event-cd-mins" class="font-pixel text-lg sm:text-2xl text-yellow-300">00</div>
                <div class="text-[10px] font-extrabold uppercase tracking-wider text-amber-200 mt-1.5">Mins</div>
              </div>
              <div class="bg-stone-950/90 border-2 border-yellow-400/60 rounded-2xl p-3 sm:p-4 text-center min-w-[68px] sm:min-w-[82px]">
                <div id="event-cd-secs" class="font-pixel text-lg sm:text-2xl text-amber-400">00</div>
                <div class="text-[10px] font-extrabold uppercase tracking-wider text-amber-200 mt-1.5">Secs</div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <div class="mc-grass-divider my-2"></div>

      <!-- LIFESTEAL SERVER FEATURES & GAMEPLAY -->
      <section id="features" class="py-14 max-w-7xl mx-auto px-4 sm:px-6">
        <div class="text-center mb-10">
          <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-lg bg-yellow-400/15 border border-yellow-400/50 text-yellow-300 text-xs font-extrabold uppercase tracking-widest mb-2">
            <i class="fa-solid fa-bolt"></i> Built For Competitive PvP
          </div>
          <h2 class="font-pixel text-2xl sm:text-3xl text-white">
            SERVER FEATURES &amp; <span class="text-yellow-300">GAMEPLAY</span>
          </h2>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <div class="mc-panel p-6 rounded-3xl space-y-3">
            <div class="w-12 h-12 rounded-2xl bg-yellow-400/20 border-2 border-yellow-400/70 flex items-center justify-center text-yellow-300 text-xl">
              <i class="fa-solid fa-server"></i>
            </div>
            <h3 class="font-silk font-bold text-lg text-white">Hosted on VitalCloud</h3>
            <p class="text-xs sm:text-sm text-amber-100/85 leading-relaxed">
              Powered by enterprise <strong class="text-yellow-300">VitalCloud</strong> infrastructure delivering ultra-low latency Indian/Asian routing, advanced DDoS protection, 20 TPS performance, and 24/7 uptime.
            </p>
          </div>

          <div class="mc-panel p-6 rounded-3xl space-y-3">
            <div class="w-12 h-12 rounded-2xl bg-rose-500/20 border-2 border-rose-400/70 flex items-center justify-center text-rose-400 text-xl">
              <i class="fa-solid fa-heart-pulse"></i>
            </div>
            <h3 class="font-silk font-bold text-lg text-white">Lifesteal Combat</h3>
            <p class="text-xs sm:text-sm text-amber-100/85 leading-relaxed">
              Eliminate rivals to permanently steal their hearts and grow stronger! Lose all your hearts and face elimination until your teammates craft a Revive Beacon.
            </p>
          </div>

          <div class="mc-panel p-6 rounded-3xl space-y-3">
            <div class="w-12 h-12 rounded-2xl bg-lime-400/20 border-2 border-lime-400/70 flex items-center justify-center text-lime-300 text-xl">
              <i class="fa-solid fa-globe"></i>
            </div>
            <h3 class="font-silk font-bold text-lg text-white">Crossplay Bedrock + Java</h3>
            <p class="text-xs sm:text-sm text-amber-100/85 leading-relaxed">
              Play seamlessly together from PC (Java <code class="text-yellow-300">:19126</code>) or Mobile, Console &amp; Windows (Bedrock <code class="text-yellow-300">:19149</code>) in the exact same Lifesteal world.
            </p>
          </div>
        </div>
      </section>

      <div class="mc-grass-divider my-2"></div>

      <!-- LIFESTEAL BATTLE KITS & GEAR STORE -->
      <section id="store" class="py-14 max-w-7xl mx-auto px-4 sm:px-6">
        <div class="text-center max-w-3xl mx-auto mb-10 space-y-3">
          <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-lg bg-yellow-400/15 border border-yellow-400/55 text-yellow-300 text-xs font-extrabold uppercase tracking-widest">
            <i class="fa-solid fa-shield-halved"></i> Instant UPI Store &bull; 15% GST 3-Day Damage Insurance
          </div>
          <h2 class="font-pixel text-2xl sm:text-4xl text-white">
            BATTLE KITS &amp; <span class="text-yellow-300">GEAR STORE</span>
          </h2>
          <p class="text-xs sm:text-sm text-amber-100/85 leading-relaxed">
            All kits include <strong class="text-yellow-300">15% GST Insurance</strong> (covers kit damage/replacement for <strong>3 Days</strong>) and our <strong class="text-lime-300">3-Hour Undamaged Kit Refund Policy</strong> (100% refund within 3 hours if kit is completely undamaged).
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <!-- 1. Stone Kit -->
          <div class="mc-panel p-6 rounded-3xl flex flex-col justify-between space-y-4">
            <div class="space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-xs font-black uppercase px-2.5 py-1 rounded-lg bg-stone-700/60 text-stone-200 border border-stone-500">Starter Tier</span>
                <span class="text-xs font-mono text-amber-200">Base ₹30 + ₹5 GST</span>
              </div>
              <div class="flex items-center gap-3">
                <div class="w-12 h-12 rounded-2xl bg-stone-800/90 border border-stone-500/60 p-2 shrink-0">
                  <svg viewBox="0 0 32 32" class="w-full h-full" xmlns="http://www.w3.org/2000/svg">
                    <polygon points="22,4 28,4 28,10 15,23 9,17" fill="#A8A29E" stroke="#44403C" stroke-width="1.5"/>
                    <rect x="6" y="18" width="10" height="3" rx="1" transform="rotate(45 11 19.5)" fill="#78350F"/>
                    <rect x="4" y="24" width="6" height="4" rx="1" transform="rotate(-45 7 26)" fill="#92400E"/>
                  </svg>
                </div>
                <div>
                  <h3 class="font-silk font-bold text-xl text-white">Stone Kit</h3>
                  <div class="flex items-baseline gap-2">
                    <span class="font-pixel text-xl text-yellow-300">₹35</span>
                    <span class="text-[11px] text-amber-200/80">incl. 15% GST</span>
                  </div>
                </div>
              </div>
              <ul class="text-xs text-amber-100/85 space-y-1.5 pt-2 border-t border-yellow-500/20">
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>Full Enchanted Stone Gear &amp; Tools</li>
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>Starter Food &amp; Golden Apples</li>
                <li><i class="fa-solid fa-shield text-amber-300 mr-1.5"></i>3-Day Damage Insurance (15% GST)</li>
                <li><i class="fa-solid fa-rotate-left text-lime-300 mr-1.5"></i>3-Hour Refund Policy (If Undamaged)</li>
              </ul>
            </div>
            <button type="button" onclick="openKitCheckout('Lifesteal Stone Kit', 30, 5, 35, 'Full Enchanted Stone Gear, Starter Food & Golden Apples')" class="mc-btn w-full bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black py-3 rounded-xl text-xs uppercase tracking-wider">
              Buy Stone Kit — ₹35
            </button>
          </div>

          <!-- 2. Legend Kit -->
          <div class="mc-panel p-6 rounded-3xl flex flex-col justify-between space-y-4 border-2 border-yellow-300 shadow-[0_0_30px_rgba(255,214,10,0.25)] relative">
            <div class="space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-[10px] font-black uppercase px-2.5 py-1 rounded-lg bg-yellow-400 text-stone-950">Best Value</span>
                <span class="text-xs font-mono text-amber-200">Base ₹40 + ₹6 GST</span>
              </div>
              <div class="flex items-center gap-3">
                <div class="w-12 h-12 rounded-2xl bg-yellow-400/20 border border-yellow-300 p-2 shrink-0">
                  <svg viewBox="0 0 32 32" class="w-full h-full" xmlns="http://www.w3.org/2000/svg">
                    <polygon points="4,22 6,10 12,16 16,7 20,16 26,10 28,22" fill="#FACC15" stroke="#854D0E" stroke-width="1.5"/>
                    <rect x="4" y="22" width="24" height="4" rx="1" fill="#EAB308"/>
                    <circle cx="16" cy="18" r="2" fill="#38BDF8"/>
                  </svg>
                </div>
                <div>
                  <h3 class="font-silk font-bold text-xl text-yellow-300">Legend Kit</h3>
                  <div class="flex items-baseline gap-2">
                    <span class="font-pixel text-xl text-white">₹46</span>
                    <span class="text-[11px] text-amber-200/80">incl. 15% GST</span>
                  </div>
                </div>
              </div>
              <div class="bg-stone-950/80 border border-yellow-500/35 rounded-2xl p-3 space-y-1 text-xs text-amber-50">
                <div class="text-[10px] font-extrabold uppercase text-yellow-300 mb-1">Includes:</div>
                <div>1. Prot 3 Diamond Armour</div>
                <div>2. Sharpness 3 Sword</div>
                <div>3. 2 Totem</div>
                <div>4. 2 Enchanted Apples</div>
                <div>5. 16 Golden Apples</div>
                <div>6. 16 Ender Pearls &amp; More!</div>
              </div>
              <div class="text-[11px] text-lime-300 font-semibold">
                <i class="fa-solid fa-rotate-left mr-1"></i>3-Hour Refund Policy (Must Be Undamaged)
              </div>
            </div>
            <button type="button" onclick="openKitCheckout('Lifesteal Legend Kit', 40, 6, 46, '1. Prot 3 Diamond Armour, 2. Sharpness 3 Sword, 3. 2 Totem, 4. 2 Enchanted Apples, 5. 16 Golden Apples, 6. 16 Ender Pearls & More')" class="mc-btn w-full bg-gradient-to-b from-yellow-300 via-yellow-400 to-amber-500 text-stone-950 font-black py-3 rounded-xl text-xs uppercase tracking-wider">
              Buy Legend Kit — ₹46
            </button>
          </div>

          <!-- 3. Iron Kit -->
          <div class="mc-panel p-6 rounded-3xl flex flex-col justify-between space-y-4">
            <div class="space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-xs font-black uppercase px-2.5 py-1 rounded-lg bg-slate-300/20 text-slate-200 border border-slate-400/50">Warrior Tier</span>
                <span class="text-xs font-mono text-amber-200">Base ₹50 + ₹8 GST</span>
              </div>
              <div class="flex items-center gap-3">
                <div class="w-12 h-12 rounded-2xl bg-slate-800/90 border border-slate-400/50 p-2 shrink-0">
                  <svg viewBox="0 0 32 32" class="w-full h-full" xmlns="http://www.w3.org/2000/svg">
                    <path d="M7 7 L12 7 L16 11 L20 7 L25 7 L27 14 L23 15 L23 26 L9 26 L9 15 L5 14 Z" fill="#E2E8F0" stroke="#475569" stroke-width="1.5"/>
                  </svg>
                </div>
                <div>
                  <h3 class="font-silk font-bold text-xl text-white">Iron Kit</h3>
                  <div class="flex items-baseline gap-2">
                    <span class="font-pixel text-xl text-yellow-300">₹58</span>
                    <span class="text-[11px] text-amber-200/80">incl. 15% GST</span>
                  </div>
                </div>
              </div>
              <ul class="text-xs text-amber-100/85 space-y-1.5 pt-2 border-t border-yellow-500/20">
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>Enchanted Iron Armour &amp; Sharpness Blade</li>
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>Golden Apples, Pearls &amp; PvP Potions</li>
                <li><i class="fa-solid fa-shield text-amber-300 mr-1.5"></i>3-Day Damage Insurance (15% GST)</li>
                <li><i class="fa-solid fa-rotate-left text-lime-300 mr-1.5"></i>3-Hour Refund Policy (If Undamaged)</li>
              </ul>
            </div>
            <button type="button" onclick="openKitCheckout('Lifesteal Iron Kit', 50, 8, 58, 'Enchanted Iron Armour, Sharpness Blade, Golden Apples & PvP Potions')" class="mc-btn w-full bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black py-3 rounded-xl text-xs uppercase tracking-wider">
              Buy Iron Kit — ₹58
            </button>
          </div>

          <!-- 4. Diamond Kit -->
          <div class="mc-panel p-6 rounded-3xl flex flex-col justify-between space-y-4">
            <div class="space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-xs font-black uppercase px-2.5 py-1 rounded-lg bg-cyan-400/20 text-cyan-300 border border-cyan-400/50">Champion Tier</span>
                <span class="text-xs font-mono text-amber-200">Base ₹100 + ₹15 GST</span>
              </div>
              <div class="flex items-center gap-3">
                <div class="w-12 h-12 rounded-2xl bg-cyan-950/80 border border-cyan-400/60 p-2 shrink-0">
                  <svg viewBox="0 0 32 32" class="w-full h-full" xmlns="http://www.w3.org/2000/svg">
                    <polygon points="16,4 27,13 16,28 5,13" fill="#22D3EE" stroke="#0E7490" stroke-width="1.5"/>
                    <polygon points="16,4 22,13 16,28 10,13" fill="#67E8F9" opacity="0.7"/>
                  </svg>
                </div>
                <div>
                  <h3 class="font-silk font-bold text-xl text-white">Diamond Kit</h3>
                  <div class="flex items-baseline gap-2">
                    <span class="font-pixel text-xl text-yellow-300">₹115</span>
                    <span class="text-[11px] text-amber-200/80">incl. 15% GST</span>
                  </div>
                </div>
              </div>
              <ul class="text-xs text-amber-100/85 space-y-1.5 pt-2 border-t border-yellow-500/20">
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>Max Protection Diamond Armour Set</li>
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>Totems, Enchanted Golden Apples &amp; Pearls</li>
                <li><i class="fa-solid fa-shield text-amber-300 mr-1.5"></i>3-Day Damage Insurance (15% GST)</li>
                <li><i class="fa-solid fa-rotate-left text-lime-300 mr-1.5"></i>3-Hour Refund Policy (If Undamaged)</li>
              </ul>
            </div>
            <button type="button" onclick="openKitCheckout('Lifesteal Diamond Kit', 100, 15, 115, 'Max Protection Diamond Armour Set, Totems, Enchanted Golden Apples & Pearls')" class="mc-btn w-full bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black py-3 rounded-xl text-xs uppercase tracking-wider">
              Buy Diamond Kit — ₹115
            </button>
          </div>

          <!-- 5. Netherite Kit -->
          <div class="mc-panel p-6 rounded-3xl flex flex-col justify-between space-y-4">
            <div class="space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-xs font-black uppercase px-2.5 py-1 rounded-lg bg-purple-500/20 text-purple-300 border border-purple-400/50">Warlord Tier</span>
                <span class="text-xs font-mono text-amber-200">Base ₹125 + ₹19 GST</span>
              </div>
              <div class="flex items-center gap-3">
                <div class="w-12 h-12 rounded-2xl bg-purple-950/70 border border-purple-400/60 p-2 shrink-0">
                  <svg viewBox="0 0 32 32" class="w-full h-full" xmlns="http://www.w3.org/2000/svg">
                    <rect x="6" y="10" width="20" height="14" rx="3" fill="#44403C" stroke="#A855F7" stroke-width="1.5"/>
                    <polygon points="8,10 14,7 24,7 26,10" fill="#57534E"/>
                    <line x1="10" y1="15" x2="22" y2="15" stroke="#FACC15" stroke-width="2"/>
                  </svg>
                </div>
                <div>
                  <h3 class="font-silk font-bold text-xl text-white">Netherite Kit</h3>
                  <div class="flex items-baseline gap-2">
                    <span class="font-pixel text-xl text-yellow-300">₹144</span>
                    <span class="text-[11px] text-amber-200/80">incl. 15% GST</span>
                  </div>
                </div>
              </div>
              <ul class="text-xs text-amber-100/85 space-y-1.5 pt-2 border-t border-yellow-500/20">
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>Heavy Netherite Armour &amp; Sharpness V Weapon</li>
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>Multiple Totems, God Apples &amp; Crystal Supplies</li>
                <li><i class="fa-solid fa-shield text-amber-300 mr-1.5"></i>3-Day Damage Insurance (15% GST)</li>
                <li><i class="fa-solid fa-rotate-left text-lime-300 mr-1.5"></i>3-Hour Refund Policy (If Undamaged)</li>
              </ul>
            </div>
            <button type="button" onclick="openKitCheckout('Lifesteal Netherite Kit', 125, 19, 144, 'Heavy Netherite Armour, Sharpness V Weapon, Totems & God Apples')" class="mc-btn w-full bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black py-3 rounded-xl text-xs uppercase tracking-wider">
              Buy Netherite Kit — ₹144
            </button>
          </div>

          <!-- 6. Ender Kit -->
          <div class="mc-panel p-6 rounded-3xl flex flex-col justify-between space-y-4">
            <div class="space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-xs font-black uppercase px-2.5 py-1 rounded-lg bg-fuchsia-500/20 text-fuchsia-300 border border-fuchsia-400/50">God Tier</span>
                <span class="text-xs font-mono text-amber-200">Base ₹150 + ₹23 GST</span>
              </div>
              <div class="flex items-center gap-3">
                <div class="w-12 h-12 rounded-2xl bg-fuchsia-950/70 border border-fuchsia-400/60 p-2 shrink-0">
                  <svg viewBox="0 0 32 32" class="w-full h-full" xmlns="http://www.w3.org/2000/svg">
                    <circle cx="16" cy="16" r="11" fill="#1E1B4B" stroke="#E879F9" stroke-width="2"/>
                    <ellipse cx="16" cy="16" rx="4" ry="8" fill="#10B981"/>
                    <circle cx="16" cy="16" r="2" fill="#022C22"/>
                  </svg>
                </div>
                <div>
                  <h3 class="font-silk font-bold text-xl text-white">Ender Kit</h3>
                  <div class="flex items-baseline gap-2">
                    <span class="font-pixel text-xl text-yellow-300">₹173</span>
                    <span class="text-[11px] text-amber-200/80">incl. 15% GST</span>
                  </div>
                </div>
              </div>
              <ul class="text-xs text-amber-100/85 space-y-1.5 pt-2 border-t border-yellow-500/20">
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>Ultimate God-Enchanted Netherite + Elytra Set</li>
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>Stack of Pearls, Totems, Rockets &amp; God Apples</li>
                <li><i class="fa-solid fa-shield text-amber-300 mr-1.5"></i>3-Day Damage Insurance (15% GST)</li>
                <li><i class="fa-solid fa-rotate-left text-lime-300 mr-1.5"></i>3-Hour Refund Policy (If Undamaged)</li>
              </ul>
            </div>
            <button type="button" onclick="openKitCheckout('Lifesteal Ender Kit', 150, 23, 173, 'Ultimate God-Enchanted Netherite + Elytra Set, Totems, Rockets & God Apples')" class="mc-btn w-full bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black py-3 rounded-xl text-xs uppercase tracking-wider">
              Buy Ender Kit — ₹173
            </button>
          </div>
        </div>
      </section>

      <div class="mc-grass-divider my-2"></div>

      <!-- LIFESTEAL HOW TO JOIN CARDS -->
      <section id="join" class="py-14 max-w-6xl mx-auto px-4 sm:px-6">
        <div class="text-center mb-8">
          <h2 class="font-pixel text-2xl sm:text-3xl text-white">
            HOW TO <span class="text-yellow-300">JOIN LIFESTEAL</span>
          </h2>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
          <div class="mc-panel p-6 rounded-3xl space-y-4">
            <div class="flex items-center justify-between">
              <h3 class="font-silk font-bold text-lg text-yellow-300 flex items-center gap-2">
                <i class="fa-solid fa-mobile-screen"></i> Bedrock Edition (PE)
              </h3>
              <span class="text-[10px] font-black uppercase px-2.5 py-1 rounded bg-yellow-400/15 text-yellow-300 border border-yellow-400/40">MCPE / Console / Win</span>
            </div>
            <ol class="text-xs sm:text-sm text-amber-100/85 space-y-2 list-decimal list-inside">
              <li>Open Minecraft Bedrock &rarr; <strong>Play</strong> &rarr; <strong>Servers</strong> &rarr; <strong>Add Server</strong>.</li>
              <li>Enter Server Address: <code class="text-yellow-300 font-mono">basic.vitalcloud.in</code></li>
              <li>Enter Port: <code class="text-yellow-300 font-mono">19149</code> and tap <strong>Play</strong>!</li>
            </ol>
            <div class="grid grid-cols-2 gap-2.5 pt-1">
              <button type="button" onclick="copyToClipboard('basic.vitalcloud.in', 'Copied Bedrock IP: basic.vitalcloud.in')" class="mc-btn bg-stone-900 hover:bg-stone-800 text-yellow-300 font-bold py-2.5 px-3 rounded-xl text-xs">
                <i class="fa-regular fa-copy mr-1"></i> Copy IP
              </button>
              <button type="button" onclick="copyToClipboard('19149', 'Copied Bedrock Port: 19149')" class="mc-btn bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black py-2.5 px-3 rounded-xl text-xs">
                <i class="fa-regular fa-copy mr-1"></i> Copy Port: 19149
              </button>
            </div>
          </div>

          <div class="mc-panel p-6 rounded-3xl space-y-4">
            <div class="flex items-center justify-between">
              <h3 class="font-silk font-bold text-lg text-yellow-300 flex items-center gap-2">
                <i class="fa-solid fa-desktop"></i> Java Edition (JAWA)
              </h3>
              <span class="text-[10px] font-black uppercase px-2.5 py-1 rounded bg-yellow-400/15 text-yellow-300 border border-yellow-400/40">MC 1.20 – 1.21+</span>
            </div>
            <ol class="text-xs sm:text-sm text-amber-100/85 space-y-2 list-decimal list-inside">
              <li>Launch Minecraft Java Edition &rarr; Click <strong>Multiplayer</strong>.</li>
              <li>Click <strong>Add Server</strong> or <strong>Direct Connection</strong>.</li>
              <li>Paste <code class="text-yellow-300 font-mono">basic.vitalcloud.in:19126</code> and click <strong>Join Server</strong>!</li>
            </ol>
            <button type="button" onclick="copyToClipboard('basic.vitalcloud.in:19126', 'Copied Java IP: basic.vitalcloud.in:19126')" class="mc-btn w-full bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black py-2.5 px-4 rounded-xl text-xs uppercase tracking-wider">
              <i class="fa-regular fa-copy mr-1.5"></i> Copy Java IP: basic.vitalcloud.in:19126
            </button>
          </div>
        </div>
      </section>
    </div>

    <!-- ===================================================================== -->
    <!-- SKYBLOCK GAMEMODE PORTAL (NEW DEDICATED EXPERIENCE IN SAME WEBSITE)   -->
    <!-- ===================================================================== -->
    <div id="portal-skyblock" class="hidden">
      <!-- SKYBLOCK HERO SECTION -->
      <section class="relative py-12 sm:py-16 max-w-7xl mx-auto px-4 sm:px-6 overflow-hidden">
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
          <div class="lg:col-span-7 text-center lg:text-left space-y-5">
            <div class="flex flex-wrap items-center justify-center lg:justify-start gap-2.5">
              <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-sky-400/15 border border-sky-400/60 text-sky-300 text-xs font-black uppercase tracking-widest shadow-[0_0_20px_rgba(56,189,248,0.2)]">
                <i class="fa-solid fa-cloud text-sky-400"></i>
                <span>PINEAPPLE SKYBLOCK &bull; SEASON 1</span>
              </div>
              <div class="inline-flex items-center gap-1.5 px-3.5 py-1.5 rounded-full bg-yellow-400/20 border border-yellow-400/70 text-yellow-300 text-xs font-black uppercase tracking-wider">
                <i class="fa-solid fa-desktop"></i>
                <span>JAVA EDITION ONLY (JAWA)</span>
              </div>
            </div>

            <h1 class="font-pixel text-3xl sm:text-5xl lg:text-[44px] text-white leading-tight drop-shadow-[0_4px_0_#0C4A6E]">
              PINEAPPLE <span class="text-transparent bg-clip-text bg-gradient-to-r from-yellow-200 via-yellow-400 to-sky-400">SKYBLOCK — ISLANDS</span>
            </h1>

            <p class="text-amber-100/90 text-sm sm:text-base max-w-2xl mx-auto lg:mx-0 leading-relaxed">
              Build your floating sky empire from a single block! Unlock automated <strong class="text-yellow-300">Minions</strong>, upgrade custom <strong class="text-sky-300">Ore Generators</strong>, dominate <code class="text-yellow-300">/is top</code> leaderboards, and trade on the player Auction House. Currently exclusive to <strong class="text-yellow-300">Java Edition (JAWA)</strong>.
            </p>

            <!-- Skyblock Public IP & Port Copy Cards -->
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3.5 pt-2 max-w-xl mx-auto lg:mx-0">
              <button type="button" onclick="copyToClipboard('pineappleskyblock.playgg.pro:25127', 'Copied Skyblock Java IP: pineappleskyblock.playgg.pro:25127')" class="mc-btn bg-gradient-to-b from-yellow-300 via-yellow-400 to-amber-500 text-stone-950 p-3.5 rounded-2xl text-left flex items-center justify-between gap-3">
                <div class="min-w-0">
                  <div class="text-[10px] font-black uppercase tracking-wider text-amber-950">Skyblock Java IP (JAWA Only)</div>
                  <div class="font-mono font-black text-xs sm:text-sm truncate">pineappleskyblock.playgg.pro</div>
                </div>
                <div class="w-9 h-9 rounded-xl bg-stone-950/15 flex items-center justify-center shrink-0">
                  <i class="fa-regular fa-copy text-sm"></i>
                </div>
              </button>

              <button type="button" onclick="copyToClipboard('25127', 'Copied Skyblock Port: 25127')" class="mc-btn bg-[#0E1E2B] hover:bg-[#13293A] text-sky-300 p-3.5 rounded-2xl text-left flex items-center justify-between gap-3 border-sky-400/50">
                <div>
                  <div class="text-[10px] font-black uppercase tracking-wider text-sky-300">Server Port &bull; Java 1.20+</div>
                  <div class="font-mono font-bold text-xs sm:text-sm text-white">Port: 25127</div>
                </div>
                <div class="w-9 h-9 rounded-xl bg-sky-400/15 border border-sky-400/40 flex items-center justify-center shrink-0">
                  <i class="fa-regular fa-copy text-sm text-sky-300"></i>
                </div>
              </button>
            </div>
          </div>

          <!-- Floating Skyblock Island Pineapple Mascot with Gamemode Switcher & Season 1 Pill Above -->
          <div class="lg:col-span-5 flex flex-col items-center space-y-3.5">
            <!-- PROMINENT 3D MINECRAFT GAMEMODE SWITCHER RIGHT ABOVE SEASON 1 LAUNCHED & LOGO -->
            <div class="w-full max-w-sm bg-stone-950/95 p-1.5 rounded-2xl border-2 border-yellow-400/80 shadow-[0_0_25px_rgba(56,189,248,0.28)] grid grid-cols-2 gap-1.5" role="group" aria-label="Select Gamemode">
              <button type="button" onclick="switchGamemode('lifesteal')" class="py-2.5 px-3 rounded-xl text-xs font-extrabold uppercase tracking-wider text-amber-100 hover:text-white hover:bg-stone-900/90 flex items-center justify-center gap-1.5 transition-all cursor-pointer">
                <span>⚔️</span>
                <span>LIFESTEAL</span>
              </button>
              <button type="button" onclick="switchGamemode('skyblock')" class="mc-btn py-2.5 px-2.5 rounded-xl text-xs font-black uppercase tracking-wider bg-gradient-to-b from-sky-300 via-sky-400 to-sky-500 text-stone-950 flex items-center justify-center gap-1.5 shadow-md">
                <span>🏝️</span>
                <span>SKYBLOCK</span>
                <span class="text-[8px] font-black px-1.5 py-0.5 rounded bg-stone-950/20 text-stone-950 border border-stone-950/30 leading-none">JAVA ONLY</span>
              </button>
            </div>

            <!-- SEASON 1 LAUNCHED STATUS PILL DIRECTLY ABOVE MASCOT LOGO -->
            <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-sky-400/15 border border-sky-400/65 text-sky-300 text-[10px] sm:text-[11px] font-black uppercase tracking-wider shadow-[0_0_16px_rgba(56,189,248,0.2)]">
              <span class="w-2 h-2 rounded-full bg-lime-400 animate-ping"></span>
              <span>SEASON 1 LAUNCHED &bull; JAVA EDITION ONLY (JAWA)</span>
            </div>

            <div class="relative mascot-float">
              <div class="absolute -inset-5 bg-gradient-to-tr from-sky-400/30 via-yellow-400/20 to-emerald-400/25 rounded-full blur-2xl"></div>
              <div class="relative mc-panel p-6 sm:p-8 rounded-3xl border-2 border-sky-400/75 flex flex-col items-center">
                <svg viewBox="0 0 210 215" class="w-48 h-48 sm:w-60 sm:h-60 drop-shadow-[0_16px_28px_rgba(0,0,0,0.85)]" xmlns="http://www.w3.org/2000/svg" aria-label="Pineapple Skyblock Floating Island Mascot">
                  <!-- Fluffy Sky Clouds -->
                  <g fill="#E0F2FE" opacity="0.85">
                    <rect x="14" y="46" width="38" height="12" rx="6"/>
                    <rect x="22" y="39" width="22" height="10" rx="5"/>
                    <rect x="156" y="34" width="40" height="12" rx="6"/>
                    <rect x="164" y="27" width="24" height="10" rx="5"/>
                  </g>

                  <!-- Floating Grass & Stone Skyblock Island Base -->
                  <polygon points="36,154 174,154 156,174 54,174" fill="#22C55E" stroke="#052E16" stroke-width="3" stroke-linejoin="round"/>
                  <polygon points="54,174 156,174 134,196 76,196" fill="#78350F" stroke="#451A03" stroke-width="3" stroke-linejoin="round"/>
                  <polygon points="76,196 134,196 105,210" fill="#57534E" stroke="#1C1917" stroke-width="3" stroke-linejoin="round"/>

                  <!-- Pineapple Crown Leaves -->
                  <polygon points="72,22 64,54 90,48" fill="#16A34A" stroke="#052E16" stroke-width="2.5" stroke-linejoin="round"/>
                  <polygon points="138,22 120,48 146,54" fill="#15803D" stroke="#052E16" stroke-width="2.5" stroke-linejoin="round"/>
                  <polygon points="105,10 89,50 121,50" fill="#22C55E" stroke="#052E16" stroke-width="3" stroke-linejoin="round"/>

                  <!-- Golden Box Pineapple Standing on Island -->
                  <rect x="62" y="48" width="86" height="98" rx="10" fill="#FACC15" stroke="#451A03" stroke-width="4"/>
                  <path d="M148 52 L157 58 L157 140 L148 144 Z" fill="#B45309" stroke="#451A03" stroke-width="3" stroke-linejoin="round"/>
                  <rect x="67" y="52" width="76" height="12" rx="4" fill="#FEF9C3" opacity="0.65"/>

                  <!-- Z-Black Angular Sunglasses -->
                  <polygon points="52,70 64,71 64,77 53,75" fill="#09090B" stroke="#000000" stroke-width="2"/>
                  <polygon points="146,71 160,69 159,75 146,77" fill="#09090B" stroke="#000000" stroke-width="2"/>
                  <polygon points="60,66 101,69 98,90 64,87" fill="#09090B" stroke="#000000" stroke-width="3.2" stroke-linejoin="round"/>
                  <polygon points="109,69 150,66 146,87 112,90" fill="#09090B" stroke="#000000" stroke-width="3.2" stroke-linejoin="round"/>
                  <polygon points="99,69 111,69 110,75 100,75" fill="#09090B" stroke="#000000" stroke-width="2"/>
                  <polygon points="68,69 78,69 71,84 66,84" fill="#FFFFFF" opacity="0.45"/>
                  <polygon points="117,69 127,69 120,84 115,84" fill="#FFFFFF" opacity="0.45"/>

                  <!-- Confident Smirk -->
                  <path d="M90 116 Q105 126 120 114" stroke="#451A03" stroke-width="4" fill="none" stroke-linecap="round"/>

                  <!-- Mini Skyblock Chest on Island Corner -->
                  <rect x="38" y="132" width="22" height="20" rx="3" fill="#D97706" stroke="#451A03" stroke-width="2.5"/>
                  <rect x="46" y="139" width="6" height="6" fill="#FEF08A"/>
                </svg>
                <div class="mt-2 flex items-center gap-2 text-xs font-black uppercase tracking-widest text-sky-300">
                  <i class="fa-solid fa-cubes text-yellow-300"></i>
                  <span>Java Only &bull; Build Your Sky Empire</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <div class="mc-grass-divider my-2"></div>

      <!-- SKYBLOCK LIVE SERVER TELEMETRY (API CONNECTED TO free-in-1.vitalcloud.in:25127) -->
      <section class="py-14 max-w-7xl mx-auto px-4 sm:px-6">
        <div class="flex flex-col sm:flex-row sm:items-end justify-between gap-4 mb-8">
          <div>
            <div class="inline-flex items-center gap-2 px-3 py-1 rounded-lg bg-sky-400/15 border border-sky-400/50 text-sky-300 text-[11px] font-black uppercase tracking-widest mb-2">
              <span class="w-2 h-2 rounded-full bg-sky-400 animate-ping"></span>
              <span>Skyblock Live Telemetry &bull; Auto-Sync 5s</span>
            </div>
            <h2 class="font-pixel text-2xl sm:text-3xl text-white">
              SKYBLOCK <span class="text-yellow-300">SERVER STATUS</span>
            </h2>
            <p class="text-xs sm:text-sm text-amber-100/80 mt-1">
              Live Java Edition status &amp; player roster <span id="sb-last-updated-text" class="text-sky-300 font-mono text-xs">(Syncing...)</span>
            </p>
          </div>

          <button type="button" onclick="fetchSkyblockStatus(true)" class="mc-btn bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black text-xs px-4 py-2.5 rounded-xl inline-flex items-center gap-2 uppercase tracking-wider self-start sm:self-auto">
            <i id="sb-refresh-icon" class="fa-solid fa-arrows-rotate"></i>
            <span>Refresh Skyblock</span>
          </button>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4 mb-6">
          <div class="mc-panel p-4 rounded-2xl">
            <div class="flex items-center justify-between text-xs text-amber-200 uppercase font-bold">
              <span>Skyblock Status</span>
              <span id="sb-ping-badge" class="font-mono text-[10px] px-2 py-0.5 rounded bg-stone-950 text-sky-300 border border-sky-500/40">-- MS</span>
            </div>
            <div id="sb-status-badge" class="font-bold flex items-center gap-2 text-base mt-2 text-yellow-300">
              <span id="sb-status-dot" class="w-2.5 h-2.5 rounded-sm bg-yellow-400 animate-pulse"></span>
              <span id="sb-status-text">CHECKING...</span>
            </div>
            <div id="sb-version-text" class="text-[11px] text-amber-200/75 mt-1 font-mono">
              MC Java 1.20+ &bull; JAWA Only
            </div>
          </div>

          <div class="mc-panel p-4 rounded-2xl">
            <div class="flex items-center justify-between text-xs text-amber-200 uppercase font-bold">
              <span>Skyblock Players</span>
              <i class="fa-solid fa-users text-sky-300"></i>
            </div>
            <div class="mt-2 flex items-baseline gap-1.5 font-mono">
              <span id="sb-players-online" class="text-2xl font-black text-white">0</span>
              <span id="sb-players-max" class="text-sm font-bold text-amber-300">/ 50</span>
            </div>
            <div id="sb-players-status" class="text-[11px] text-amber-200/75 mt-1">
              Querying Java server...
            </div>
          </div>

          <div onclick="copyToClipboard('pineappleskyblock.playgg.pro:25127', 'Copied Skyblock Java IP: pineappleskyblock.playgg.pro:25127')" class="mc-panel p-4 rounded-2xl cursor-pointer group">
            <div class="flex items-center justify-between text-xs text-amber-200 uppercase font-bold">
              <span>Player Connect IP</span>
              <i class="fa-regular fa-copy text-yellow-300 group-hover:scale-110 transition-transform"></i>
            </div>
            <div class="font-mono font-bold text-xs sm:text-sm text-yellow-300 mt-2 truncate">
              pineappleskyblock.playgg.pro
            </div>
            <div class="text-[11px] text-amber-200/75 mt-1">
              Port: <strong class="text-white">25127</strong> (Click to copy)
            </div>
          </div>

          <div class="mc-panel p-4 rounded-2xl">
            <div class="flex items-center justify-between text-xs text-amber-200 uppercase font-bold">
              <span>Supported Edition</span>
              <i class="fa-solid fa-desktop text-yellow-300"></i>
            </div>
            <div class="font-mono font-bold text-base text-yellow-300 mt-2">
              JAVA ONLY (JAWA)
            </div>
            <div class="text-[11px] text-amber-200/75 mt-1">
              Bedrock/PE coming in future
            </div>
          </div>
        </div>

        <div class="mc-panel p-4 sm:p-5 rounded-2xl">
          <div class="flex items-center justify-between gap-2 mb-3">
            <span class="text-xs font-extrabold uppercase tracking-wider text-yellow-300 flex items-center gap-2">
              <i class="fa-solid fa-gamepad"></i> Active Skyblock Players (JAWA)
            </span>
            <span class="text-[11px] text-amber-200/75">Live 3D Heads</span>
          </div>
          <div id="sb-players-list" class="flex flex-wrap items-center gap-2">
            <span class="text-xs text-amber-200/75 italic">Syncing live Skyblock roster...</span>
          </div>
        </div>
      </section>

      <div class="mc-grass-divider my-2"></div>

      <!-- SKYBLOCK FEATURES & GAMEPLAY -->
      <section class="py-14 max-w-7xl mx-auto px-4 sm:px-6">
        <div class="text-center mb-10">
          <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-lg bg-sky-400/15 border border-sky-400/50 text-sky-300 text-xs font-extrabold uppercase tracking-widest mb-2">
            <i class="fa-solid fa-island-tropical"></i> Custom Skyblock Mechanics
          </div>
          <h2 class="font-pixel text-2xl sm:text-3xl text-white">
            SKYBLOCK <span class="text-yellow-300">FEATURES</span>
          </h2>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <div class="mc-panel p-6 rounded-3xl space-y-3">
            <div class="w-12 h-12 rounded-2xl bg-yellow-400/20 border-2 border-yellow-400/70 flex items-center justify-center text-yellow-300 text-xl">
              <i class="fa-solid fa-robot"></i>
            </div>
            <h3 class="font-silk font-bold text-lg text-white">Automated Minions</h3>
            <p class="text-xs sm:text-sm text-amber-100/85 leading-relaxed">
              Deploy Miner, Farmer, Slayer, and Lumberjack Minions that work 24/7 while you're offline—upgradeable with auto-smelters and compactors!
            </p>
          </div>

          <div class="mc-panel p-6 rounded-3xl space-y-3">
            <div class="w-12 h-12 rounded-2xl bg-sky-500/20 border-2 border-sky-400/70 flex items-center justify-center text-sky-300 text-xl">
              <i class="fa-solid fa-gem"></i>
            </div>
            <h3 class="font-silk font-bold text-lg text-white">Upgradable Ore Generators</h3>
            <p class="text-xs sm:text-sm text-amber-100/85 leading-relaxed">
              Level up your cobblestone generator to spawn Coal, Iron, Gold, Redstone, Lapis, Diamond, Emerald, and Ancient Debris blocks!
            </p>
          </div>

          <div class="mc-panel p-6 rounded-3xl space-y-3">
            <div class="w-12 h-12 rounded-2xl bg-emerald-500/20 border-2 border-emerald-400/70 flex items-center justify-center text-emerald-300 text-xl">
              <i class="fa-solid fa-ranking-star"></i>
            </div>
            <h3 class="font-silk font-bold text-lg text-white">Co-op Islands &amp; /is top</h3>
            <p class="text-xs sm:text-sm text-amber-100/85 leading-relaxed">
              Team up with friends using <code class="text-yellow-300">/is coop</code>, set up public player shops with <code class="text-yellow-300">/is warp</code>, and climb the <code class="text-yellow-300">/is top</code> leaderboard.
            </p>
          </div>
        </div>
      </section>

      <div class="mc-grass-divider my-2"></div>

      <!-- SKYBLOCK ISLAND RANKS & CRATE KEYS STORE -->
      <section class="py-14 max-w-7xl mx-auto px-4 sm:px-6">
        <div class="text-center max-w-3xl mx-auto mb-10 space-y-3">
          <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-lg bg-yellow-400/15 border border-yellow-400/55 text-yellow-300 text-xs font-extrabold uppercase tracking-widest">
            <i class="fa-solid fa-shield-halved"></i> Instant UPI Store &bull; 15% GST 3-Day Protection
          </div>
          <h2 class="font-pixel text-2xl sm:text-4xl text-white">
            SKYBLOCK RANKS &amp; <span class="text-yellow-300">ISLAND KITS</span>
          </h2>
          <p class="text-xs sm:text-sm text-amber-100/85 leading-relaxed">
            All Skyblock packages include <strong class="text-yellow-300">15% GST Insurance</strong> (3-day item/rank protection) and our <strong class="text-lime-300">3-Hour Unused/Undamaged Refund Policy</strong> via UPI (<code class="text-yellow-300">ghostmc.fund@ybl</code>).
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
          <!-- 1. Sprout Starter Pack -->
          <div class="mc-panel p-6 rounded-3xl flex flex-col justify-between space-y-4">
            <div class="space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-xs font-black uppercase px-2.5 py-1 rounded-lg bg-emerald-500/20 text-emerald-300 border border-emerald-400/50">Island Starter</span>
                <span class="text-xs font-mono text-amber-200">Base ₹30 + ₹5 GST</span>
              </div>
              <h3 class="font-silk font-bold text-xl text-white">Sprout Starter Pack</h3>
              <div class="flex items-baseline gap-2">
                <span class="font-pixel text-xl text-yellow-300">₹35</span>
                <span class="text-[11px] text-amber-200/80">incl. 15% GST</span>
              </div>
              <ul class="text-xs text-amber-100/85 space-y-1.5 pt-2 border-t border-yellow-500/20">
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>1x Cobblestone Miner Minion (Tier 1)</li>
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>2x Vote Crate Keys &amp; ₹5,000 In-Game Cash</li>
                <li><i class="fa-solid fa-shield text-amber-300 mr-1.5"></i>3-Day Protection Insurance (15% GST)</li>
                <li><i class="fa-solid fa-rotate-left text-lime-300 mr-1.5"></i>3-Hour Refund Policy (If Unused/Undamaged)</li>
              </ul>
            </div>
            <button type="button" onclick="openKitCheckout('Skyblock Sprout Starter Pack', 30, 5, 35, '1x Cobblestone Minion Tier 1, 2x Vote Keys & ₹5,000 In-Game Cash')" class="mc-btn w-full bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black py-3 rounded-xl text-xs uppercase tracking-wider">
              Buy Sprout Pack — ₹35
            </button>
          </div>

          <!-- 2. Sky Legend Island Kit -->
          <div class="mc-panel p-6 rounded-3xl flex flex-col justify-between space-y-4 border-2 border-yellow-300 shadow-[0_0_30px_rgba(255,214,10,0.25)]">
            <div class="space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-[10px] font-black uppercase px-2.5 py-1 rounded-lg bg-yellow-400 text-stone-950">Most Popular</span>
                <span class="text-xs font-mono text-amber-200">Base ₹40 + ₹6 GST</span>
              </div>
              <h3 class="font-silk font-bold text-xl text-yellow-300">Sky Legend Kit</h3>
              <div class="flex items-baseline gap-2">
                <span class="font-pixel text-xl text-white">₹46</span>
                <span class="text-[11px] text-amber-200/80">incl. 15% GST</span>
              </div>
              <ul class="text-xs text-amber-100/85 space-y-1.5 pt-2 border-t border-yellow-500/20">
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>Diamond Minion Tier 2 + Enchanted Diamond Tools</li>
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>2x Spawner Keys, 16x Golden Apples &amp; 16x Pearls</li>
                <li><i class="fa-solid fa-shield text-amber-300 mr-1.5"></i>3-Day Protection Insurance (15% GST)</li>
                <li><i class="fa-solid fa-rotate-left text-lime-300 mr-1.5"></i>3-Hour Refund Policy (If Unused/Undamaged)</li>
              </ul>
            </div>
            <button type="button" onclick="openKitCheckout('Skyblock Sky Legend Kit', 40, 6, 46, 'Diamond Minion Tier 2, Enchanted Diamond Tools, 2x Spawner Keys, 16x Golden Apples & 16x Pearls')" class="mc-btn w-full bg-gradient-to-b from-yellow-300 via-yellow-400 to-amber-500 text-stone-950 font-black py-3 rounded-xl text-xs uppercase tracking-wider">
              Buy Sky Legend Kit — ₹46
            </button>
          </div>

          <!-- 3. Island VIP Rank -->
          <div class="mc-panel p-6 rounded-3xl flex flex-col justify-between space-y-4">
            <div class="space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-xs font-black uppercase px-2.5 py-1 rounded-lg bg-sky-400/20 text-sky-300 border border-sky-400/50">Permanent Rank</span>
                <span class="text-xs font-mono text-amber-200">Base ₹60 + ₹9 GST</span>
              </div>
              <h3 class="font-silk font-bold text-xl text-white">Island VIP Rank</h3>
              <div class="flex items-baseline gap-2">
                <span class="font-pixel text-xl text-yellow-300">₹69</span>
                <span class="text-[11px] text-amber-200/80">incl. 15% GST</span>
              </div>
              <ul class="text-xs text-amber-100/85 space-y-1.5 pt-2 border-t border-yellow-500/20">
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i><code class="text-sky-300">/fly</code> on Your Own Island &amp; VIP Chat Tag</li>
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>3x Auction House Slots + Daily VIP Crate Key</li>
                <li><i class="fa-solid fa-shield text-amber-300 mr-1.5"></i>3-Day Protection Insurance (15% GST)</li>
                <li><i class="fa-solid fa-rotate-left text-lime-300 mr-1.5"></i>3-Hour Refund Policy (If Unused)</li>
              </ul>
            </div>
            <button type="button" onclick="openKitCheckout('Skyblock Island VIP Rank', 60, 9, 69, 'Island /fly, VIP Chat Prefix, 3x Auction House Slots & Daily VIP Key')" class="mc-btn w-full bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black py-3 rounded-xl text-xs uppercase tracking-wider">
              Buy VIP Rank — ₹69
            </button>
          </div>

          <!-- 4. Sky Lord Rank -->
          <div class="mc-panel p-6 rounded-3xl flex flex-col justify-between space-y-4">
            <div class="space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-xs font-black uppercase px-2.5 py-1 rounded-lg bg-purple-500/20 text-purple-300 border border-purple-400/50">Elite Rank</span>
                <span class="text-xs font-mono text-amber-200">Base ₹110 + ₹17 GST</span>
              </div>
              <h3 class="font-silk font-bold text-xl text-white">Sky Lord Rank</h3>
              <div class="flex items-baseline gap-2">
                <span class="font-pixel text-xl text-yellow-300">₹127</span>
                <span class="text-[11px] text-amber-200/80">incl. 15% GST</span>
              </div>
              <ul class="text-xs text-amber-100/85 space-y-1.5 pt-2 border-t border-yellow-500/20">
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i><code class="text-sky-300">/fly</code>, <code class="text-sky-300">/feed</code>, <code class="text-sky-300">/workbench</code> &amp; Sky Lord Tag</li>
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>2x Minion Speed Booster + 5x Auction Slots</li>
                <li><i class="fa-solid fa-shield text-amber-300 mr-1.5"></i>3-Day Protection Insurance (15% GST)</li>
                <li><i class="fa-solid fa-rotate-left text-lime-300 mr-1.5"></i>3-Hour Refund Policy (If Unused)</li>
              </ul>
            </div>
            <button type="button" onclick="openKitCheckout('Skyblock Sky Lord Rank', 110, 17, 127, '/fly, /feed, /workbench, 2x Minion Speed Booster & 5x Auction Slots')" class="mc-btn w-full bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black py-3 rounded-xl text-xs uppercase tracking-wider">
              Buy Sky Lord — ₹127
            </button>
          </div>

          <!-- 5. Pineapple Emperor Rank -->
          <div class="mc-panel p-6 rounded-3xl flex flex-col justify-between space-y-4 md:col-span-2">
            <div class="space-y-3">
              <div class="flex items-center justify-between">
                <span class="text-xs font-black uppercase px-2.5 py-1 rounded-lg bg-amber-500/25 text-yellow-300 border border-yellow-400/60">Supreme Island Rank</span>
                <span class="text-xs font-mono text-amber-200">Base ₹160 + ₹24 GST</span>
              </div>
              <h3 class="font-silk font-bold text-xl text-yellow-300">Pineapple Emperor Rank</h3>
              <div class="flex items-baseline gap-2">
                <span class="font-pixel text-xl text-white">₹184</span>
                <span class="text-[11px] text-amber-200/80">incl. 15% GST</span>
              </div>
              <ul class="text-xs text-amber-100/85 space-y-1.5 pt-2 border-t border-yellow-500/20">
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>Permanent Island <code class="text-sky-300">/fly</code>, <code class="text-sky-300">/anvil</code>, <code class="text-sky-300">/ec</code> &amp; Custom Island Biome Selector</li>
                <li><i class="fa-solid fa-check text-yellow-300 mr-1.5"></i>3x Mythic Crate Keys + 10x Auction House Slots + Emperor Golden Prefix</li>
                <li><i class="fa-solid fa-shield text-amber-300 mr-1.5"></i>3-Day Protection Insurance (15% GST) &bull; 3-Hour Refund Policy (If Unused)</li>
              </ul>
            </div>
            <button type="button" onclick="openKitCheckout('Skyblock Pineapple Emperor Rank', 160, 24, 184, 'Permanent Island /fly, /anvil, /ec, Custom Biome Selector, 3x Mythic Keys & Emperor Prefix')" class="mc-btn w-full bg-gradient-to-b from-yellow-300 via-yellow-400 to-amber-500 text-stone-950 font-black py-3 rounded-xl text-xs uppercase tracking-wider">
              Buy Pineapple Emperor — ₹184
            </button>
          </div>
        </div>
      </section>

      <div class="mc-grass-divider my-2"></div>

      <!-- SKYBLOCK HOW TO JOIN (JAVA EDITION ONLY) -->
      <section class="py-14 max-w-5xl mx-auto px-4 sm:px-6">
        <div class="text-center mb-8">
          <h2 class="font-pixel text-2xl sm:text-3xl text-white">
            HOW TO JOIN <span class="text-yellow-300">SKYBLOCK (JAWA)</span>
          </h2>
        </div>

        <div class="mc-panel p-6 sm:p-8 rounded-3xl border-2 border-sky-400/70 space-y-5">
          <div class="flex flex-wrap items-center justify-between gap-2">
            <h3 class="font-silk font-bold text-lg sm:text-xl text-yellow-300 flex items-center gap-2">
              <i class="fa-solid fa-desktop text-sky-400"></i> Minecraft Java Edition (JAWA Only)
            </h3>
            <span class="text-[11px] font-black uppercase px-3 py-1 rounded-lg bg-yellow-400 text-stone-950">MC Java 1.20 – 1.21+</span>
          </div>

          <ol class="text-xs sm:text-sm text-amber-100/90 space-y-2.5 list-decimal list-inside">
            <li>Launch <strong>Minecraft Java Edition (PC)</strong> and click <strong>Multiplayer</strong>.</li>
            <li>Click <strong>Add Server</strong> and enter Server Name: <strong class="text-yellow-300">Pineapple Skyblock</strong>.</li>
            <li>Paste Server Address: <code class="text-yellow-300 font-mono bg-stone-950 px-2 py-0.5 rounded border border-yellow-500/30">pineappleskyblock.playgg.pro:25127</code></li>
            <li>Click <strong>Done</strong> &rarr; <strong>Join Server</strong>, then type <code class="text-sky-300 font-mono">/is create</code> to spawn your floating island!</li>
          </ol>

          <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 pt-2">
            <button type="button" onclick="copyToClipboard('pineappleskyblock.playgg.pro:25127', 'Copied Skyblock IP: pineappleskyblock.playgg.pro:25127')" class="mc-btn bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black py-3 px-4 rounded-xl text-xs uppercase tracking-wider">
              <i class="fa-regular fa-copy mr-1.5"></i> Copy IP: pineappleskyblock.playgg.pro:25127
            </button>
            <button type="button" onclick="copyToClipboard('25127', 'Copied Skyblock Port: 25127')" class="mc-btn bg-stone-900 hover:bg-stone-800 text-sky-300 font-bold py-3 px-4 rounded-xl text-xs uppercase tracking-wider">
              <i class="fa-regular fa-copy mr-1.5"></i> Copy Port: 25127
            </button>
          </div>
        </div>
      </section>
    </div>

    <div class="mc-grass-divider my-2"></div>

    <!-- ===================================================================== -->
    <!-- SHARED COMMUNITY SECTIONS (PARTNERS, FUNDERS, AI BOT, FOUNDER DISCORD) -->
    <!-- ===================================================================== -->

    <!-- OFFICIAL PARTNERSHIPS SECTION -->
    <section id="partners" class="py-14 max-w-6xl mx-auto px-4 sm:px-6">
      <div class="text-center mb-8">
        <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-lg bg-yellow-400/15 border border-yellow-400/50 text-yellow-300 text-xs font-extrabold uppercase tracking-widest mb-2">
          <i class="fa-solid fa-handshake"></i> Community Network
        </div>
        <h2 class="font-pixel text-2xl sm:text-3xl text-white">
          OFFICIAL <span class="text-yellow-300">PARTNERSHIPS</span>
        </h2>
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-6">
        <div class="lg:col-span-2 mc-panel p-6 sm:p-8 rounded-3xl flex flex-col sm:flex-row items-center gap-6 border-2 border-yellow-400/70">
          <div class="w-20 h-20 rounded-2xl bg-gradient-to-br from-yellow-300 to-amber-500 p-3 flex items-center justify-center shrink-0 shadow-lg">
            <svg viewBox="0 0 64 64" class="w-full h-full" xmlns="http://www.w3.org/2000/svg">
              <path d="M32 6 L54 16 V32 C54 46 44 55 32 59 C20 55 10 46 10 32 V16 Z" fill="#181205" stroke="#FEF08A" stroke-width="3"/>
              <path d="M22 33 L29 40 L43 24" stroke="#FACC15" stroke-width="5" fill="none" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
          <div class="text-center sm:text-left space-y-2">
            <div class="inline-flex items-center gap-1.5 px-3 py-0.5 rounded-full bg-lime-400/20 border border-lime-400/50 text-lime-300 text-[10px] font-black uppercase tracking-widest">
              <i class="fa-solid fa-certificate"></i> Official Alliance
            </div>
            <h3 class="font-silk font-bold text-xl sm:text-2xl text-white">
              Partnership with <span class="text-yellow-300">Friends SMP</span>
            </h3>
            <p class="text-xs sm:text-sm text-amber-100/85 leading-relaxed">
              PineappleSMP is proudly partnered with <strong class="text-yellow-300">Friends SMP</strong> to bring joint community tournaments, cross-server events, and friendly survival rivalries to our players.
            </p>
          </div>
        </div>

        <div class="mc-panel p-6 rounded-3xl flex flex-col justify-between space-y-4">
          <div class="space-y-2">
            <h3 class="font-silk font-bold text-lg text-white">Want to Partner?</h3>
            <p class="text-xs text-amber-100/80 leading-relaxed">
              Have an active Minecraft SMP, Discord community, or YouTube channel? Open a partnership ticket on our Discord server!
            </p>
          </div>
          <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="mc-btn bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black py-3 px-4 rounded-xl text-xs text-center uppercase tracking-wider">
            Open Partnership Ticket
          </a>
        </div>
      </div>
    </section>

    <div class="mc-grass-divider my-2"></div>

    <!-- SERVER FUNDERS HALL OF HONOR -->
    <section id="funders" class="py-14 max-w-5xl mx-auto px-4 sm:px-6">
      <div class="text-center mb-8">
        <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-lg bg-yellow-400/15 border border-yellow-400/50 text-yellow-300 text-xs font-extrabold uppercase tracking-widest mb-2">
          <i class="fa-solid fa-crown"></i> Hall of Honor
        </div>
        <h2 class="font-pixel text-2xl sm:text-3xl text-white">
          SERVER <span class="text-yellow-300">FUNDERS</span>
        </h2>
        <p class="text-xs sm:text-sm text-amber-100/80 mt-1">
          Honoring the generous supporters powering PineappleSMP &amp; VitalCloud hosting.
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 max-w-3xl mx-auto">
        <div class="mc-panel p-6 rounded-3xl border-2 border-yellow-300/85 flex items-center gap-4 shadow-[0_0_25px_rgba(255,214,10,0.2)]">
          <img src="https://mc-heads.net/avatar/flaxxy444/64" alt="flaxxy444" class="w-16 h-16 rounded-2xl border-2 border-yellow-300 bg-stone-900 shrink-0" onerror="this.onerror=null;this.src='data:image/svg+xml;utf8,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 64 64%22><rect width=%2264%22 height=%2264%22 fill=%22%23FACC15%22/><rect x=%2216%22 y=%2222%22 width=%2210%22 height=%2210%22 fill=%22%2309090B%22/><rect x=%2238%22 y=%2222%22 width=%2210%22 height=%2210%22 fill=%22%2309090B%22/><rect x=%2222%22 y=%2242%22 width=%2220%22 height=%226%22 fill=%22%23451A03%22/></svg>'">
          <div>
            <div class="inline-flex items-center gap-1.5 px-2.5 py-0.5 rounded-full bg-yellow-400 text-stone-950 text-[10px] font-black uppercase tracking-wider mb-1">
              <i class="fa-solid fa-crown"></i> Founding Funder
            </div>
            <h3 class="font-pixel text-lg sm:text-xl text-white">flaxxy444</h3>
            <p class="text-xs text-amber-200/80 mt-0.5">Official Season 1 Supporter</p>
          </div>
        </div>

        <div class="mc-panel p-6 rounded-3xl flex flex-col justify-between space-y-3">
          <div>
            <h3 class="font-silk font-bold text-lg text-white">Become a Funder</h3>
            <p class="text-xs text-amber-100/80 mt-1">
              Support PineappleSMP server upgrades and get featured permanently in our Hall of Honor!
            </p>
          </div>
          <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="mc-btn bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black py-2.5 px-4 rounded-xl text-xs text-center uppercase tracking-wider">
            Support on Discord
          </a>
        </div>
      </div>
    </section>

    <div class="mc-grass-divider my-2"></div>

    <!-- PINEAPPLEBOT AI SUPPORT ASSISTANT (ENGLISH / HINDI / HINGLISH) -->
    <section id="ai-support" class="py-14 max-w-5xl mx-auto px-4 sm:px-6">
      <div class="text-center mb-8">
        <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-lg bg-yellow-400/15 border border-yellow-400/55 text-yellow-300 text-xs font-extrabold uppercase tracking-widest mb-3">
          <i class="fa-solid fa-robot"></i> 24/7 Smart Error Diagnostics &amp; Server Helper
        </div>
        <h2 class="font-pixel text-2xl sm:text-4xl text-white">
          PINEAPPLEBOT <span class="text-yellow-300">AI SUPPORT</span>
        </h2>
        <p class="text-xs sm:text-sm text-amber-100/85 mt-2">
          Ask about Lifesteal or Skyblock IPs, connection errors, kits, or chat casually in <strong>English</strong>, <strong>Hindi</strong>, or <strong>Hinglish</strong>.
        </p>
      </div>

      <div class="mc-panel rounded-3xl border-2 border-yellow-400/80 overflow-hidden">
        <div class="bg-[#231A07] px-4 sm:px-6 py-3.5 border-b-2 border-yellow-500/35 flex flex-wrap items-center justify-between gap-3">
          <div class="flex items-center gap-2.5">
            <div class="w-9 h-9 rounded-xl bg-yellow-400 text-stone-950 flex items-center justify-center font-black">
              <i class="fa-solid fa-wand-magic-sparkles"></i>
            </div>
            <div>
              <div class="font-silk font-bold text-sm text-white">PineappleBot AI</div>
              <div class="text-[11px] text-lime-300 font-semibold">Online &bull; Lifesteal &amp; Skyblock Aware</div>
            </div>
          </div>

          <div class="flex items-center gap-1.5 bg-stone-950 p-1 rounded-xl border border-yellow-500/40" role="group" aria-label="AI Response Language">
            <button type="button" onclick="setAiLanguage('English')" id="lang-btn-English" class="px-3 py-1 rounded-lg text-xs font-black bg-yellow-400 text-stone-950 transition-all cursor-pointer">English</button>
            <button type="button" onclick="setAiLanguage('Hindi')" id="lang-btn-Hindi" class="px-3 py-1 rounded-lg text-xs font-bold text-amber-200 hover:text-white transition-all cursor-pointer">Hindi</button>
            <button type="button" onclick="setAiLanguage('Hinglish')" id="lang-btn-Hinglish" class="px-3 py-1 rounded-lg text-xs font-bold text-amber-200 hover:text-white transition-all cursor-pointer">Hinglish</button>
          </div>
        </div>

        <div class="px-4 sm:px-6 py-2.5 bg-[#161105] border-b border-yellow-500/25 flex flex-wrap items-center gap-2">
          <span class="text-[10px] font-extrabold uppercase text-amber-300">Quick Help:</span>
          <button type="button" onclick="sendQuickAiPrompt('How do I join Pineapple Skyblock?')" class="text-[11px] px-2.5 py-1 rounded-lg bg-stone-900 hover:bg-stone-800 text-sky-300 border border-sky-500/35 cursor-pointer">Skyblock IP &amp; Port</button>
          <button type="button" onclick="sendQuickAiPrompt('Unable to connect to world / Connection timed out error')" class="text-[11px] px-2.5 py-1 rounded-lg bg-stone-900 hover:bg-stone-800 text-amber-100 border border-yellow-500/30 cursor-pointer">Connection Timed Out</button>
          <button type="button" onclick="sendQuickAiPrompt('What is in Legend Kit and how does 3-hour refund work?')" class="text-[11px] px-2.5 py-1 rounded-lg bg-stone-900 hover:bg-stone-800 text-amber-100 border border-yellow-500/30 cursor-pointer">Legend Kit &amp; Refund</button>
          <button type="button" onclick="sendQuickAiPrompt('When is the next PvP Event?')" class="text-[11px] px-2.5 py-1 rounded-lg bg-stone-900 hover:bg-stone-800 text-amber-100 border border-yellow-500/30 cursor-pointer">29 Nov PvP Event</button>
        </div>

        <div id="ai-chat-messages" class="p-4 sm:p-6 h-[320px] overflow-y-auto custom-scroll space-y-3.5 bg-[#0B0802]">
          <div class="flex items-start gap-3">
            <div class="w-8 h-8 rounded-xl bg-yellow-400 text-stone-950 flex items-center justify-center font-black text-xs shrink-0 mt-0.5">AI</div>
            <div class="bg-[#1C1506] border border-yellow-500/40 rounded-2xl rounded-tl-none p-3.5 text-xs sm:text-sm text-amber-50 max-w-[85%] space-y-2">
              <p>Welcome to <strong>PineappleSMP</strong>! Ask me about <strong>Lifesteal SMP</strong> or our new <strong>Java-Only Skyblock</strong> (<code class="text-yellow-300">pineappleskyblock.playgg.pro:25127</code>), kits, or any connection errors.</p>
            </div>
          </div>
        </div>

        <div class="p-4 bg-[#140F04] border-t border-yellow-500/30 space-y-2.5">
          <form onsubmit="handleAiSubmit(event)" class="flex items-center gap-2">
            <input type="text" id="ai-user-input" placeholder="Describe an error or chat with PineappleBot..." class="flex-1 bg-stone-950 border border-yellow-500/45 focus:border-yellow-300 rounded-xl px-4 py-3 text-xs sm:text-sm text-white outline-none">
            <button type="submit" id="ai-send-btn" class="mc-btn bg-gradient-to-b from-yellow-300 to-amber-500 text-stone-950 font-black px-5 py-3 rounded-xl text-xs uppercase tracking-wider shrink-0">
              Send <i class="fa-solid fa-paper-plane ml-1"></i>
            </button>
          </form>
          <div class="flex flex-wrap items-center justify-between gap-2 text-[11px] text-amber-200/75">
            <span>Selected Language: <strong id="ai-current-lang-label" class="text-yellow-300">English</strong></span>
            <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="text-yellow-300 hover:text-white font-bold">
              <i class="fa-brands fa-discord text-indigo-400 mr-1"></i>Issue not solved? Create Ticket on Discord &rarr;
            </a>
          </div>
        </div>
      </div>
    </section>

    <div class="mc-grass-divider my-2"></div>

    <!-- FOUNDER DISCORD PROFILE SHOWCASE BOX (devesh_37.) -->
    <section id="founder-discord" class="py-12 max-w-4xl mx-auto px-4 sm:px-6">
      <div class="mc-panel rounded-3xl p-5 sm:p-7 border-2 border-yellow-400/75 relative">
        <div class="flex flex-col sm:flex-row items-center sm:items-start justify-between gap-5">
          <div class="flex flex-col sm:flex-row items-center sm:items-start gap-4 text-center sm:text-left">
            <div class="relative shrink-0">
              <img id="founder-discord-pfp" src="https://cdn.discordapp.com/embed/avatars/0.png" alt="devesh_37." class="w-20 h-20 rounded-2xl border-2 border-yellow-300 object-cover bg-stone-900" onerror="this.onerror=null;this.src='data:image/svg+xml;utf8,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 80 80%22><rect width=%2280%22 height=%2280%22 fill=%22%231C1404%22/><rect x=%2220%22 y=%2222%22 width=%2240%22 height=%2242%22 rx=%226%22 fill=%22%23FACC15%22/><polygon points=%2218,30 38,32 37,43 20,42%22 fill=%22%2309090B%22/><polygon points=%2242,32 62,30 60,42 43,43%22 fill=%22%2309090B%22/><path d=%22M32 52 Q40 57 48 51%22 stroke=%22%23451A03%22 stroke-width=%223%22 fill=%22none%22/></svg>'">
              <span id="founder-discord-status-dot" class="w-4 h-4 rounded-full bg-lime-400 border-2 border-stone-950 absolute -bottom-1 -right-1" title="Live Discord Status"></span>
            </div>

            <div class="space-y-1.5">
              <div class="inline-flex items-center gap-1.5 px-2.5 py-0.5 rounded-full bg-indigo-500/20 border border-indigo-400/50 text-indigo-300 text-[10px] font-black uppercase tracking-wider">
                <i class="fa-brands fa-discord"></i> Founder &amp; Developer
              </div>
              <div class="flex flex-wrap items-center justify-center sm:justify-start gap-2">
                <h3 id="founder-discord-displayname" class="font-silk font-bold text-xl text-white">Devesh</h3>
                <button type="button" onclick="copyToClipboard('devesh_37.', 'Copied Discord Username: devesh_37.')" class="font-mono text-xs bg-stone-950 hover:bg-stone-900 text-yellow-300 px-2.5 py-1 rounded-lg border border-yellow-500/40 inline-flex items-center gap-1.5 cursor-pointer">
                  <span>devesh_37.</span>
                  <i class="fa-regular fa-copy text-[10px]"></i>
                </button>
              </div>
              <p id="founder-discord-bio" class="text-xs sm:text-sm text-amber-100/85 max-w-xl">
                Founder &amp; Creator of PineappleSMP &bull; Building Season 1 Lifesteal, Skyblock &amp; VitalCloud network.
              </p>
              <div id="founder-discord-activity" class="text-[11px] font-mono text-yellow-300/90">
                <i class="fa-solid fa-circle-dot text-lime-400 mr-1"></i>Live Sync Active &bull; Discord: devesh_37.
              </div>
            </div>
          </div>

          <div class="flex sm:flex-col items-center sm:items-end gap-2 shrink-0">
            <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="mc-btn bg-gradient-to-b from-indigo-500 to-indigo-700 text-white font-bold px-3.5 py-2 rounded-xl text-xs">
              Message on Discord
            </a>
          </div>
        </div>
      </div>
    </section>

  </main>

  <!-- FOOTER WITH BOX PINEAPPLE LOGO & "POWERED BY DEVESH" WATERMARK -->
  <footer class="relative bg-[#090702] border-t-2 border-yellow-500/40 pt-10 pb-12 px-4 sm:px-6 text-center overflow-hidden">
    <div class="pointer-events-none absolute inset-x-0 bottom-0 h-44 bg-gradient-to-t from-yellow-400/15 via-amber-500/5 to-transparent"></div>

    <div class="relative max-w-6xl mx-auto flex flex-col items-center space-y-5">
      <div class="flex items-center gap-3">
        <div class="w-10 h-10 rounded-xl bg-gradient-to-br from-yellow-300 via-amber-400 to-amber-600 p-1 border border-yellow-200 shadow-[0_0_16px_rgba(255,214,10,0.4)]">
          <svg viewBox="0 0 64 64" class="w-full h-full" xmlns="http://www.w3.org/2000/svg" aria-label="PineappleSMP Footer Emblem Logo">
            <polygon points="32,2 58,12 54,48 32,62 10,48 6,12" fill="#1C1404" stroke="#FDE047" stroke-width="2.5"/>
            <polygon points="32,3 25,17 39,17" fill="#16A34A"/>
            <polygon points="32,4 28,17 36,17" fill="#22C55E"/>
            <polygon points="18,8 17,19 28,17" fill="#16A34A"/>
            <polygon points="46,8 36,17 47,19" fill="#15803D"/>
            <rect x="16" y="17" width="32" height="36" rx="4" fill="#FACC15" stroke="#451A03" stroke-width="2.2"/>
            <rect x="41" y="18" width="6" height="34" rx="2" fill="#B45309" opacity="0.45"/>
            <polygon points="14,23 30,24.5 29,34 15.5,33" fill="#09090B" stroke="#000000" stroke-width="1.6"/>
            <polygon points="34,24.5 50,23 48.5,33 35,34" fill="#09090B" stroke="#000000" stroke-width="1.6"/>
            <rect x="29.5" y="24.5" width="5" height="2.8" fill="#09090B"/>
            <polygon points="17,25 21.5,25 18.5,32 15.5,32" fill="#FFFFFF" opacity="0.45"/>
            <polygon points="37,25 41.5,25 38.5,32 35.5,32" fill="#FFFFFF" opacity="0.45"/>
            <path d="M26 43 Q32 47 38 42" stroke="#451A03" stroke-width="2.4" fill="none" stroke-linecap="round"/>
          </svg>
        </div>
        <span class="font-silk font-bold text-lg text-white tracking-wider">PINEAPPLE <span class="text-yellow-300">SMP</span></span>
      </div>

      <div class="flex flex-wrap items-center justify-center gap-3 sm:gap-4 text-xs text-amber-200/85">
        <span>Lifesteal Java: <strong class="text-yellow-300 font-mono">basic.vitalcloud.in:19126</strong></span>
        <span class="text-yellow-500/50">&bull;</span>
        <span>Lifesteal Bedrock: <strong class="text-yellow-300 font-mono">basic.vitalcloud.in:19149</strong></span>
        <span class="text-yellow-500/50">&bull;</span>
        <span>Skyblock (JAWA Only): <strong class="text-sky-300 font-mono">pineappleskyblock.playgg.pro:25127</strong></span>
        <span class="text-yellow-500/50">&bull;</span>
        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="text-indigo-300 hover:text-white font-bold transition-colors">
          <i class="fa-brands fa-discord mr-1"></i>discord.gg/Vp9Ss592cq
        </a>
      </div>

      <!-- SIMPLE & SMOOTH MOVING "POWERED BY DEVESH" WATERMARK TEXT -->
      <div class="w-full pt-5 mt-2 border-t border-yellow-500/25 flex justify-center items-center select-none">
        <span class="animate-watermark-text font-silk font-bold text-base sm:text-xl tracking-[0.26em] uppercase text-transparent bg-clip-text bg-gradient-to-r from-yellow-200 via-yellow-400 to-amber-500">
          POWERED BY DEVESH
        </span>
      </div>
    </div>
  </footer>

  <!-- UPI KIT CHECKOUT MODAL (ghostmc.fund@ybl) -->
  <div id="kit-checkout-modal" class="hidden fixed inset-0 z-50 bg-black/80 backdrop-blur-sm flex items-center justify-center p-4">
    <div class="mc-panel w-full max-w-md rounded-3xl border-2 border-yellow-300 overflow-hidden shadow-2xl">
      <div class="bg-[#231A07] px-5 py-4 border-b border-yellow-500/35 flex items-center justify-between">
        <div>
          <div class="text-[10px] font-pixel text-yellow-300 uppercase">Instant UPI Checkout</div>
          <h3 id="checkout-kit-title" class="font-silk font-bold text-lg text-white mt-0.5">Buy Legend Kit</h3>
        </div>
        <button type="button" onclick="closeKitCheckout()" class="w-8 h-8 rounded-xl bg-stone-950 text-amber-200 hover:text-white flex items-center justify-center cursor-pointer">
          <i class="fa-solid fa-xmark"></i>
        </button>
      </div>

      <div class="p-5 space-y-4 max-h-[82vh] overflow-y-auto custom-scroll text-xs">
        <div class="bg-stone-950/90 border border-yellow-500/35 rounded-2xl p-3.5 space-y-1.5">
          <div class="flex justify-between text-amber-100">
            <span>Package Base Price:</span>
            <span id="checkout-base-price" class="font-mono font-bold">₹40</span>
          </div>
          <div class="flex justify-between text-amber-200">
            <span>15% GST (3-Day Protection Insurance):</span>
            <span id="checkout-gst-price" class="font-mono font-bold">₹6</span>
          </div>
          <div class="flex justify-between text-yellow-300 text-sm font-black pt-1.5 border-t border-yellow-500/25">
            <span>Total Payable:</span>
            <span id="checkout-total-price" class="font-mono">₹46</span>
          </div>
        </div>

        <div class="bg-[#161105] border border-yellow-500/30 rounded-xl p-3 text-amber-100/90">
          <span class="font-bold text-yellow-300">Package Details: </span>
          <span id="checkout-kit-desc">Includes Prot 3 Diamond Armour &amp; more.</span>
        </div>

        <div class="flex flex-col items-center bg-white p-3.5 rounded-2xl">
          <img id="checkout-qr-img" src="" alt="Scan UPI QR Code" class="w-40 h-40 object-contain" onerror="this.onerror=null;this.src='data:image/svg+xml;utf8,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 160 160%22><rect width=%22160%22 height=%22160%22 fill=%22%23FEF9C3%22/><text x=%2280%22 y=%2274%22 font-family=%22sans-serif%22 font-size=%2212%22 font-weight=%22bold%22 text-anchor=%22middle%22 fill=%22%23451A03%22>UPI ID:</text><text x=%2280%22 y=%2294%22 font-family=%22monospace%22 font-size=%2212%22 font-weight=%22bold%22 text-anchor=%22middle%22 fill=%22%2309090B%22>ghostmc.fund@ybl</text></svg>'">
          <div class="text-[11px] font-bold text-stone-800 mt-1">Scan with GPay / PhonePe / Paytm</div>
        </div>

        <div class="flex items-center justify-between bg-stone-950 border border-yellow-400/50 rounded-xl px-3.5 py-2.5">
          <div>
            <div class="text-[10px] uppercase text-amber-300 font-bold">Official UPI ID</div>
            <div class="font-mono font-bold text-sm text-white">ghostmc.fund@ybl</div>
          </div>
          <button type="button" onclick="copyToClipboard('ghostmc.fund@ybl', 'Copied UPI ID: ghostmc.fund@ybl')" class="px-3 py-1.5 rounded-lg bg-yellow-400 text-stone-950 font-black text-xs cursor-pointer">
            Copy UPI
          </button>
        </div>

        <a id="checkout-upi-deeplink" href="upi://pay?pa=ghostmc.fund@ybl&pn=PineappleSMP&cu=INR" class="mc-btn block w-full bg-gradient-to-b from-lime-400 to-emerald-600 text-stone-950 font-black py-3 rounded-xl text-center uppercase tracking-wider">
          <i class="fa-solid fa-mobile-screen-button mr-1.5"></i>Pay Directly via UPI App
        </a>

        <div class="bg-amber-500/15 border border-yellow-400/60 rounded-2xl p-3.5 space-y-1.5 text-amber-100">
          <div class="font-black text-yellow-300 uppercase text-[11px]">
            <i class="fa-solid fa-triangle-exclamation mr-1"></i>Important Delivery &amp; Refund Rules:
          </div>
          <p>1. After paying, <strong>take a screenshot of the transaction</strong> and create a ticket on our Discord (<a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="underline text-yellow-300 font-bold">discord.gg/Vp9Ss592cq</a>) to claim your item/rank.</p>
          <p>2. <strong>15% GST Insurance:</strong> Covers damage/protection for 3 days.</p>
          <p>3. <strong>3-Hour Refund Policy:</strong> Refunds are only valid within 3 hours of purchase if the kit/rank is completely unused/undamaged.</p>
        </div>
      </div>
    </div>
  </div>

  <!-- FLOATING TOAST NOTIFICATION -->
  <div id="toast" class="fixed bottom-5 right-5 z-50 translate-y-24 opacity-0 transition-all duration-300 pointer-events-none">
    <div class="bg-stone-950 border-2 border-yellow-400 text-yellow-300 px-4 py-3 rounded-2xl shadow-2xl flex items-center gap-2.5 text-xs font-extrabold">
      <i class="fa-solid fa-circle-check text-lime-400 text-sm"></i>
      <span id="toast-text">Copied!</span>
    </div>
  </div>

  <!-- SELF-CONTAINED NON-BLOCKING APPLICATION SCRIPT -->
  <script>
    // Lifesteal Endpoints
    const SERVER_IP = "basic.vitalcloud.in";
    const JAVA_PORT = 19126;
    const BEDROCK_PORT = 19149;
    const JAVA_FULL_ADDRESS = `${SERVER_IP}:${JAVA_PORT}`;
    const BEDROCK_FULL_ADDRESS = `${SERVER_IP}:${BEDROCK_PORT}`;

    // Skyblock Endpoints (Player Display IP vs Backend VitalCloud API IP)
    const SKYBLOCK_DISPLAY_ADDRESS = "pineappleskyblock.playgg.pro:25127";
    const SKYBLOCK_API_ADDRESS = "free-in-1.vitalcloud.in:25127";

    const DISCORD_INVITE = "https://discord.gg/Vp9Ss592cq";
    const UPI_ID = "ghostmc.fund@ybl";

    let currentGamemode = 'lifesteal';

    function switchGamemode(mode) {
      currentGamemode = mode === 'skyblock' ? 'skyblock' : 'lifesteal';
      const lsPortal = document.getElementById('portal-lifesteal');
      const sbPortal = document.getElementById('portal-skyblock');
      const subtitle = document.getElementById('nav-brand-subtitle');
      const navIpText = document.getElementById('nav-quick-ip-text');
      const eventsLink = document.getElementById('nav-link-events');

      if (currentGamemode === 'skyblock') {
        document.body.classList.add('mode-skyblock');
        if (lsPortal) lsPortal.classList.add('hidden');
        if (sbPortal) sbPortal.classList.remove('hidden');
        if (subtitle) subtitle.textContent = 'SKYBLOCK (JAWA ONLY)';
        if (navIpText) navIpText.textContent = SKYBLOCK_DISPLAY_ADDRESS;
        if (eventsLink) eventsLink.classList.add('hidden');
        fetchSkyblockStatus(false);
        showToast('Switched to Pineapple Skyblock (Java Only)');
      } else {
        document.body.classList.remove('mode-skyblock');
        if (sbPortal) sbPortal.classList.add('hidden');
        if (lsPortal) lsPortal.classList.remove('hidden');
        if (subtitle) subtitle.textContent = 'LIFESTEAL SMP';
        if (navIpText) navIpText.textContent = JAVA_FULL_ADDRESS;
        if (eventsLink) eventsLink.classList.remove('hidden');
        fetchLiveServerStatus(false);
        showToast('Switched to Lifesteal SMP');
      }
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    function copyCurrentModePrimaryIp() {
      if (currentGamemode === 'skyblock') {
        copyToClipboard(SKYBLOCK_DISPLAY_ADDRESS, `Copied Skyblock IP: ${SKYBLOCK_DISPLAY_ADDRESS}`);
      } else {
        copyToClipboard(JAVA_FULL_ADDRESS, `Copied Java IP: ${JAVA_FULL_ADDRESS}`);
      }
    }

    async function fetchWithTimeout(url, options = {}, timeoutMs = 3500) {
      const controller = new AbortController();
      const id = setTimeout(() => controller.abort(), timeoutMs);
      try {
        const response = await fetch(url, { ...options, signal: controller.signal });
        clearTimeout(id);
        return response;
      } catch (err) {
        clearTimeout(id);
        throw err;
      }
    }

    function escapeHtml(str) {
      return String(str)
        .replace(/&/g, "&amp;")
        .replace(/</g, "&lt;")
        .replace(/>/g, "&gt;")
        .replace(/"/g, "&quot;")
        .replace(/'/g, "&#039;");
    }

    function formatNowTime() {
      return new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit', second: '2-digit' });
    }

    let toastTimer = null;
    function showToast(msg) {
      const toastEl = document.getElementById('toast');
      const textEl = document.getElementById('toast-text');
      if (!toastEl || !textEl) return;
      textEl.textContent = msg;
      toastEl.classList.remove('translate-y-24', 'opacity-0');
      toastEl.classList.add('translate-y-0', 'opacity-100');
      if (toastTimer) clearTimeout(toastTimer);
      toastTimer = setTimeout(() => {
        toastEl.classList.add('translate-y-24', 'opacity-0');
        toastEl.classList.remove('translate-y-0', 'opacity-100');
      }, 2800);
    }

    function copyToClipboard(text, successMsg) {
      try {
        const ta = document.createElement('textarea');
        ta.value = text;
        ta.setAttribute('readonly', '');
        ta.style.position = 'fixed';
        ta.style.opacity = '0';
        document.body.appendChild(ta);
        ta.select();
        document.execCommand('copy');
        document.body.removeChild(ta);
        showToast(successMsg || `Copied: ${text}`);
      } catch (e) {
        showToast(`Copy: ${text}`);
      }
    }

    // =========================================================================
    // LIFESTEAL LIVE SERVER TELEMETRY (AUTO-REFRESH EVERY 5 SECONDS)
    // =========================================================================
    function renderPlayersUI(players, isOnline, onlineCount) {
      const cardList = document.getElementById('card-players-list');
      if (!cardList) return;
      const fallbackAvatar = "data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24'><rect width='24' height='24' fill='%23FACC15'/><rect x='5' y='8' width='4' height='4' fill='%2309090B'/><rect x='15' y='8' width='4' height='4' fill='%2309090B'/></svg>";

      if (!isOnline) {
        cardList.innerHTML = `<span class="text-xs text-rose-300/85 italic">Server offline or starting up</span>`;
        return;
      }

      if (!players.length) {
        const msg = onlineCount > 0 ? `${onlineCount} player(s) online` : '0 players online right now';
        cardList.innerHTML = `<span class="text-xs text-amber-200/75 italic">${escapeHtml(msg)}</span>`;
        return;
      }

      cardList.innerHTML = players.map(p => `
        <span class="inline-flex items-center gap-1.5 px-2.5 py-1 rounded-lg bg-stone-950 border border-yellow-400/45 text-xs text-white font-mono">
          <img src="https://mc-heads.net/avatar/${encodeURIComponent(p.name)}/32" alt="${escapeHtml(p.name)}" class="w-4 h-4 rounded-sm" onerror="this.onerror=null;this.src='${fallbackAvatar}'">
          <span>${escapeHtml(p.name)}</span>
          <span class="text-[10px] px-1.5 py-0.5 rounded bg-yellow-400/15 border border-yellow-400/40 text-yellow-300 font-extrabold">${p.edition === 'Bedrock' ? 'PE' : 'JAWA'}</span>
        </span>
      `).join('');
    }

    async function fetchLiveServerStatus(manual = false) {
      const icon = document.getElementById('refresh-icon');
      if (manual && icon) icon.classList.add('fa-spin');

      const t0 = performance.now();
      let javaData = null;
      let bedrockData = null;

      try {
        const [jRes, bRes] = await Promise.allSettled([
          fetchWithTimeout(`https://api.mcstatus.io/v2/status/java/${JAVA_FULL_ADDRESS}`, {}, 3500),
          fetchWithTimeout(`https://api.mcstatus.io/v2/status/bedrock/${BEDROCK_FULL_ADDRESS}`, {}, 3500)
        ]);
        if (jRes.status === 'fulfilled' && jRes.value.ok) javaData = await jRes.value.json();
        if (bRes.status === 'fulfilled' && bRes.value.ok) bedrockData = await bRes.value.json();
      } catch (e) {}

      const ms = Math.max(14, Math.round(performance.now() - t0));
      const jOnline = Boolean(javaData && javaData.online);
      const bOnline = Boolean(bedrockData && bedrockData.online);
      const anyOnline = jOnline || bOnline;

      const jCount = jOnline ? (javaData.players?.online ?? 0) : 0;
      const bCount = bOnline ? (bedrockData.players?.online ?? 0) : 0;
      const totalOnline = Math.max(jCount, bCount);
      const maxPlayers = (jOnline && javaData.players?.max) || (bOnline && bedrockData.players?.max) || 50;

      const pMap = new Map();
      if (jOnline && Array.isArray(javaData.players?.list)) {
        javaData.players.list.forEach(entry => {
          const n = (entry.name_clean || entry.name_raw || entry.name || '').trim();
          if (n) pMap.set(n.toLowerCase(), { name: n, edition: n.startsWith('.') ? 'Bedrock' : 'Java' });
        });
      }
      if (bOnline && Array.isArray(bedrockData.players?.list)) {
        bedrockData.players.list.forEach(entry => {
          const n = (entry.name_clean || entry.name_raw || entry.name || '').trim();
          if (n && !pMap.has(n.toLowerCase())) pMap.set(n.toLowerCase(), { name: n, edition: 'Bedrock' });
        });
      }

      const players = Array.from(pMap.values());

      const statusDot = document.getElementById('server-status-dot');
      const statusText = document.getElementById('server-status-text');
      const statusBadge = document.getElementById('server-status-badge');
      const pingBadge = document.getElementById('ping-latency-badge');
      const versionText = document.getElementById('server-version-text');
      const onlineEl = document.getElementById('server-players-online');
      const maxEl = document.getElementById('server-players-max');
      const pStatusEl = document.getElementById('server-players-status');
      const updatedEl = document.getElementById('last-updated-text');

      if (anyOnline) {
        if (statusDot) statusDot.className = 'w-2.5 h-2.5 rounded-sm bg-lime-400 animate-pulse';
        if (statusText) statusText.textContent = 'ONLINE';
        if (statusBadge) statusBadge.className = 'font-bold flex items-center gap-2 text-base mt-2 text-lime-300';
        if (pingBadge) pingBadge.textContent = `${ms} MS`;
        const ver = (javaData?.version?.name_clean || bedrockData?.version?.name || '1.20 - 1.21+');
        if (versionText) versionText.textContent = `MC ${ver} • Crossplay`;
        if (pStatusEl) pStatusEl.textContent = 'Live player count synced';
      } else {
        if (statusDot) statusDot.className = 'w-2.5 h-2.5 rounded-sm bg-rose-500';
        if (statusText) statusText.textContent = 'OFFLINE / STARTING';
        if (statusBadge) statusBadge.className = 'font-bold flex items-center gap-2 text-base mt-2 text-rose-400';
        if (pingBadge) pingBadge.textContent = 'TIMEOUT';
        if (pStatusEl) pStatusEl.textContent = 'Waiting for server response...';
      }

      if (onlineEl) onlineEl.textContent = String(totalOnline);
      if (maxEl) maxEl.textContent = `/ ${maxPlayers}`;
      if (updatedEl) updatedEl.textContent = `(Synced ${formatNowTime()})`;

      renderPlayersUI(players, anyOnline, totalOnline);

      if (manual && icon) setTimeout(() => icon.classList.remove('fa-spin'), 400);
    }

    // =========================================================================
    // SKYBLOCK LIVE SERVER TELEMETRY (API: free-in-1.vitalcloud.in:25127)
    // =========================================================================
    async function fetchSkyblockStatus(manual = false) {
      const icon = document.getElementById('sb-refresh-icon');
      if (manual && icon) icon.classList.add('fa-spin');

      const t0 = performance.now();
      let sbData = null;

      try {
        const res = await fetchWithTimeout(`https://api.mcstatus.io/v2/status/java/${SKYBLOCK_API_ADDRESS}`, {}, 3500);
        if (res.ok) sbData = await res.json();
      } catch (e) {}

      const ms = Math.max(14, Math.round(performance.now() - t0));
      const isOnline = Boolean(sbData && sbData.online);
      const onlineCount = isOnline ? (sbData.players?.online ?? 0) : 0;
      const maxPlayers = (isOnline && sbData.players?.max) || 50;

      const players = [];
      if (isOnline && Array.isArray(sbData.players?.list)) {
        sbData.players.list.forEach(entry => {
          const n = (entry.name_clean || entry.name_raw || entry.name || '').trim();
          if (n) players.push({ name: n });
        });
      }

      const statusDot = document.getElementById('sb-status-dot');
      const statusText = document.getElementById('sb-status-text');
      const statusBadge = document.getElementById('sb-status-badge');
      const pingBadge = document.getElementById('sb-ping-badge');
      const versionText = document.getElementById('sb-version-text');
      const onlineEl = document.getElementById('sb-players-online');
      const maxEl = document.getElementById('sb-players-max');
      const pStatusEl = document.getElementById('sb-players-status');
      const updatedEl = document.getElementById('sb-last-updated-text');
      const listEl = document.getElementById('sb-players-list');

      if (isOnline) {
        if (statusDot) statusDot.className = 'w-2.5 h-2.5 rounded-sm bg-lime-400 animate-pulse';
        if (statusText) statusText.textContent = 'ONLINE';
        if (statusBadge) statusBadge.className = 'font-bold flex items-center gap-2 text-base mt-2 text-lime-300';
        if (pingBadge) pingBadge.textContent = `${ms} MS`;
        const ver = sbData?.version?.name_clean || '1.20+';
        if (versionText) versionText.textContent = `MC ${ver} • JAWA Only`;
        if (pStatusEl) pStatusEl.textContent = 'Live Skyblock players synced';
      } else {
        if (statusDot) statusDot.className = 'w-2.5 h-2.5 rounded-sm bg-rose-500';
        if (statusText) statusText.textContent = 'OFFLINE / STARTING';
        if (statusBadge) statusBadge.className = 'font-bold flex items-center gap-2 text-base mt-2 text-rose-400';
        if (pingBadge) pingBadge.textContent = 'TIMEOUT';
        if (pStatusEl) pStatusEl.textContent = 'Waiting for Skyblock server...';
      }

      if (onlineEl) onlineEl.textContent = String(onlineCount);
      if (maxEl) maxEl.textContent = `/ ${maxPlayers}`;
      if (updatedEl) updatedEl.textContent = `(Synced ${formatNowTime()})`;

      if (listEl) {
        const fallbackAvatar = "data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24'><rect width='24' height='24' fill='%23FACC15'/><rect x='5' y='8' width='4' height='4' fill='%2309090B'/><rect x='15' y='8' width='4' height='4' fill='%2309090B'/></svg>";
        if (!isOnline) {
          listEl.innerHTML = `<span class="text-xs text-rose-300/85 italic">Skyblock server offline or starting up</span>`;
        } else if (!players.length) {
          const msg = onlineCount > 0 ? `${onlineCount} JAWA player(s) online` : '0 players online on Skyblock right now';
          listEl.innerHTML = `<span class="text-xs text-amber-200/75 italic">${escapeHtml(msg)}</span>`;
        } else {
          listEl.innerHTML = players.map(p => `
            <span class="inline-flex items-center gap-1.5 px-2.5 py-1 rounded-lg bg-stone-950 border border-sky-400/50 text-xs text-white font-mono">
              <img src="https://mc-heads.net/avatar/${encodeURIComponent(p.name)}/32" alt="${escapeHtml(p.name)}" class="w-4 h-4 rounded-sm" onerror="this.onerror=null;this.src='${fallbackAvatar}'">
              <span>${escapeHtml(p.name)}</span>
              <span class="text-[10px] px-1.5 py-0.5 rounded bg-yellow-400/15 border border-yellow-400/40 text-yellow-300 font-extrabold">JAWA</span>
            </span>
          `).join('');
        }
      }

      if (manual && icon) setTimeout(() => icon.classList.remove('fa-spin'), 400);
    }

    // =========================================================================
    // UPCOMING PVP EVENT COUNTDOWN (29 NOVEMBER 2026)
    // =========================================================================
    function updatePvpEventCountdown() {
      const target = new Date('2026-11-29T18:00:00+05:30').getTime();
      const diff = Math.max(0, target - Date.now());
      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const mins = Math.floor((diff / 1000 / 60) % 60);
      const secs = Math.floor((diff / 1000) % 60);

      const dEl = document.getElementById('event-cd-days');
      const hEl = document.getElementById('event-cd-hours');
      const mEl = document.getElementById('event-cd-mins');
      const sEl = document.getElementById('event-cd-secs');
      if (dEl) dEl.textContent = String(days).padStart(2, '0');
      if (hEl) hEl.textContent = String(hours).padStart(2, '0');
      if (mEl) mEl.textContent = String(mins).padStart(2, '0');
      if (sEl) sEl.textContent = String(secs).padStart(2, '0');
    }

    // =========================================================================
    // UPI STORE CHECKOUT MODAL
    // =========================================================================
    function openKitCheckout(name, base, gst, total, desc) {
      const modal = document.getElementById('kit-checkout-modal');
      if (!modal) return;
      document.getElementById('checkout-kit-title').textContent = `Buy ${name}`;
      document.getElementById('checkout-base-price').textContent = `₹${base}`;
      document.getElementById('checkout-gst-price').textContent = `₹${gst}`;
      document.getElementById('checkout-total-price').textContent = `₹${total}`;
      document.getElementById('checkout-kit-desc').textContent = desc;

      const upiUri = `upi://pay?pa=${encodeURIComponent(UPI_ID)}&pn=${encodeURIComponent('PineappleSMP')}&am=${total}&cu=INR&tn=${encodeURIComponent(name)}`;
      document.getElementById('checkout-upi-deeplink').href = upiUri;

      const qrImg = document.getElementById('checkout-qr-img');
      if (qrImg) {
        qrImg.src = `https://api.qrserver.com/v1/create-qr-code/?size=200x200&data=${encodeURIComponent(upiUri)}`;
      }

      modal.classList.remove('hidden');
    }

    function closeKitCheckout() {
      const modal = document.getElementById('kit-checkout-modal');
      if (modal) modal.classList.add('hidden');
    }

    // =========================================================================
    // PINEAPPLEBOT AI SUPPORT ASSISTANT (ENGLISH, HINDI, HINGLISH)
    // =========================================================================
    let selectedAiLang = 'English';
    let aiVariantCounter = 0;

    function setAiLanguage(lang) {
      selectedAiLang = lang;
      ['English', 'Hindi', 'Hinglish'].forEach(l => {
        const btn = document.getElementById(`lang-btn-${l}`);
        if (!btn) return;
        if (l === lang) {
          btn.className = 'px-3 py-1 rounded-lg text-xs font-black bg-yellow-400 text-stone-950 transition-all cursor-pointer';
        } else {
          btn.className = 'px-3 py-1 rounded-lg text-xs font-bold text-amber-200 hover:text-white transition-all cursor-pointer';
        }
      });
      const lbl = document.getElementById('ai-current-lang-label');
      if (lbl) lbl.textContent = lang;
      showToast(`AI Language: ${lang}`);
    }

    function generateSmartAiReply(promptText, lang, variantIndex) {
      const q = promptText.toLowerCase();
      const styles = [
        { greetEn: "Here's the exact solution:", greetHi: "यहाँ सही समाधान है:", greetHing: "Ye raha exact solution:" },
        { greetEn: "Sure thing! Check this out:", greetHi: "बिल्कुल! यह जानकारी देखें:", greetHing: "Bilkul bhai! Ye check karo:" },
        { greetEn: "Quick PineappleSMP guide:", greetHi: "त्वरित PineappleSMP गाइड:", greetHing: "Quick PineappleSMP guide dekho:" }
      ];
      const st = styles[variantIndex % styles.length];

      if (q.includes('skyblock') || q.includes('sky') || q.includes('25127') || q.includes('playgg') || q.includes('island')) {
        if (lang === 'Hindi') {
          return `${st.greetHi}\n• Pineapple Skyblock अभी केवल Java Edition (JAWA) के लिए उपलब्ध है!\n• IP: pineappleskyblock.playgg.pro और Port: 25127 डालकर जॉइन करें।\n• सर्वर में जाकर /is create लिखें और अपना आइलैंड शुरू करें!`;
        }
        if (lang === 'Hinglish') {
          return `${st.greetHing}\n• Pineapple Skyblock abhi sirf Java Edition (JAWA) ke liye hai!\n• IP: pineappleskyblock.playgg.pro aur Port: 25127 (ya pineappleskyblock.playgg.pro:25127) daal kar join karo.\n• Join karne ke baad /is create type karke apna island bnao!`;
        }
        return `${st.greetEn}\n• Pineapple Skyblock is currently exclusive to Minecraft Java Edition (JAWA Only)!\n• Connect using IP: pineappleskyblock.playgg.pro and Port: 25127 (pineappleskyblock.playgg.pro:25127).\n• Once online, type /is create to start your floating island!`;
      }

      if (q.includes('error') || q.includes('connect') || q.includes('timeout') || q.includes('ping') || q.includes('join') || q.includes('unable')) {
        if (lang === 'Hindi') {
          return `${st.greetHi}\n1. Lifesteal Java IP: basic.vitalcloud.in:19126 | Bedrock: basic.vitalcloud.in (Port: 19149)।\n2. Skyblock (केवल JAWA): pineappleskyblock.playgg.pro:25127।\n3. Minecraft वर्जन 1.20 - 1.21+ रखें। समस्या हल न होने पर Discord (discord.gg/Vp9Ss592cq) पर टिकट बनाएं!`;
        }
        if (lang === 'Hinglish') {
          return `${st.greetHing}\n1. Lifesteal Java: basic.vitalcloud.in:19126 | Bedrock: basic.vitalcloud.in (Port 19149).\n2. Skyblock (Sirf JAWA): pineappleskyblock.playgg.pro:25127.\n3. Game version 1.20 - 1.21+ rakho. Agar fir bhi solve na ho toh Discord (discord.gg/Vp9Ss592cq) par ticket bna lo!`;
        }
        return `${st.greetEn}\n1. Lifesteal Java IP: basic.vitalcloud.in:19126 | Bedrock IP: basic.vitalcloud.in (Port: 19149).\n2. Skyblock (JAWA Only): pineappleskyblock.playgg.pro:25127.\n3. Ensure your client is 1.20–1.21+. Still stuck? Open a support ticket on Discord (discord.gg/Vp9Ss592cq)!`;
      }

      if (q.includes('kit') || q.includes('legend') || q.includes('refund') || q.includes('gst') || q.includes('buy') || q.includes('price')) {
        if (lang === 'Hindi') {
          return `${st.greetHi}\n• Lifesteal Legend Kit (₹40 + 15% GST = ₹46): Prot 3 Diamond Armour, Sharpness 3 Sword, 2 Totem, 2 Enchanted Apples, 16 Golden Apples, 16 Ender Pearls और भी बहुत कुछ!\n• Skyblock में Sprout Pack (₹35), Sky Legend Kit (₹46) और VIP/Lord/Emperor रैंक उपलब्ध हैं। 3 घंटे के अंदर अनयूज़्ड/अनडैमेज्ड किट पर रिफंड मिलेगा।`;
        }
        if (lang === 'Hinglish') {
          return `${st.greetHing}\n• Lifesteal Legend Kit (₹40 + 15% GST = ₹46): Prot 3 Diamond Armour, Sharpness 3 Sword, 2 Totem, 2 Enchanted Apples, 16 Golden Apples, 16 Ender Pearls & More!\n• Skyblock me Sprout Pack (₹35), Sky Legend Kit (₹46) aur VIP/Sky Lord/Emperor ranks hain. 3 hours ke andar undamaged/unused package par refund mil jayega!`;
        }
        return `${st.greetEn}\n• Lifesteal Legend Kit (₹40 + 15% GST = ₹46) includes Prot 3 Diamond Armour, Sharpness 3 Sword, 2 Totems, 2 Enchanted Apples, 16 Golden Apples, 16 Ender Pearls & more!\n• Skyblock offers Sprout Pack (₹35), Sky Legend Kit (₹46), and Island VIP/Sky Lord/Emperor ranks. All packages carry 15% GST 3-day protection and a 3-hour unused/undamaged refund policy.`;
      }

      if (q.includes('event') || q.includes('pvp') || q.includes('29') || q.includes('november')) {
        if (lang === 'Hindi') {
          return `${st.greetHi} अगला बड़ा PvP इवेंट 29 नवंबर 2026 को होगा! Java और Bedrock दोनों खिलाड़ी भाग ले सकते हैं। रजिस्ट्रेशन के लिए Discord (discord.gg/Vp9Ss592cq) जॉइन करें।`;
        }
        if (lang === 'Hinglish') {
          return `${st.greetHing} Upcoming PvP Event 29 November 2026 ko hone wala hai! Java aur Bedrock dono players join kar sakte hain. Registration ke liye Discord (discord.gg/Vp9Ss592cq) join karo!`;
        }
        return `${st.greetEn} Our next major PvP Event takes place on 29 November 2026! Both Java and Bedrock players can compete. Join discord.gg/Vp9Ss592cq to register your spot.`;
      }

      if (lang === 'Hindi') {
        return `${st.greetHi} मैं बढ़िया हूँ! मैं PineappleBot हूँ — PineappleSMP (Lifesteal और Skyblock) का आपका AI सहायक। आप मुझसे सर्वर IP, किट्स, इवेंट्स या किसी भी एरर के बारे में पूछ सकते हैं!`;
      }
      if (lang === 'Hinglish') {
        return `${st.greetHing} Main ekdum mast hu bhai! Main PineappleBot hu — Lifesteal aur Skyblock dono ke liye tumhara AI helper. Batao kya help chahiye?`;
      }
      return `${st.greetEn} I'm doing great! I'm PineappleBot, your helper for both Lifesteal SMP and Java-Only Skyblock (pineappleskyblock.playgg.pro:25127). Ask me anything!`;
    }

    function appendAiBubble(role, text, originalPrompt = '') {
      const box = document.getElementById('ai-chat-messages');
      if (!box) return;

      const wrap = document.createElement('div');
      wrap.className = role === 'user' ? 'flex justify-end' : 'flex items-start gap-3';

      if (role === 'user') {
        wrap.innerHTML = `
          <div class="bg-yellow-400 text-stone-950 font-semibold rounded-2xl rounded-tr-none px-4 py-2.5 text-xs sm:text-sm max-w-[82%] shadow">
            ${escapeHtml(text)}
          </div>
        `;
      } else {
        const safePrompt = escapeHtml(originalPrompt).replace(/'/g, "\\'");
        wrap.innerHTML = `
          <div class="w-8 h-8 rounded-xl bg-yellow-400 text-stone-950 flex items-center justify-center font-black text-xs shrink-0 mt-0.5">AI</div>
          <div class="bg-[#1C1506] border border-yellow-500/40 rounded-2xl rounded-tl-none p-3.5 text-xs sm:text-sm text-amber-50 max-w-[85%] space-y-2.5">
            <div class="whitespace-pre-line leading-relaxed">${escapeHtml(text)}</div>
            <div class="pt-2 border-t border-yellow-500/20 flex flex-wrap items-center justify-between gap-2 text-[11px]">
              <button type="button" onclick="regenerateAiAnswer('${safePrompt}')" class="text-yellow-300 hover:text-white font-bold inline-flex items-center gap-1 cursor-pointer">
                <i class="fa-solid fa-rotate"></i> New Answer
              </button>
              <a href="${DISCORD_INVITE}" target="_blank" rel="noopener noreferrer" class="text-indigo-300 hover:text-white font-bold">
                Create Ticket on Discord &rarr;
              </a>
            </div>
          </div>
        `;
      }

      box.appendChild(wrap);
      box.scrollTop = box.scrollHeight;
    }

    function sendQuickAiPrompt(promptText) {
      const inp = document.getElementById('ai-user-input');
      if (inp) inp.value = promptText;
      handleAiSubmit(new Event('submit'));
    }

    function regenerateAiAnswer(promptText) {
      aiVariantCounter += 1;
      const reply = generateSmartAiReply(promptText, selectedAiLang, aiVariantCounter);
      appendAiBubble('ai', reply, promptText);
    }

    function handleAiSubmit(e) {
      if (e) e.preventDefault();
      const inp = document.getElementById('ai-user-input');
      if (!inp) return;
      const text = inp.value.trim();
      if (!text) return;
      inp.value = '';
      appendAiBubble('user', text);
      aiVariantCounter += 1;
      const reply = generateSmartAiReply(text, selectedAiLang, aiVariantCounter);
      setTimeout(() => appendAiBubble('ai', reply, text), 160);
    }

    // =========================================================================
    // FOUNDER DISCORD LIVE PROFILE SYNC (devesh_37.)
    // =========================================================================
    const FOUNDER_DISCORD_CONFIG = {
      snowflakeId: '',
      defaultBio: 'Founder & Creator of PineappleSMP • Building Season 1 Lifesteal, Skyblock & VitalCloud network.'
    };

    async function syncFounderDiscordProfile() {
      const bioEl = document.getElementById('founder-discord-bio');
      if (bioEl && FOUNDER_DISCORD_CONFIG.defaultBio) {
        bioEl.textContent = FOUNDER_DISCORD_CONFIG.defaultBio;
      }

      if (!FOUNDER_DISCORD_CONFIG.snowflakeId) return;
      try {
        const res = await fetchWithTimeout(`https://api.lanyard.rest/v1/users/${FOUNDER_DISCORD_CONFIG.snowflakeId}`, {}, 3500);
        if (!res.ok) return;
        const json = await res.json();
        const data = json?.data;
        if (!data || !data.discord_user) return;

        const u = data.discord_user;
        const pfpEl = document.getElementById('founder-discord-pfp');
        const nameEl = document.getElementById('founder-discord-displayname');
        const dotEl = document.getElementById('founder-discord-status-dot');
        const actEl = document.getElementById('founder-discord-activity');

        if (pfpEl && u.avatar) {
          pfpEl.src = `https://cdn.discordapp.com/avatars/${u.id}/${u.avatar}.png?size=128`;
        }
        if (nameEl) {
          nameEl.textContent = u.global_name || u.username || 'Devesh';
        }
        if (dotEl) {
          const colors = { online: 'bg-lime-400', idle: 'bg-amber-400', dnd: 'bg-rose-500', offline: 'bg-stone-500' };
          dotEl.className = `w-4 h-4 rounded-full ${colors[data.discord_status] || 'bg-lime-400'} border-2 border-stone-950 absolute -bottom-1 -right-1`;
        }
        if (actEl && Array.isArray(data.activities) && data.activities.length > 0) {
          const custom = data.activities.find(a => a.type === 4 && a.state);
          if (custom && bioEl) bioEl.textContent = custom.state;
          const game = data.activities.find(a => a.type === 0 && a.name);
          if (game) actEl.innerHTML = `<i class="fa-solid fa-gamepad text-yellow-300 mr-1"></i>Playing ${escapeHtml(game.name)}`;
        }
      } catch (e) {}
    }

    // =========================================================================
    // INITIALIZE NON-BLOCKING LOOPS ON DOM READY
    // =========================================================================
    document.addEventListener('DOMContentLoaded', () => {
      try {
        updatePvpEventCountdown();
        setInterval(updatePvpEventCountdown, 1000);

        fetchLiveServerStatus(false);
        fetchSkyblockStatus(false);
        setInterval(() => {
          if (currentGamemode === 'skyblock') {
            fetchSkyblockStatus(false);
          } else {
            fetchLiveServerStatus(false);
          }
        }, 5000);

        syncFounderDiscordProfile();
        setInterval(syncFounderDiscordProfile, 15000);
      } catch (err) {
        console.error('Initialization warning:', err);
      }
    });
  </script>
</body>
</html>
