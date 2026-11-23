<!DOCTYPE html>
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
    <div class="animate-ticker">
      <div class="flex items-center gap-8 px-4">
        <span><i class="fa-solid fa-crown mr-1.5"></i>PINEAPPLE SMP — SEASON 1 LAUNCHED</span>
        <span>&bull;</span>
        <span><i class="fa-solid fa-bolt mr-1.5"></i>UPCOMING PVP EVENT ON 29 NOVEMBER 2026</span>
        <span>&bull;</span>
        <span><i class="fa-solid fa-desktop mr-1.5"></i>JAVA: basic.vitalcloud.in:19126</span>
        <span>&bull;</span>
        <span><i class="fa-solid fa-mobile-screen mr-1.5"></i>BEDROCK: basic.vitalcloud.in &bull; PORT: 19149</span>
        <span>&bull;</span>
        <span><i class="fa-brands fa-discord mr-1.5"></i>DISCORD: discord.gg/Vp9Ss592cq</span>
        <span>&bull;</span>
      </div>
      <div class="flex items-center gap-8 px-4" aria-hidden="true">
        <span><i class="fa-solid fa-crown mr-1.5"></i>PINEAPPLE SMP — SEASON 1 LAUNCHED</span>
        <span>&bull;</span>
        <span><i class="fa-solid fa-bolt mr-1.5"></i>UPCOMING PVP EVENT ON 29 NOVEMBER 2026</span>
        <span>&bull;</span>
        <span><i class="fa-solid fa-desktop mr-1.5"></i>JAVA: basic.vitalcloud.in:19126</span>
        <span>&bull;</span>
        <span><i class="fa-solid fa-mobile-screen mr-1.5"></i>BEDROCK: basic.vitalcloud.in &bull; PORT: 19149</span>
        <span>&bull;</span>
        <span><i class="fa-brands fa-discord mr-1.5"></i>DISCORD: discord.gg/Vp9Ss592cq</span>
        <span>&bull;</span>
      </div>
    </div>
  </div>

  <!-- STICKY NAVIGATION BAR -->
  <header class="sticky top-0 z-40 bg-[#120D04]/95 backdrop-blur-md border-b-2 border-yellow-500/40 shadow-xl">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 h-16 sm:h-[72px] flex items-center justify-between gap-3">
      
      <!-- Brand Logo: Box Pineapple Voxel-Emblem with Z-Black Sunglasses -->
      <a href="#" class="flex items-center gap-3 group shrink-0">
        <div class="w-11 h-11 sm:w-12 sm:h-12 rounded-xl bg-gradient-to-br from-yellow-300 via-amber-400 to-amber-600 p-1 border-2 border-yellow-200 shadow-[0_0_18px_rgba(255,214,10,0.45)] group-hover:scale-105 transition-transform">
          <svg viewBox="0 0 64 64" class="w-full h-full" xmlns="http://www.w3.org/2000/svg" aria-label="PineappleSMP Emblem Logo">
            <!-- Golden-Amber Hexagonal Shield Crest -->
            <polygon points="32,2 58,12 54,48 32,62 10,48 6,12" fill="#1C1404" stroke="#FDE047" stroke-width="2.5" stroke-linejoin="round"/>
            <!-- Lush Emerald Crown Leaves -->
            <polygon points="32,3 25,17 39,17" fill="#15803D"/>
            <polygon points="32,4 28,17 36,17" fill="#22C55E"/>
            <polygon points="18,8 17,19 28,17" fill="#16A34A"/>
            <polygon points="46,8 36,17 47,19" fill="#15803D"/>
            <!-- 3D Voxel Box Pineapple Body -->
            <rect x="16" y="17" width="32" height="36" rx="4" fill="#FACC15" stroke="#451A03" stroke-width="2.2"/>
            <!-- Right Side Voxel Shadow -->
            <rect x="41" y="18" width="6" height="34" rx="2" fill="#B45309" opacity="0.5"/>
            <!-- Top Highlight -->
            <rect x="18" y="19" width="23" height="5" rx="2" fill="#FEF08A" opacity="0.7"/>
            <!-- Pineapple Scale Texture -->
            <path d="M23 18 L23 52 M31 18 L31 52 M39 18 L39 52 M17 37 L47 37 M17 45 L47 45" stroke="#92400E" stroke-width="1.3" opacity="0.5"/>
            <!-- Iconic Z-Black Angular Sunglasses -->
            <rect x="12" y="25" width="4" height="3" fill="#09090B"/>
            <rect x="48" y="25" width="4" height="3" fill="#09090B"/>
            <polygon points="14,23 30,24.5 29,34 15.5,33" fill="#09090B" stroke="#000000" stroke-width="1.8" stroke-linejoin="round"/>
            <polygon points="34,24.5 50,23 48.5,33 35,34" fill="#09090B" stroke="#000000" stroke-width="1.8" stroke-linejoin="round"/>
            <rect x="29.5" y="24.5" width="5" height="2.8" fill="#09090B"/>
            <!-- Crisp Glossy White Reflections -->
            <polygon points="17,25 21.5,25 18.5,32 15.5,32" fill="#FFFFFF" opacity="0.45"/>
            <polygon points="37,25 41.5,25 38.5,32 35.5,32" fill="#FFFFFF" opacity="0.45"/>
            <!-- Confident Smirk -->
            <path d="M26 43 Q32 47 38 42" stroke="#451A03" stroke-width="2.4" fill="none" stroke-linecap="round"/>
            <!-- Corner Rivet Sparkles -->
            <circle cx="11" cy="14" r="1.5" fill="#FEF08A"/>
            <circle cx="53" cy="14" r="1.5" fill="#FEF08A"/>
          </svg>
        </div>
        <div>
          <div class="font-silk font-bold text-sm sm:text-base text-white tracking-wider leading-none">
            PINEAPPLE <span class="text-yellow-300">SMP</span>
          </div>
          <div class="text-[10px] font-extrabold text-amber-300 uppercase tracking-widest mt-1">
            LIFESTEAL SMP
          </div>
        </div>
      </a>

      <!-- Center Navigation Links -->
      <nav class="hidden xl:flex items-center gap-4 text-[11px] font-extrabold uppercase tracking-wider text-amber-100/85">
        <a href="#status" class="hover:text-yellow-300 transition-colors">Status</a>
        <a href="#events" class="hover:text-yellow-300 transition-colors">Events</a>
        <a href="#features" class="hover:text-yellow-300 transition-colors">Features</a>
        <a href="#store" class="hover:text-yellow-300 transition-colors">Kits Store</a>
        <a href="#partners" class="hover:text-yellow-300 transition-colors">Partners</a>
        <a href="#funders" class="hover:text-yellow-300 transition-colors">Funders</a>
        <a href="#join" class="hover:text-yellow-300 transition-colors">How to Join</a>
        <a href="#ai-support" class="hover:text-yellow-300 transition-colors">AI Support</a>
      </nav>

      <!-- Quick Copy IP Pill & Discord CTA -->
      <div class="flex items-center gap-2 sm:gap-3">
        <button type="button" onclick="copyToClipboard('basic.vitalcloud.in:19126', 'Copied Java IP: basic.vitalcloud.in:19126')" class="hidden sm:inline-flex items-center gap-2 px-3 py-1.5 rounded-xl bg-[#1E1707] hover:bg-[#2B210A] border border-yellow-400/50 text-xs font-mono font-bold text-yellow-300 transition-all active:scale-95 cursor-pointer" title="Click to copy Java IP">
          <span class="w-2 h-2 rounded-full bg-lime-400 animate-pulse"></span>
          <span>basic.vitalcloud.in:19126</span>
          <i class="fa-regular fa-copy text-[11px] text-amber-200"></i>
        </button>

        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="mc-btn bg-gradient-to-b from-indigo-500 to-indigo-700 text-white font-extrabold text-xs px-3.5 py-2 rounded-xl flex items-center gap-1.5 uppercase tracking-wider shadow-md">
          <i class="fa-brands fa-discord text-sm"></i>
          <span>Discord</span>
        </a>
      </div>
    </div>
  </header>

  <main class="flex-1">

    <!-- HERO SECTION -->
    <section class="relative py-12 sm:py-16 max-w-7xl mx-auto px-4 sm:px-6 overflow-hidden">
      <!-- Ambient Floating Golden Sparkles -->
      <div class="pointer-events-none absolute top-10 left-8 w-2 h-2 rotate-45 bg-yellow-300 sparkle-dot"></div>
      <div class="pointer-events-none absolute top-24 right-14 w-2.5 h-2.5 rotate-45 bg-amber-400 sparkle-dot" style="animation-delay: 1.2s;"></div>
      <div class="pointer-events-none absolute bottom-12 left-1/3 w-2 h-2 rotate-45 bg-yellow-200 sparkle-dot" style="animation-delay: 2.1s;"></div>

      <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
        
        <!-- Left Hero Text & Instant IP Copy Cards -->
        <div class="lg:col-span-7 text-center lg:text-left space-y-5">
          <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-yellow-400/15 border border-yellow-400/60 text-yellow-300 text-xs font-black uppercase tracking-widest shadow-[0_0_20px_rgba(255,214,10,0.2)]">
            <i class="fa-solid fa-fire text-amber-400"></i>
            <span>LIFESTEAL SMP &bull; SEASON 1 LAUNCHED</span>
          </div>

          <h1 class="font-pixel text-3xl sm:text-5xl lg:text-[50px] text-white leading-tight drop-shadow-[0_4px_0_#78350F]">
            PINEAPPLE <span class="text-transparent bg-clip-text bg-gradient-to-r from-yellow-200 via-yellow-400 to-amber-500">SMP</span>
          </h1>

          <p class="text-amber-100/90 text-sm sm:text-base max-w-2xl mx-auto lg:mx-0 leading-relaxed">
            Enter India's ultimate <strong class="text-yellow-300">Lifesteal SMP</strong> network powered by <strong class="text-yellow-300">VitalCloud</strong>. Steal hearts in intense crossplay PvP battles, gear up with custom Battle Kits, and compete in Season 1!
          </p>

          <!-- Instant Copy IP Action Cards -->
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

        <!-- Right Hero Box Pineapple Voxel-Emblem Mascot with Z-Black Sunglasses -->
        <div class="lg:col-span-5 flex justify-center">
          <div class="relative mascot-float">
            <div class="absolute -inset-5 bg-gradient-to-tr from-yellow-400/30 via-amber-400/20 to-yellow-200/30 rounded-full blur-2xl"></div>
            <div class="relative mc-panel p-6 sm:p-8 rounded-3xl border-2 border-yellow-400/85 flex flex-col items-center">
              <svg viewBox="0 0 200 210" class="w-48 h-48 sm:w-60 sm:h-60 drop-shadow-[0_16px_28px_rgba(0,0,0,0.8)]" xmlns="http://www.w3.org/2000/svg" aria-label="PineappleSMP Voxel Emblem Mascot Wearing Z-Black Sunglasses">
                <!-- Golden-Amber Hexagonal Shield Crest Backdrop -->
                <polygon points="100,8 178,42 168,146 100,196 32,146 22,42" fill="#FACC15" stroke="#451A03" stroke-width="4" stroke-linejoin="round"/>
                <polygon points="100,16 170,47 161,141 100,187 39,141 30,47" fill="#1A1204" stroke="#FDE047" stroke-width="2" stroke-linejoin="round"/>

                <!-- Corner Glowing Rivets & Diamond Sparkles -->
                <circle cx="38" cy="52" r="3" fill="#FEF08A"/>
                <circle cx="162" cy="52" r="3" fill="#FEF08A"/>
                <circle cx="46" cy="136" r="3" fill="#FACC15"/>
                <circle cx="154" cy="136" r="3" fill="#FACC15"/>
                <polygon points="164,24 167,31 174,34 167,37 164,44 161,37 154,34 161,31" fill="#FEF08A"/>
                <polygon points="34,26 36,31 41,33 36,35 34,40 32,35 27,33 32,31" fill="#FDE047"/>

                <!-- Lush Multi-Layered Emerald Crown of Spiky Pineapple Leaves -->
                <polygon points="62,32 54,64 82,58" fill="#14532D" stroke="#052E16" stroke-width="2.5" stroke-linejoin="round"/>
                <polygon points="138,32 118,58 146,64" fill="#14532D" stroke="#052E16" stroke-width="2.5" stroke-linejoin="round"/>
                <polygon points="78,20 68,58 96,56" fill="#16A34A" stroke="#052E16" stroke-width="2.5" stroke-linejoin="round"/>
                <polygon points="122,20 104,56 132,58" fill="#15803D" stroke="#052E16" stroke-width="2.5" stroke-linejoin="round"/>
                <polygon points="100,12 83,56 117,56" fill="#22C55E" stroke="#052E16" stroke-width="3" stroke-linejoin="round"/>
                <polygon points="100,16 93,54 107,54" fill="#86EFAC" opacity="0.5"/>

                <!-- 3D Isometric/Voxel Golden Box-Pineapple Body -->
                <rect x="48" y="54" width="94" height="106" rx="10" fill="#FACC15" stroke="#451A03" stroke-width="4.5"/>
                <!-- Right Isometric Voxel Depth Side -->
                <path d="M142 58 L152 65 L152 153 L142 158 Z" fill="#B45309" stroke="#451A03" stroke-width="3.5" stroke-linejoin="round"/>
                <!-- Top Highlight Bevel -->
                <rect x="53" y="58" width="84" height="14" rx="5" fill="#FEF9C3" opacity="0.65"/>

                <!-- Textured Diamond Pineapple Scales -->
                <g stroke="#92400E" stroke-width="2" opacity="0.45">
                  <path d="M54 106 L74 126 L54 146 M74 106 L94 126 L74 146 M94 106 L114 126 L94 146 M114 106 L134 126 L114 146" fill="none"/>
                  <path d="M136 106 L116 126 L136 146 M116 106 L96 126 L116 146 M96 106 L76 126 L96 146 M76 106 L56 126 L76 146" fill="none"/>
                  <line x1="52" y1="106" x2="138" y2="106"/>
                </g>

                <!-- Iconic Z-Black Angular Sunglasses -->
                <g>
                  <polygon points="36,77 50,78 50,85 37,83" fill="#09090B" stroke="#000000" stroke-width="2"/>
                  <polygon points="140,78 156,76 155,83 140,85" fill="#09090B" stroke="#000000" stroke-width="2"/>
                  <polygon points="46,72 91,75 88,99 50,96" fill="#09090B" stroke="#000000" stroke-width="3.5" stroke-linejoin="round"/>
                  <polygon points="99,75 144,72 140,96 102,99" fill="#09090B" stroke="#000000" stroke-width="3.5" stroke-linejoin="round"/>
                  <polygon points="89,75 101,75 100,82 90,82" fill="#09090B" stroke="#000000" stroke-width="2"/>
                  <!-- Glossy White Lens Reflections -->
                  <polygon points="55,76 66,76 58,93 52,93" fill="#FFFFFF" opacity="0.45"/>
                  <polygon points="70,77 75,77 67,93 62,93" fill="#FFFFFF" opacity="0.22"/>
                  <polygon points="108,76 119,76 111,93 105,93" fill="#FFFFFF" opacity="0.45"/>
                  <polygon points="123,77 128,77 120,93 115,93" fill="#FFFFFF" opacity="0.22"/>
                </g>

                <!-- Confident Smirk -->
                <path d="M80 130 Q97 141 114 127" stroke="#451A03" stroke-width="4.5" fill="none" stroke-linecap="ro
