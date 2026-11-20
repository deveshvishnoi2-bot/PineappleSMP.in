<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>PineappleSMP | Minecraft Lifesteal & Survival Adventure</title>
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Font Awesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
  <!-- Google Fonts (GTA 6 Vice Condensed Display + Clean UI Sans) -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Anton&family=Bebas+Neue&family=Inter:wght@400;500;600;700;800&family=Outfit:wght@600;800;900&family=Plus+Jakarta+Sans:wght@400;500;600;700;800&family=Press+Start+2P&display=swap" rel="stylesheet">
  
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            vice: {
              pink: '#FF2A85',
              magenta: '#D946EF',
              purple: '#7C3AED',
              cyan: '#00F0FF',
              orange: '#FF7A2F',
              gold: '#FACC15',
            },
            pineapple: {
              300: '#FDE047',
              400: '#FACC15',
              500: '#FF8C24',
              600: '#FF2A85',
              700: '#A21CAF',
            },
            jungle: {
              400: '#00F0FF',
              500: '#06B6D4',
              600: '#0891B2',
              700: '#0E7490',
            },
            smpDark: '#090612',
            smpCard: '#120B24',
            smpBorder: '#351D5C'
          },
          fontFamily: {
            gta: ['"Bebas Neue"', 'Anton', 'sans-serif'],
            heading: ['Outfit', '"Bebas Neue"', 'sans-serif'],
            pixel: ['"Press Start 2P"', 'monospace'],
            sans: ['"Plus Jakarta Sans"', 'Inter', 'sans-serif']
          }
        }
      }
    }
  </script>
  <style>
    :root {
      --bg-vice-night: #080510;
      --vice-pink: #ff2a85;
      --vice-cyan: #00f0ff;
      --vice-sunset: #ff8c24;
      --vice-gold: #facc15;
    }

    body {
      background-color: var(--bg-vice-night);
      background-image:
        radial-gradient(circle at 50% 8%, rgba(255, 42, 133, 0.24) 0%, rgba(255, 140, 36, 0.14) 24%, transparent 54%),
        radial-gradient(circle at 12% 35%, rgba(0, 240, 255, 0.14) 0%, transparent 45%),
        radial-gradient(circle at 88% 60%, rgba(217, 70, 239, 0.16) 0%, transparent 48%),
        linear-gradient(180deg, #130926 0%, #090612 38%, #07040F 100%);
      color: #F8FAFC;
      overflow-x: hidden;
      font-family: 'Plus Jakarta Sans', 'Inter', sans-serif;
    }

    /* GTA 6 Vice City Neon Glass Card */
    .mc-panel {
      background: linear-gradient(160deg, rgba(24, 14, 48, 0.88) 0%, rgba(11, 7, 24, 0.96) 100%);
      backdrop-filter: blur(16px);
      border: 1.5px solid rgba(255, 42, 133, 0.36);
      box-shadow:
        inset 0 1px 0 rgba(0, 240, 255, 0.22),
        inset 0 -2px 0 rgba(0, 0, 0, 0.85),
        0 14px 36px rgba(0, 0, 0, 0.72),
        0 0 22px rgba(255, 42, 133, 0.1);
      transition: transform 0.25s cubic-bezier(0.16, 1, 0.3, 1), border-color 0.25s ease, box-shadow 0.25s ease;
    }
    .mc-panel:hover {
      border-color: rgba(0, 240, 255, 0.75);
      box-shadow:
        inset 0 1px 0 rgba(255, 42, 133, 0.38),
        0 18px 44px rgba(0, 0, 0, 0.8),
        0 0 32px rgba(0, 240, 255, 0.18),
        0 0 18px rgba(255, 42, 133, 0.18);
    }

    /* Vice City Neon Action Button */
    .mc-btn {
      box-shadow:
        inset 0 1px 0 rgba(255, 255, 255, 0.45),
        inset 0 -3px 0 rgba(0, 0, 0, 0.4),
        0 8px 24px rgba(255, 42, 133, 0.28);
      transition: transform 0.15s ease, filter 0.18s ease, box-shadow 0.18s ease;
    }
    .mc-btn:hover {
      filter: brightness(1.08);
      transform: translateY(-2px);
      box-shadow:
        inset 0 1px 0 rgba(255, 255, 255, 0.55),
        0 12px 28px rgba(0, 240, 255, 0.32),
        0 0 18px rgba(255, 42, 133, 0.35);
    }
    .mc-btn:active {
      transform: translateY(1px);
    }

    /* Vice City Neon Sunset Laser Divider */
    .mc-grass-divider {
      height: 4px;
      width: 100%;
      background: linear-gradient(90deg, transparent 0%, #00F0FF 18%, #FF2A85 50%, #FF8C24 72%, #FACC15 86%, transparent 100%);
      box-shadow: 0 0 18px rgba(255, 42, 133, 0.65), 0 0 10px rgba(0, 240, 255, 0.45);
      opacity: 0.9;
    }

    /* GTA 6 Vice Sunset Typography Glow */
    .pineapple-text-glow {
      text-shadow:
        0 0 32px rgba(255, 42, 133, 0.72),
        0 0 60px rgba(255, 140, 36, 0.45),
        0 6px 18px rgba(0, 0, 0, 0.9);
    }
    .vice-cyan-glow {
      text-shadow: 0 0 22px rgba(0, 240, 255, 0.75);
    }

    /* Retro Vice Scanlines & Palm Horizon Grid */
    .bg-grid-pattern {
      background-image:
        linear-gradient(to right, rgba(255, 42, 133, 0.08) 1px, transparent 1px),
        linear-gradient(to bottom, rgba(0, 240, 255, 0.07) 1px, transparent 1px);
      background-size: 44px 44px;
    }

    .vice-scanlines {
      background: repeating-linear-gradient(
        to bottom,
        rgba(255, 255, 255, 0) 0px,
        rgba(255, 255, 255, 0) 3px,
        rgba(255, 42, 133, 0.04) 4px
      );
    }

    /* Striped Retro Vice Sun Disk */
    .vice-sun-disk {
      background: linear-gradient(180deg, #FACC15 0%, #FF7A2F 45%, #FF2A85 85%, #A21CAF 100%);
      -webkit-mask-image: linear-gradient(
        to bottom,
        #000 0%,
        #000 54%,
        transparent 54%,
        transparent 57%,
        #000 57%,
        #000 68%,
        transparent 68%,
        transparent 72%,
        #000 72%,
        #000 82%,
        transparent 82%,
        transparent 87%,
        #000 87%,
        #000 100%
      );
      mask-image: linear-gradient(
        to bottom,
        #000 0%,
        #000 54%,
        transparent 54%,
        transparent 57%,
        #000 57%,
        #000 68%,
        transparent 68%,
        transparent 72%,
        #000 72%,
        #000 82%,
        transparent 82%,
        transparent 87%,
        #000 87%,
        #000 100%
      );
    }

    @keyframes floatParticle {
      0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 0.4; }
      50% { transform: translateY(-24px) rotate(45deg); opacity: 0.95; }
    }
    .pixel-spark {
      position: fixed;
      pointer-events: none;
      z-index: 1;
      border-radius: 9999px;
      animation: floatParticle 6s ease-in-out infinite;
    }

    @keyframes floating {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-10px); }
    }
    .animate-float {
      animation: floating 4.2s ease-in-out infinite;
    }

    .shine-btn {
      position: relative;
      overflow: hidden;
    }
    .shine-btn::after {
      content: '';
      position: absolute;
      top: -50%;
      left: -60%;
      width: 22%;
      height: 200%;
      background: rgba(255, 255, 255, 0.35);
      transform: rotate(30deg);
      transition: all 0.7s cubic-bezier(0.19, 1, 0.22, 1);
    }
    .shine-btn:hover::after {
      left: 140%;
    }

    @keyframes tickerSlide {
      0% { transform: translate3d(0, 0, 0); }
      100% { transform: translate3d(-50%, 0, 0); }
    }
    .ticker-wrapper {
      display: flex;
      width: max-content;
      animation: tickerSlide 30s linear infinite;
    }
    .ticker-wrapper:hover {
      animation-play-state: paused;
    }

    @keyframes fadeSlideUp {
      from { opacity: 0; transform: translateY(8px); }
      to { opacity: 1; transform: translateY(0); }
    }
    .chat-msg-enter {
      animation: fadeSlideUp 0.28s cubic-bezier(0.16, 1, 0.3, 1) forwards;
    }

    .avatar-scroll::-webkit-scrollbar {
      width: 6px;
    }
    .avatar-scroll::-webkit-scrollbar-track {
      background: rgba(18, 11, 36, 0.8);
      border-radius: 8px;
    }
    .avatar-scroll::-webkit-scrollbar-thumb {
      background: linear-gradient(180deg, #FF2A85, #00F0FF);
      border-radius: 8px;
    }
  </style>
</head>
<body class="text-slate-100 min-h-screen relative selection:bg-vice-pink selection:text-white">

  <!-- Ambient Vice City Grid, Scanlines, Sunset Glows & Neon Sparkles -->
  <div class="fixed inset-0 bg-grid-pattern opacity-45 pointer-events-none z-0"></div>
  <div class="fixed inset-0 vice-scanlines pointer-events-none z-0"></div>
  <div class="fixed -top-16 left-1/2 -translate-x-1/2 w-[780px] h-[380px] bg-gradient-to-r from-vice-pink/25 via-vice-orange/20 to-vice-cyan/20 blur-[140px] rounded-full pointer-events-none z-0"></div>
  <div class="pixel-spark w-2 h-2 bg-vice-pink shadow-[0_0_12px_#ff2a85]" style="top: 18%; left: 9%; animation-delay: 0s;"></div>
  <div class="pixel-spark w-2.5 h-2.5 bg-vice-cyan shadow-[0_0_12px_#00f0ff]" style="top: 30%; right: 11%; animation-delay: 1.5s;"></div>
  <div class="pixel-spark w-2 h-2 bg-vice-gold shadow-[0_0_10px_#facc15]" style="top: 62%; left: 7%; animation-delay: 3s;"></div>
  <div class="pixel-spark w-2 h-2 bg-vice-magenta shadow-[0_0_12px_#d946ef]" style="top: 76%; right: 13%; animation-delay: 2.2s;"></div>

  <!-- Toast Notification -->
  <div id="toast" class="fixed bottom-6 right-6 z-50 transform translate-y-24 opacity-0 transition-all duration-300 bg-gradient-to-r from-vice-pink via-vice-orange to-vice-cyan text-slate-950 font-black px-5 py-3 rounded-xl shadow-[0_0_30px_rgba(255,42,133,0.5)] flex items-center gap-2.5 text-xs sm:text-sm pointer-events-none border border-white/50">
    <i class="fa-solid fa-circle-check text-slate-950 text-base"></i>
    <span id="toast-text">Copied to clipboard!</span>
  </div>

  <!-- 1. TOP RUNNING UPDATE / NEWS BROADCAST TICKER -->
  <div class="relative z-40 bg-gradient-to-r from-[#24092E] via-[#150A2B] to-[#072336] border-b border-vice-pink/50 py-2 overflow-hidden shadow-[0_4px_20px_rgba(255,42,133,0.25)]">
    <div class="ticker-wrapper flex items-center gap-10 text-xs font-extrabold tracking-wider uppercase text-pink-100">
      <div class="flex items-center gap-10 shrink-0">
        <span class="flex items-center gap-2 text-vice-cyan">
          <span class="w-2 h-2 rounded-full bg-vice-pink animate-ping"></span>
          PINEAPPLE SMP — SEASON 1 LAUNCHED &bull; VICE EDITION
        </span>
        <span class="text-vice-pink/60">|</span>
        <span class="flex items-center gap-2 text-amber-200">
          JAVA IP: <strong class="font-mono text-white">basic.vitalcloud.in:19126</strong>
        </span>
        <span class="text-vice-pink/60">|</span>
        <span class="flex items-center gap-2 text-cyan-200">
          BEDROCK IP: <strong class="font-mono text-white">basic.vitalcloud.in</strong> &bull; PORT: <strong class="font-mono text-vice-gold">19149</strong>
        </span>
        <span class="text-vice-pink/60">|</span>
        <span class="flex items-center gap-2 text-pink-300">
          HOSTED ON VITALCLOUD
        </span>
        <span class="text-vice-pink/60">|</span>
        <span class="flex items-center gap-2 text-amber-200">
          <i class="fa-brands fa-discord text-vice-cyan text-sm"></i>
          DISCORD: <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="underline text-vice-gold hover:text-white">discord.gg/Vp9Ss592cq</a>
        </span>
        <span class="text-vice-pink/60">|</span>
      </div>
      <!-- Duplicate track for seamless infinite loop -->
      <div class="flex items-center gap-10 shrink-0" aria-hidden="true">
        <span class="flex items-center gap-2 text-vice-cyan">
          <span class="w-2 h-2 rounded-full bg-vice-pink animate-ping"></span>
          PINEAPPLE SMP — SEASON 1 LAUNCHED &bull; VICE EDITION
        </span>
        <span class="text-vice-pink/60">|</span>
        <span class="flex items-center gap-2 text-amber-200">
          JAVA IP: <strong class="font-mono text-white">basic.vitalcloud.in:19126</strong>
        </span>
        <span class="text-vice-pink/60">|</span>
        <span class="flex items-center gap-2 text-cyan-200">
          BEDROCK IP: <strong class="font-mono text-white">basic.vitalcloud.in</strong> &bull; PORT: <strong class="font-mono text-vice-gold">19149</strong>
        </span>
        <span class="text-vice-pink/60">|</span>
        <span class="flex items-center gap-2 text-pink-300">
          HOSTED ON VITALCLOUD
        </span>
        <span class="text-vice-pink/60">|</span>
        <span class="flex items-center gap-2 text-amber-200">
          <i class="fa-brands fa-discord text-vice-cyan text-sm"></i>
          DISCORD: <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="underline text-vice-gold hover:text-white">discord.gg/Vp9Ss592cq</a>
        </span>
        <span class="text-vice-pink/60">|</span>
      </div>
    </div>
  </div>

  <!-- 2. STICKY VICE CITY GLASSMORPHIC NAVBAR -->
  <header class="sticky top-0 z-30 bg-[#0B0718]/85 backdrop-blur-xl border-b border-vice-pink/35 shadow-[0_8px_30px_rgba(0,0,0,0.65)]">
    <div class="w-full max-w-7xl mx-auto px-4 sm:px-6 py-3 flex items-center justify-between gap-4">
      
      <!-- Left: PineappleSMP Vice Neon Brand Logo -->
      <a href="#home" class="flex items-center gap-3 group shrink-0">
        <div class="w-11 h-11 sm:w-12 sm:h-12 rounded-xl border border-vice-cyan/70 bg-gradient-to-br from-[#2B0B3F] via-[#130826] to-[#082436] p-1 flex items-center justify-center shadow-[0_0_18px_rgba(255,42,133,0.45)] group-hover:scale-105 transition-transform">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 300" class="w-full h-full drop-shadow-[0_2px_8px_rgba(255,42,133,0.65)]">
            <defs>
              <linearGradient id="navViceTop" x1="0" y1="0" x2="1" y2="1">
                <stop offset="0%" stop-color="#FEF08A"/>
                <stop offset="100%" stop-color="#FF8C24"/>
              </linearGradient>
              <linearGradient id="navViceFront" x1="0" y1="0" x2="0" y2="1">
                <stop offset="0%" stop-color="#FF7A2F"/>
                <stop offset="100%" stop-color="#FF2A85"/>
              </linearGradient>
              <linearGradient id="navViceSide" x1="0" y1="0" x2="1" y2="1">
                <stop offset="0%" stop-color="#D946EF"/>
                <stop offset="100%" stop-color="#6D28D9"/>
              </linearGradient>
              <linearGradient id="navViceLeaf" x1="0" y1="1" x2="0" y2="0">
                <stop offset="0%" stop-color="#0891B2"/>
                <stop offset="60%" stop-color="#00F0FF"/>
                <stop offset="100%" stop-color="#A5F3FC"/>
              </linearGradient>
            </defs>
            <path d="M160 66 C152 30, 145 10, 160 4 C175 10, 168 30, 160 66 Z" fill="url(#navViceLeaf)" stroke="#1E1B4B" stroke-width="4"/>
            <path d="M152 68 C130 38, 108 26, 102 38 C114 58, 134 68, 152 74 Z" fill="url(#navViceLeaf)" stroke="#1E1B4B" stroke-width="4"/>
            <path d="M168 68 C190 38, 212 26, 218 38 C206 58, 186 68, 168 74 Z" fill="url(#navViceLeaf)" stroke="#1E1B4B" stroke-width="4"/>
            <polygon points="160,64 226,88 160,112 94,88" fill="url(#navViceTop)" stroke="#1E1B4B" stroke-width="5" stroke-linejoin="round"/>
            <polygon points="94,88 160,112 160,188 94,162" fill="url(#navViceSide)" stroke="#1E1B4B" stroke-width="5" stroke-linejoin="round"/>
            <polygon points="160,112 226,88 226,162 160,188" fill="url(#navViceFront)" stroke="#1E1B4B" stroke-width="5" stroke-linejoin="round"/>
            <rect x="172" y="132" width="11" height="14" rx="2" fill="#0F172A"/>
            <rect x="174" y="134" width="4" height="4" fill="#00F0FF"/>
            <rect x="204" y="120" width="11" height="14" rx="2" fill="#0F172A"/>
            <rect x="206" y="122" width="4" height="4" fill="#00F0FF"/>
            <path d="M187 143 Q194 152 200 140 Z" fill="#FACC15"/>
            <rect x="46" y="176" width="228" height="54" rx="12" fill="#1E0B36" stroke="#00F0FF" stroke-width="4"/>
            <text x="160" y="213" font-family="'Outfit', sans-serif" font-weight="900" font-size="34" text-anchor="middle" fill="#FACC15" letter-spacing="1.5">PINEAPPLE</text>
            <rect x="96" y="232" width="128" height="44" rx="8" fill="#FF2A85" stroke="#1E0B36" stroke-width="5"/>
            <text x="160" y="263" font-family="'Outfit', sans-serif" font-weight="900" font-size="28" text-anchor="middle" fill="#FFFFFF" letter-spacing="3">SMP</text>
          </svg>
        </div>
        <div class="flex flex-col text-left">
          <span class="font-gta text-2xl sm:text-3xl tracking-wider text-white leading-none">
            PINEAPPLE<span class="text-transparent bg-clip-text bg-gradient-to-r from-vice-pink via-vice-orange to-vice-cyan">SMP</span>
          </span>
          <span class="text-[10px] font-extrabold uppercase tracking-widest text-vice-cyan mt-0.5">
            Vice Lifesteal Network
          </span>
        </div>
      </a>

      <!-- Center Navigation Links -->
      <nav class="hidden xl:flex items-center gap-5 text-xs font-extrabold uppercase tracking-wider text-slate-300">
        <a href="#status" class="hover:text-vice-cyan transition-colors">Status</a>
        <a href="#features" class="hover:text-vice-cyan transition-colors">Features</a>
        <a href="#kits-store" class="hover:text-vice-gold transition-colors">Kits Store</a>
        <a href="#funders" class="hover:text-vice-pink transition-colors">Funders</a>
        <a href="#partnerships" class="hover:text-vice-cyan transition-colors">Partners</a>
        <a href="#join-guide" class="hover:text-vice-cyan transition-colors">How to Join</a>
        <a href="#ai-support" class="hover:text-vice-pink transition-colors">AI Support</a>
      </nav>

      <!-- Far Right: Quick IP Copy & Vice Neon Discord CTA -->
      <div class="ml-auto flex items-center justify-end gap-2 sm:gap-3">
        <button onclick="copyToClipboard('basic.vitalcloud.in:19126', 'Copied Java IP & Port: basic.vitalcloud.in:19126')" title="Click to copy IP & Port" class="hidden md:flex items-center gap-2 bg-[#160D2E]/95 hover:bg-[#211342] text-slate-200 px-3.5 py-2 rounded-xl border border-vice-cyan/50 text-xs font-semibold tracking-wider transition-all hover:border-vice-pink active:scale-95 shadow-[0_0_15px_rgba(0,240,255,0.18)]">
          <span id="nav-status-dot" class="w-2 h-2 rounded-full bg-vice-cyan animate-pulse"></span>
          <span>IP: <strong class="text-vice-gold font-mono">basic.vitalcloud.in:19126</strong></span>
          <i class="fa-regular fa-copy text-vice-cyan text-[11px]"></i>
        </button>

        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="mc-btn shine-btn bg-gradient-to-r from-vice-pink via-vice-magenta to-vice-purple hover:from-vice-orange hover:to-vice-pink text-white font-extrabold px-3.5 py-2 sm:px-5 sm:py-2.5 rounded-xl text-xs sm:text-sm border border-white/25 transition-all flex items-center gap-2">
          <i class="fa-brands fa-discord text-sm"></i>
          <span>Discord</span>
        </a>
      </div>
    </div>
  </header>

  <main class="relative z-10">

    <!-- 3. GTA 6 VICE CITY SUNSET HERO SECTION -->
    <section id="home" class="relative pt-10 pb-14 md:pt-16 md:pb-22 max-w-6xl mx-auto px-4 text-center overflow-hidden">
      
      <!-- GTA 6 Vice Sunset Sun-Disk & Palm Silhouette Backdrop -->
      <div class="pointer-events-none select-none absolute inset-x-0 top-4 flex justify-center items-center z-0 opacity-85">
        <div class="relative w-[330px] h-[330px] sm:w-[430px] sm:h-[430px] rounded-full vice-sun-disk shadow-[0_0_110px_rgba(255,42,133,0.65)] blur-[0.5px]"></div>
      </div>

      <!-- Left & Right Vice City Palm Tree Silhouettes -->
      <svg viewBox="0 0 240 260" class="pointer-events-none select-none hidden md:block absolute left-2 top-16 w-48 lg:w-60 h-auto text-[#090414] opacity-90 z-0 drop-shadow-[0_0_12px_rgba(255,42,133,0.4)]" fill="currentColor">
        <path d="M55 260 C62 195, 76 145, 96 95 L106 98 C88 148, 76 198, 72 260 Z"/>
        <path d="M98 96 C68 72, 32 76, 10 98 C36 90, 66 92, 94 104 Z"/>
        <path d="M100 94 C78 58, 44 44, 16 54 C46 58, 72 72, 95 98 Z"/>
        <path d="M102 94 C104 54, 86 24, 62 14 C82 32, 92 60, 97 95 Z"/>
        <path d="M104 95 C128 62, 160 52, 186 64 C158 66, 130 78, 106 100 Z"/>
        <path d="M104 98 C136 86, 168 96, 188 118 C162 108, 134 102, 104 104 Z"/>
      </svg>
      <svg viewBox="0 0 240 260" class="pointer-events-none select-none hidden md:block absolute right-2 top-16 w-48 lg:w-60 h-auto text-[#090414] opacity-90 z-0 -scale-x-100 drop-shadow-[0_0_12px_rgba(0,240,255,0.35)]" fill="currentColor">
        <path d="M55 260 C62 195, 76 145, 96 95 L106 98 C88 148, 76 198, 72 260 Z"/>
        <path d="M98 96 C68 72, 32 76, 10 98 C36 90, 66 92, 94 104 Z"/>
        <path d="M100 94 C78 58, 44 44, 16 54 C46 58, 72 72, 95 98 Z"/>
        <path d="M102 94 C104 54, 86 24, 62 14 C82 32, 92 60, 97 95 Z"/>
        <path d="M104 95 C128 62, 160 52, 186 64 C158 66, 130 78, 106 100 Z"/>
        <path d="M104 98 C136 86, 168 96, 188 118 C162 108, 134 102, 104 104 Z"/>
      </svg>

      <!-- GTA 6 Vice Neon PineappleSMP Crest -->
      <div class="relative z-10 flex justify-center mb-6">
        <div class="relative w-64 h-64 sm:w-72 sm:h-72 md:w-80 md:h-80 animate-float flex items-center justify-center">
          <div class="absolute inset-0 bg-gradient-to-tr from-vice-pink/35 via-vice-orange/25 to-vice-cyan/35 blur-3xl rounded-full scale-95 pointer-events-none"></div>
          
          <div id="hero-logo-box" class="relative w-full h-full rounded-3xl p-3 sm:p-4 bg-gradient-to-br from-[#230B3B]/80 via-[#0E0720]/90 to-[#08263A]/85 border-2 border-vice-cyan/70 shadow-[0_0_60px_rgba(255,42,133,0.5)] flex items-center justify-center overflow-hidden backdrop-blur-md">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 380 340" class="w-full h-full filter drop-shadow-[0_12px_24px_rgba(0,0,0,0.85)]">
              <defs>
                <linearGradient id="heroViceTop" x1="0" y1="0" x2="1" y2="1">
                  <stop offset="0%" stop-color="#FEF9C3"/>
                  <stop offset="50%" stop-color="#FACC15"/>
                  <stop offset="100%" stop-color="#FF8C24"/>
                </linearGradient>
                <linearGradient id="heroViceFront" x1="0" y1="0" x2="0" y2="1">
                  <stop offset="0%" stop-color="#FF7A2F"/>
                  <stop offset="55%" stop-color="#FF2A85"/>
                  <stop offset="100%" stop-color="#C026D3"/>
                </linearGradient>
                <linearGradient id="heroViceSide" x1="0" y1="0" x2="1" y2="1">
                  <stop offset="0%" stop-color="#A855F7"/>
                  <stop offset="100%" stop-color="#4C1D95"/>
                </linearGradient>
                <linearGradient id="heroViceLeafMain" x1="0" y1="1" x2="0" y2="0">
                  <stop offset="0%" stop-color="#0284C7"/>
                  <stop offset="55%" stop-color="#00F0FF"/>
                  <stop offset="100%" stop-color="#CFFAFE"/>
                </linearGradient>
                <linearGradient id="heroViceLeafDark" x1="0" y1="1" x2="0" y2="0">
                  <stop offset="0%" stop-color="#1E1B4B"/>
                  <stop offset="100%" stop-color="#0891B2"/>
                </linearGradient>
                <linearGradient id="heroViceText" x1="0" y1="0" x2="1" y2="0">
                  <stop offset="0%" stop-color="#00F0FF"/>
                  <stop offset="35%" stop-color="#FFFFFF"/>
                  <stop offset="70%" stop-color="#FACC15"/>
                  <stop offset="100%" stop-color="#FF2A85"/>
                </linearGradient>
                <linearGradient id="heroVicePlank" x1="0" y1="0" x2="1" y2="0">
                  <stop offset="0%" stop-color="#FF2A85"/>
                  <stop offset="50%" stop-color="#D946EF"/>
                  <stop offset="100%" stop-color="#7C3AED"/>
                </linearGradient>
              </defs>

              <circle cx="190" cy="145" r="118" fill="#FF2A85" opacity="0.18"/>
              <circle cx="190" cy="145" r="88" fill="#00F0FF" opacity="0.14"/>

              <path d="M174 78 C154 42, 134 24, 122 34 C132 54, 150 70, 170 82 Z" fill="url(#heroViceLeafDark)" stroke="#0F172A" stroke-width="4" stroke-linejoin="round"/>
              <path d="M206 78 C226 42, 246 24, 258 34 C248 54, 230 70, 210 82 Z" fill="url(#heroViceLeafDark)" stroke="#0F172A" stroke-width="4" stroke-linejoin="round"/>

              <path d="M190 74 C180 34, 174 10, 190 4 C206 10, 200 34, 190 74 Z" fill="url(#heroViceLeafMain)" stroke="#0F172A" stroke-width="4.5" stroke-linejoin="round"/>
              <path d="M180 78 C156 46, 130 36, 120 48 C134 66, 158 76, 178 82 Z" fill="url(#heroViceLeafMain)" stroke="#0F172A" stroke-width="4.5" stroke-linejoin="round"/>
              <path d="M200 78 C224 46, 250 36, 260 48 C246 66, 222 76, 202 82 Z" fill="url(#heroViceLeafMain)" stroke="#0F172A" stroke-width="4.5" stroke-linejoin="round"/>
              <path d="M170 84 C140 68, 112 68, 104 80 C124 92, 148 92, 170 88 Z" fill="url(#heroViceLeafMain)" stroke="#0F172A" stroke-width="4" stroke-linejoin="round"/>
              <path d="M210 84 C240 68, 268 68, 276 80 C256 92, 232 92, 210 88 Z" fill="url(#heroViceLeafMain)" stroke="#0F172A" stroke-width="4" stroke-linejoin="round"/>

              <polygon points="190,68 264,96 190,124 116,96" fill="url(#heroViceTop)" stroke="#1E1B4B" stroke-width="5.5" stroke-linejoin="round"/>
              <polygon points="116,96 190,124 190,206 116,178" fill="url(#heroViceSide)" stroke="#1E1B4B" stroke-width="5.5" stroke-linejoin="round"/>
              <polygon points="190,124 264,96 264,178 190,206" fill="url(#heroViceFront)" stroke="#1E1B4B" stroke-width="5.5" stroke-linejoin="round"/>

              <path d="M153 82 L227 110 M227 82 L153 110" stroke="#FFFBEB" stroke-width="2.5" opacity="0.55"/>
              <path d="M126 112 L180 192 M148 118 L186 174 M176 122 L124 170 M152 112 L120 144" stroke="#311042" stroke-width="3.2" opacity="0.55"/>
              <path d="M200 132 L254 172 M224 116 L260 146 M252 112 L198 192 M228 118 L194 172" stroke="#581C87" stroke-width="3" opacity="0.45"/>

              <!-- Vice Sunglasses / Neon Eyes -->
              <rect x="200" y="144" width="18" height="14" rx="2.5" fill="#090612" stroke="#00F0FF" stroke-width="2"/>
              <line x1="218" y1="149" x2="236" y2="142" stroke="#00F0FF" stroke-width="2.5"/>
              <rect x="236" y="131" width="18" height="14" rx="2.5" fill="#090612" stroke="#00F0FF" stroke-width="2"/>
              <line x1="204" y1="148" x2="213" y2="154" stroke="#FF2A85" stroke-width="2"/>
              <line x1="240" y1="135" x2="249" y2="141" stroke="#FF2A85" stroke-width="2"/>
              <path d="M220 158 Q228 169 235 154 Z" fill="#FACC15" stroke="#1E1B4B" stroke-width="1.5"/>

              <polygon points="82,66 85,73 92,76 85,79 82,86 79,79 72,76 79,73" fill="#00F0FF"/>
              <polygon points="300,64 303,71 310,74 303,77 300,84 297,77 290,74 297,71" fill="#FF2A85"/>
              <rect x="92" y="130" width="6" height="6" rx="1" fill="#00F0FF"/>
              <rect x="284" y="128" width="6" height="6" rx="1" fill="#FACC15"/>

              <g filter="drop-shadow(0px 8px 8px rgba(0,0,0,0.9))">
                <text x="190" y="255" font-family="'Outfit', 'Impact', sans-serif" font-weight="900" font-size="52" text-anchor="middle" fill="#140726" stroke="#140726" stroke-width="16" stroke-linejoin="round" letter-spacing="2">PINEAPPLE</text>
                <text x="190" y="250" font-family="'Outfit', 'Impact', sans-serif" font-weight="900" font-size="52" text-anchor="middle" fill="#831843" stroke="#FF2A85" stroke-width="6" stroke-linejoin="round" letter-spacing="2">PINEAPPLE</text>
                <text x="190" y="246" font-family="'Outfit', 'Impact', sans-serif" font-weight="900" font-size="52" text-anchor="middle" fill="url(#heroViceText)" letter-spacing="2">PINEAPPLE</text>
              </g>

              <g filter="drop-shadow(0px 6px 10px rgba(255,42,133,0.6))">
                <rect x="106" y="268" width="168" height="54" rx="10" fill="#140726" stroke="#00F0FF" stroke-width="3.5"/>
                <rect x="111" y="272" width="158" height="46" rx="7" fill="url(#heroVicePlank)"/>
                <text x="190" y="305" font-family="'Press Start 2P', 'Outfit', monospace" font-weight="900" font-size="25" text-anchor="middle" fill="#140726" letter-spacing="4">SMP</text>
                <text x="190" y="302" font-family="'Press Start 2P', 'Outfit', monospace" font-weight="900" font-size="25" text-anchor="middle" fill="#FFFFFF" letter-spacing="4">SMP</text>
              </g>
            </svg>
          </div>
        </div>
      </div>

      <!-- GTA 6 Vice Edition Hero Headlines -->
      <div class="relative z-10 inline-flex items-center gap-2 bg-[#160B2E]/90 border border-vice-cyan/60 px-5 py-2 rounded-full text-vice-cyan text-xs sm:text-sm font-black uppercase tracking-widest mb-5 shadow-[0_0_25px_rgba(0,240,255,0.3)] backdrop-blur-md">
        <i class="fa-solid fa-sun text-vice-gold"></i> SEASON 1 LAUNCHED &bull; BEDROCK + JAVA CROSSPLAY
      </div>

      <h1 class="relative z-10 font-gta text-5xl sm:text-7xl md:text-8xl text-white tracking-wider uppercase pineapple-text-glow leading-[0.95]">
        PINEAPPLE SMP <br/>
        <span class="text-transparent bg-clip-text bg-gradient-to-r from-vice-cyan via-vice-pink to-vice-gold">SEASON 1 LAUNCHED</span>
      </h1>
      
      <p class="relative z-10 mt-5 text-slate-200 max-w-2xl mx-auto text-base sm:text-lg leading-relaxed font-medium drop-shadow">
        Welcome to Vice Lifesteal — Jump into the ultimate Minecraft Lifesteal SMP adventure with Bedrock &amp; Java crossplay, hosted 24/7 on VitalCloud!
      </p>

      <!-- Vice Neon Quick Join Buttons -->
      <div class="relative z-10 mt-8 flex flex-wrap justify-center gap-3.5">
        <button onclick="copyToClipboard('basic.vitalcloud.in:19126', 'Copied Java IP & Port: basic.vitalcloud.in:19126')" class="mc-btn shine-btn bg-gradient-to-r from-vice-pink via-vice-orange to-vice-gold text-slate-950 font-black px-5 py-3.5 rounded-xl text-xs sm:text-sm flex items-center gap-2 border border-white/40">
          <i class="fa-solid fa-desktop text-sm"></i>
          <span>Java: <span class="font-mono">basic.vitalcloud.in:19126</span></span>
        </button>
        <button onclick="copyToClipboard('basic.vitalcloud.in', 'Copied Bedrock IP: basic.vitalcloud.in')" class="mc-btn shine-btn bg-[#150C2E]/95 hover:bg-[#1F1242] text-vice-cyan border border-vice-cyan/70 font-bold px-5 py-3.5 rounded-xl text-xs sm:text-sm flex items-center gap-2">
          <i class="fa-solid fa-mobile-screen text-sm text-vice-pink"></i>
          <span>Bedrock IP: <span class="font-mono text-white">basic.vitalcloud.in</span></span>
        </button>
        <button onclick="copyToClipboard('19149', 'Copied Bedrock Port: 19149')" class="mc-btn shine-btn bg-[#150C2E]/95 hover:bg-[#1F1242] text-vice-gold border border-vice-pink/70 font-bold px-5 py-3.5 rounded-xl text-xs sm:text-sm flex items-center gap-2">
          <i class="fa-solid fa-plug text-sm text-vice-cyan"></i>
          <span>Port: <span class="font-mono text-white">19149</span></span>
        </button>
        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="mc-btn shine-btn bg-gradient-to-r from-[#5865F2] to-vice-purple text-white font-extrabold px-5 py-3.5 rounded-xl text-xs sm:text-sm flex items-center gap-2 border border-white/25">
          <i class="fa-brands fa-discord text-lg"></i>
          <span>Join Discord</span>
        </a>
      </div>

      <!-- 4. LIVE SERVER STATUS & PLAYER ROSTER (AUTO-REFRESH EVERY 5 SECONDS) -->
      <div id="status" class="relative z-10 mt-12 max-w-4xl mx-auto">
        <div class="flex flex-wrap items-center justify-between gap-2 px-2 mb-2.5">
          <div class="flex flex-wrap items-center gap-2 text-xs text-slate-300">
            <span id="telemetry-dot" class="inline-block w-2 h-2 rounded-full bg-vice-cyan animate-ping"></span>
            <span>Live Telemetry (<span class="font-mono text-vice-gold">Java :19126 | Bedrock :19149</span>)</span>
            <span class="inline-flex items-center gap-1 px-2.5 py-0.5 rounded-full bg-vice-pink/20 border border-vice-pink/50 text-pink-200 font-bold text-[10px]">
              <i class="fa-solid fa-bolt text-vice-cyan"></i> Auto-Sync: Every 5s
            </span>
            <span id="last-updated-text" class="text-[11px] text-slate-400 font-mono">(Connecting...)</span>
          </div>
          <button id="refresh-status-btn" onclick="fetchLiveServerStatus(true)" class="flex items-center gap-1.5 bg-[#190F36]/95 hover:bg-[#24164D] text-vice-cyan hover:text-white text-xs font-semibold px-3 py-1.5 rounded-lg border border-vice-cyan/50 transition-all hover:border-vice-pink shadow-sm active:scale-95">
            <i id="refresh-icon" class="fa-solid fa-arrows-rotate text-[11px]"></i>
            <span>Sync Now</span>
          </button>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4 text-left">
          
          <!-- Server Status Card -->
          <div class="mc-panel p-4 rounded-xl relative overflow-hidden group">
            <div class="text-xs text-slate-300 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Server Status</span>
              <span id="ping-latency-badge" class="text-[10px] bg-slate-900 px-2 py-0.5 rounded text-vice-gold font-mono">PINGING</span>
            </div>
            <div id="server-status-badge" class="font-bold flex items-center gap-2 text-base mt-1.5 text-amber-400">
              <span id="server-status-dot" class="w-2.5 h-2.5 rounded-full bg-amber-400 shadow-[0_0_10px_#f59e0b] animate-pulse"></span>
              <span id="server-status-text">Checking...</span>
            </div>
            <div id="server-version-text" class="text-[10px] text-slate-400 mt-1 font-mono truncate">Bedrock 1.20 - 1.21+ / Java</div>

            <div class="mt-3 pt-2.5 border-t border-vice-pink/25 text-center">
              <div class="inline-block py-1 px-3 rounded-lg bg-gradient-to-r from-vice-pink/25 via-vice-purple/25 to-vice-cyan/25 border border-vice-cyan/50 shadow-inner">
                <span class="font-heading font-black text-xs sm:text-sm tracking-widest text-transparent bg-clip-text bg-gradient-to-r from-vice-cyan via-white to-vice-gold">
                  basic.vitalcloud.in
                </span>
              </div>
              <div class="text-[10px] font-bold text-vice-cyan mt-1 uppercase tracking-wider flex items-center justify-center gap-1">
                <span>Java: 19126 | Bedrock: 19149</span>
              </div>
            </div>
          </div>

          <!-- Players Online Tracker -->
          <div class="mc-panel p-4 rounded-xl relative overflow-hidden group">
            <div class="text-xs text-slate-300 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Players Online</span>
              <i class="fa-solid fa-users text-vice-pink text-xs"></i>
            </div>
            <div class="flex items-baseline gap-1.5 mt-1">
              <span id="server-players-online" class="text-2xl font-black font-mono text-white tracking-tight">0</span>
              <span id="server-players-max" class="text-xs text-slate-400 font-mono">/ 50</span>
            </div>
            <div class="text-[10px] text-vice-gold font-medium mt-0.5 flex items-center gap-1">
              <span id="players-pulse-dot" class="w-1.5 h-1.5 rounded-full bg-vice-gold animate-pulse"></span>
              <span id="server-players-status">Querying live server...</span>
            </div>

            <!-- In-Card Username Roster -->
            <div class="mt-2.5 pt-2.5 border-t border-vice-pink/25">
              <div class="text-[10px] uppercase font-bold text-slate-300 flex items-center justify-between mb-1.5">
                <span>Active Roster:</span>
                <span id="roster-count-tag" class="font-mono text-vice-cyan text-[9px] bg-[#0B061A] px-1.5 py-0.5 rounded border border-vice-cyan/30">5S SYNC</span>
              </div>
              <div id="card-players-list" class="flex flex-wrap gap-1.5 max-h-24 overflow-y-auto pr-1">
                <span class="text-[11px] text-slate-400 italic">Checking active players...</span>
              </div>
            </div>
          </div>

          <!-- SMP Mode Card -->
          <div class="mc-panel p-4 rounded-xl relative overflow-hidden">
            <div class="text-xs text-slate-300 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Game Mode</span>
              <i class="fa-solid fa-heart text-vice-pink text-xs"></i>
            </div>
            <div class="text-white font-bold text-base mt-1.5 flex items-center gap-1.5">
              <span class="text-vice-pink">&#10084;&#65039;</span> Lifesteal SMP
            </div>
            <div class="text-[10px] text-slate-400 mt-1">Kill = +1 Heart | Death = -1 Heart</div>
          </div>

          <!-- Crossplay Info Card -->
          <div onclick="copyToClipboard('19149', 'Copied Bedrock Port: 19149')" class="mc-panel p-4 rounded-xl relative overflow-hidden cursor-pointer group">
            <div class="text-xs text-slate-300 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Bedrock Port</span>
              <i class="fa-regular fa-copy text-vice-cyan text-xs group-hover:scale-110 transition-transform"></i>
            </div>
            <div class="text-vice-gold font-mono font-bold text-base mt-1.5">19149</div>
            <div class="text-[10px] text-vice-cyan mt-1 font-mono truncate">basic.vitalcloud.in</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Vice City Neon Sunset Divider -->
    <div class="mc-grass-divider my-2"></div>

    <!-- 5. STEP-BY-STEP HOW TO JOIN (1 BEDROCK CARD + 1 JAVA CARD SIDE-BY-SIDE) -->
    <section id="join-guide" class="py-14 max-w-5xl mx-auto px-4 sm:px-6">
      <div class="text-center mb-10">
        <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-vice-cyan/15 border border-vice-cyan/40 text-vice-cyan text-xs font-bold uppercase tracking-widest mb-3">
          <i class="fa-solid fa-gamepad"></i> Easy 1-Minute Setup
        </div>
        <h2 class="font-gta text-4xl sm:text-6xl text-white tracking-wider">HOW TO JOIN PINEAPPLE SMP</h2>
        <p class="text-slate-300 text-sm mt-1">Supported on Phone (Pocket Edition), Console (Xbox, PS, Switch), Windows 10/11 &amp; PC Java!</p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
        
        <!-- Bedrock Connection Card -->
        <div class="bg-gradient-to-br from-[#2A0D45]/75 via-[#130B29] to-[#0A253B]/75 border-2 border-vice-pink/80 p-6 rounded-2xl relative overflow-hidden shadow-[0_0_35px_rgba(255,42,133,0.22)]">
          <div class="flex items-center justify-between mb-4">
            <span class="text-xs uppercase font-black px-3 py-1 bg-gradient-to-r from-vice-pink to-vice-orange text-white rounded-lg shadow">
              Bedrock / Pocket Edition
            </span>
            <span class="text-xs text-vice-cyan font-bold">Crossplay Ready</span>
          </div>

          <div class="space-y-3.5 text-xs text-slate-200">
            <div class="flex items-start gap-2.5">
              <span class="w-5 h-5 rounded-full bg-vice-pink/25 text-vice-gold font-bold flex items-center justify-center shrink-0 border border-vice-pink/50">1</span>
              <span>Open Minecraft on your phone, console, or Windows 10/11 PC.</span>
            </div>
            <div class="flex items-start gap-2.5">
              <span class="w-5 h-5 rounded-full bg-vice-pink/25 text-vice-gold font-bold flex items-center justify-center shrink-0 border border-vice-pink/50">2</span>
              <span>Tap <strong>Play</strong> &rarr; Click the <strong>Servers</strong> tab &rarr; Scroll down and tap <strong>Add Server</strong>.</span>
            </div>
            <div class="flex items-start gap-2.5">
              <span class="w-5 h-5 rounded-full bg-vice-pink/25 text-vice-gold font-bold flex items-center justify-center shrink-0 border border-vice-pink/50">3</span>
              <div class="flex-1">
                Enter the exact Bedrock server details below:
              </div>
            </div>
          </div>

          <div class="mt-4 bg-[#090514]/95 border border-vice-cyan/40 rounded-xl p-3.5 space-y-2.5 text-xs">
            <div class="flex items-center justify-between">
              <span class="text-slate-400 font-semibold">Server Name:</span>
              <span class="text-white font-bold font-mono">PineappleSMP</span>
            </div>
            <div class="flex items-center justify-between border-t border-slate-800/80 pt-2">
              <span class="text-slate-400 font-semibold">Server Address:</span>
              <div class="flex items-center gap-2">
                <span class="text-vice-gold font-mono font-bold">basic.vitalcloud.in</span>
                <button onclick="copyToClipboard('basic.vitalcloud.in', 'Copied Bedrock IP: basic.vitalcloud.in')" class="text-slate-400 hover:text-vice-cyan" title="Copy IP">
                  <i class="fa-regular fa-copy"></i>
                </button>
              </div>
            </div>
            <div class="flex items-center justify-between border-t border-slate-800/80 pt-2">
              <span class="text-slate-400 font-semibold">Port:</span>
              <div class="flex items-center gap-2">
                <span class="text-vice-cyan font-mono font-extrabold text-sm">19149</span>
                <button onclick="copyToClipboard('19149', 'Copied Bedrock Port: 19149')" class="text-slate-400 hover:text-vice-cyan" title="Copy Port">
                  <i class="fa-regular fa-copy"></i>
                </button>
              </div>
            </div>
          </div>

          <div class="mt-4 flex gap-2">
            <button onclick="copyToClipboard('basic.vitalcloud.in', 'Copied Bedrock IP: basic.vitalcloud.in')" class="mc-btn shine-btn flex-1 bg-gradient-to-r from-vice-pink to-vice-orange text-white font-black py-2.5 px-3 rounded-xl text-xs transition-all flex items-center justify-center gap-1.5 shadow-md">
              <i class="fa-regular fa-copy"></i>
              <span>Copy Bedrock IP</span>
            </button>
            <button onclick="copyToClipboard('19149', 'Copied Bedrock Port: 19149')" class="mc-btn shine-btn flex-1 bg-gradient-to-r from-vice-cyan to-sky-500 text-slate-950 font-black py-2.5 px-3 rounded-xl text-xs transition-all flex items-center justify-center gap-1.5 shadow-md">
              <i class="fa-solid fa-plug"></i>
              <span>Copy Port (19149)</span>
            </button>
          </div>
        </div>

        <!-- Java Connection Card -->
        <div class="mc-panel p-6 rounded-2xl relative overflow-hidden flex flex-col justify-between">
          <div>
            <div class="flex items-center justify-between mb-4">
              <span class="text-xs uppercase font-extrabold px-3 py-1 bg-[#1D113B] text-vice-cyan border border-vice-cyan/40 rounded-lg">
                Java Edition (PC)
              </span>
              <span class="text-xs text-slate-300">1.19 - 1.21+</span>
            </div>

            <div class="space-y-3.5 text-xs text-slate-200">
              <div class="flex items-start gap-2.5">
                <span class="w-5 h-5 rounded-full bg-[#1D113B] text-vice-cyan font-bold flex items-center justify-center shrink-0 border border-vice-cyan/40">1</span>
                <span>Launch Minecraft Java Edition.</span>
              </div>
              <div class="flex items-start gap-2.5">
                <span class="w-5 h-5 rounded-full bg-[#1D113B] text-vice-cyan font-bold flex items-center justify-center shrink-0 border border-vice-cyan/40">2</span>
                <span>Click <strong>Multiplayer</strong> &rarr; Click <strong>Direct Connection</strong> or <strong>Add Server</strong>.</span>
              </div>
              <div class="flex items-start gap-2.5">
                <span class="w-5 h-5 rounded-full bg-[#1D113B] text-vice-cyan font-bold flex items-center justify-center shrink-0 border border-vice-cyan/40">3</span>
                <span>Enter the Server Address below to connect:</span>
              </div>
            </div>

            <div class="mt-4 bg-[#090514]/95 border border-vice-pink/35 rounded-xl p-3.5 space-y-2 text-xs">
              <div class="text-slate-400 uppercase font-semibold text-[10px]">Server Address:</div>
              <div class="flex items-center justify-between">
                <span class="font-mono font-bold text-vice-gold text-sm">basic.vitalcloud.in:19126</span>
                <button onclick="copyToClipboard('basic.vitalcloud.in:19126', 'Copied Java IP: basic.vitalcloud.in:19126')" class="text-slate-400 hover:text-vice-cyan" title="Copy Address">
                  <i class="fa-regular fa-copy"></i>
                </button>
              </div>
            </div>
          </div>

          <div class="mt-4">
            <button onclick="copyToClipboard('basic.vitalcloud.in:19126', 'Copied Java Address: basic.vitalcloud.in:19126')" class="mc-btn w-full bg-[#1E113D] hover:bg-[#2A1854] text-white border border-vice-cyan/50 font-bold py-2.5 px-4 rounded-xl text-xs transition-all flex items-center justify-center gap-2">
              <i class="fa-regular fa-copy text-vice-gold"></i>
              <span>Copy Java IP &amp; Port</span>
            </button>
          </div>
        </div>

      </div>
    </section>

    <!-- Vice City Neon Sunset Divider -->
    <div class="mc-grass-divider my-2"></div>

    <!-- 6. OFFICIAL BATTLE KITS & 3-DAY INSURANCE STORE SECTION -->
    <section id="kits-store" class="py-16 max-w-7xl mx-auto px-4 sm:px-6 relative">
      <div class="text-center mb-10">
        <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-gradient-to-r from-vice-pink/20 to-vice-cyan/20 border border-vice-pink/50 text-vice-gold text-xs font-extrabold uppercase tracking-widest mb-3 shadow">
          <i class="fa-solid fa-shield-heart text-vice-cyan"></i> Vice Armory &bull; 3-Day Damage Insurance Included
        </div>
        <h2 class="font-gta text-4xl sm:text-6xl text-white tracking-wider">
          BATTLE KITS &amp; <span class="text-transparent bg-clip-text bg-gradient-to-r from-vice-cyan via-vice-pink to-vice-gold">GEAR STORE</span>
        </h2>
        <p class="text-slate-300 text-xs sm:text-sm mt-3 max-w-2xl mx-auto leading-relaxed">
          Gear up instantly for Lifesteal PvP! Every kit includes <strong class="text-vice-cyan">+10% Insurance GST</strong> which activates a <strong class="text-vice-gold">3-Day Kit Damage Insurance Guarantee</strong>.
        </p>

        <!-- 10% GST = 3-Day Kit Damage Insurance Policy Banner -->
        <div class="mt-6 max-w-3xl mx-auto bg-gradient-to-r from-[#260B3B]/90 via-[#120A26]/95 to-[#082438]/90 border-2 border-vice-cyan/55 rounded-2xl p-4 sm:p-5 shadow-[0_0_32px_rgba(0,240,255,0.18)] flex flex-col sm:flex-row items-center gap-4 text-left">
          <div class="w-12 h-12 rounded-2xl bg-vice-cyan/15 border border-vice-cyan/50 text-vice-cyan flex items-center justify-center text-2xl shrink-0">
            <i class="fa-solid fa-shield-halved"></i>
          </div>
          <div class="flex-1 text-xs sm:text-sm text-slate-200 leading-relaxed">
            <div class="font-heading font-black text-vice-cyan uppercase tracking-wider text-xs sm:text-sm mb-0.5">
              10% GST = 3-Day Kit Damage Insurance Protection
            </div>
            <p>
              If your purchased kit gets damaged within <strong class="text-white">3 days of purchase</strong>, our staff team will either <strong class="text-vice-gold">repair your kit completely</strong> or provide a <strong class="text-vice-pink">brand-new replacement kit</strong>!
            </p>
          </div>
        </div>
      </div>

      <!-- 5 Kits Grid -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-5 gap-5">

        <!-- 1. STONE KIT -->
        <div class="mc-panel rounded-2xl p-5 flex flex-col justify-between transition-all duration-300 hover:-translate-y-1.5 relative overflow-hidden group">
          <div>
            <div class="flex items-center justify-between mb-3">
              <span class="text-[10px] font-extrabold uppercase tracking-wider px-2.5 py-0.5 rounded-md bg-slate-900 text-slate-300 border border-slate-600">Starter Tier</span>
              <span class="text-[10px] font-bold text-vice-cyan flex items-center gap-1"><i class="fa-solid fa-shield-check"></i> 3d Insured</span>
            </div>
            <div class="w-16 h-16 mx-auto my-3 rounded-2xl bg-[#090514] border border-slate-700 flex items-center justify-center p-2.5 group-hover:scale-110 transition-transform shadow-inner">
              <svg viewBox="0 0 64 64" class="w-full h-full">
                <polygon points="46,10 54,10 54,18 34,38 26,30" fill="#94A3B8" stroke="#334155" stroke-width="2.5"/>
                <polygon points="46,10 54,10 50,14 30,34 26,30" fill="#CBD5E1"/>
                <rect x="20" y="32" width="14" height="5" rx="1" transform="rotate(-45 27 34.5)" fill="#64748B" stroke="#1E293B" stroke-width="2"/>
                <rect x="13" y="42" width="11" height="5" rx="1" transform="rotate(-45 18.5 44.5)" fill="#78350F" stroke="#451A03" stroke-width="2"/>
                <rect x="10" y="48" width="6" height="6" rx="1" fill="#94A3B8" stroke="#1E293B" stroke-width="2"/>
              </svg>
            </div>
            <h3 class="text-xl font-heading font-black text-white text-center">Stone Kit</h3>
            <p class="text-[11px] text-slate-400 text-center mt-1">Full Stone Gear, Sword, Tools, Shield &amp; Golden Apples</p>

            <div class="mt-4 bg-[#090514]/95 border border-slate-800 rounded-xl p-3 space-y-1.5 text-xs">
              <div class="flex justify-between text-slate-400">
                <span>Base Price:</span>
                <span class="font-mono text-slate-200">&#8377;30</span>
              </div>
              <div class="flex justify-between text-vice-cyan">
                <span>10% Insurance GST:</span>
                <span class="font-mono">+&#8377;3</span>
              </div>
              <div class="border-t border-slate-800 pt-1.5 flex justify-between items-baseline">
                <span class="font-bold text-white">Total Payable:</span>
                <span class="font-heading font-black text-lg text-vice-gold">&#8377;33</span>
              </div>
            </div>
          </div>

          <button type="button" onclick="openKitCheckout('Stone Kit', 30, 3, 33)" class="mc-btn shine-btn mt-4 w-full bg-gradient-to-r from-slate-600 to-slate-500 text-white font-extrabold py-3 px-4 rounded-xl text-xs uppercase tracking-wider flex items-center justify-center gap-2">
            <i class="fa-solid fa-cart-shopping"></i>
            <span>Buy Stone Kit</span>
          </button>
        </div>

        <!-- 2. IRON KIT -->
        <div class="mc-panel rounded-2xl p-5 flex flex-col justify-between transition-all duration-300 hover:-translate-y-1.5 relative overflow-hidden group">
          <div>
            <div class="flex items-center justify-between mb-3">
              <span class="text-[10px] font-extrabold uppercase tracking-wider px-2.5 py-0.5 rounded-md bg-zinc-900 text-zinc-200 border border-zinc-500/60">Warrior Tier</span>
              <span class="text-[10px] font-bold text-vice-cyan flex items-center gap-1"><i class="fa-solid fa-shield-check"></i> 3d Insured</span>
            </div>
            <div class="w-16 h-16 mx-auto my-3 rounded-2xl bg-[#090514] border border-zinc-600/60 flex items-center justify-center p-2.5 group-hover:scale-110 transition-transform shadow-inner">
              <svg viewBox="0 0 64 64" class="w-full h-full">
                <path d="M16 14 L26 14 L28 20 L36 20 L38 14 L48 14 L52 26 L44 30 L44 50 L20 50 L20 30 L12 26 Z" fill="#E2E8F0" stroke="#475569" stroke-width="2.5" stroke-linejoin="round"/>
                <path d="M24 22 L40 22 L40 46 L24 46 Z" fill="#CBD5E1"/>
                <rect x="28" y="26" width="8" height="14" rx="1" fill="#94A3B8"/>
              </svg>
            </div>
            <h3 class="text-xl font-heading font-black text-white text-center">Iron Kit</h3>
            <p class="text-[11px] text-slate-400 text-center mt-1">Protection Iron Armor, Sharpness Sword, Bow &amp; Pearls</p>

            <div class="mt-4 bg-[#090514]/95 border border-slate-800 rounded-xl p-3 space-y-1.5 text-xs">
              <div class="flex justify-between text-slate-400">
                <span>Base Price:</span>
                <span class="font-mono text-slate-200">&#8377;50</span>
              </div>
              <div class="flex justify-between text-vice-cyan">
                <span>10% Insurance GST:</span>
                <span class="font-mono">+&#8377;5</span>
              </div>
              <div class="border-t border-slate-800 pt-1.5 flex justify-between items-baseline">
                <span class="font-bold text-white">Total Payable:</span>
                <span class="font-heading font-black text-lg text-vice-gold">&#8377;55</span>
              </div>
            </div>
          </div>

          <button type="button" onclick="openKitCheckout('Iron Kit', 50, 5, 55)" class="mc-btn shine-btn mt-4 w-full bg-gradient-to-r from-zinc-100 to-slate-300 text-slate-950 font-black py-3 px-4 rounded-xl text-xs uppercase tracking-wider flex items-center justify-center gap-2">
            <i class="fa-solid fa-cart-shopping"></i>
            <span>Buy Iron Kit</span>
          </button>
        </div>

        <!-- 3. DIAMOND KIT -->
        <div class="mc-panel rounded-2xl p-5 flex flex-col justify-between transition-all duration-300 hover:-translate-y-1.5 border-vice-cyan/70 relative overflow-hidden group shadow-[0_0_28px_rgba(0,240,255,0.16)]">
          <div>
            <div class="flex items-center justify-between mb-3">
              <span class="text-[10px] font-extrabold uppercase tracking-wider px-2.5 py-0.5 rounded-md bg-cyan-950 text-vice-cyan border border-vice-cyan/60">Popular</span>
              <span class="text-[10px] font-bold text-vice-cyan flex items-center gap-1"><i class="fa-solid fa-shield-check"></i> 3d Insured</span>
            </div>
            <div class="w-16 h-16 mx-auto my-3 rounded-2xl bg-cyan-950/60 border border-vice-cyan/60 flex items-center justify-center p-2.5 group-hover:scale-110 transition-transform shadow-inner">
              <svg viewBox="0 0 64 64" class="w-full h-full">
                <polygon points="22,12 42,12 54,26 32,52 10,26" fill="#00F0FF" stroke="#0E7490" stroke-width="2.5" stroke-linejoin="round"/>
                <polygon points="22,12 42,12 38,26 26,26" fill="#CFFAFE"/>
                <polygon points="10,26 26,26 32,52" fill="#06B6D4"/>
                <polygon points="54,26 38,26 32,52" fill="#0891B2"/>
              </svg>
            </div>
            <h3 class="text-xl font-heading font-black text-vice-cyan text-center">Diamond Kit</h3>
            <p class="text-[11px] text-slate-300 text-center mt-1">Enchanted Diamond Set, Sharpness Sword, Totem &amp; Gapples</p>

            <div class="mt-4 bg-[#090514]/95 border border-cyan-900/60 rounded-xl p-3 space-y-1.5 text-xs">
              <div class="flex justify-between text-slate-400">
                <span>Base Price:</span>
                <span class="font-mono text-slate-200">&#8377;100</span>
              </div>
              <div class="flex justify-between text-vice-cyan">
                <span>10% Insurance GST:</span>
                <span class="font-mono">+&#8377;10</span>
              </div>
              <div class="border-t border-slate-800 pt-1.5 flex justify-between items-baseline">
                <span class="font-bold text-white">Total Payable:</span>
                <span class="font-heading font-black text-lg text-vice-cyan">&#8377;110</span>
              </div>
            </div>
          </div>

          <button type="button" onclick="openKitCheckout('Diamond Kit', 100, 10, 110)" class="mc-btn shine-btn mt-4 w-full bg-gradient-to-r from-vice-cyan to-sky-400 text-slate-950 font-black py-3 px-4 rounded-xl text-xs uppercase tracking-wider flex items-center justify-center gap-2">
            <i class="fa-solid fa-cart-shopping"></i>
            <span>Buy Diamond Kit</span>
          </button>
        </div>

        <!-- 4. NETHERITE KIT -->
        <div class="mc-panel rounded-2xl p-5 flex flex-col justify-between transition-all duration-300 hover:-translate-y-1.5 border-vice-orange/75 relative overflow-hidden group shadow-[0_0_28px_rgba(255,140,36,0.18)]">
          <div>
            <div class="flex items-center justify-between mb-3">
              <span class="text-[10px] font-extrabold uppercase tracking-wider px-2.5 py-0.5 rounded-md bg-amber-950 text-vice-gold border border-vice-orange/60">Heavy PvP</span>
              <span class="text-[10px] font-bold text-vice-cyan flex items-center gap-1"><i class="fa-solid fa-shield-check"></i> 3d Insured</span>
            </div>
            <div class="w-16 h-16 mx-auto my-3 rounded-2xl bg-amber-950/50 border border-vice-orange/60 flex items-center justify-center p-2.5 group-hover:scale-110 transition-transform shadow-inner">
              <svg viewBox="0 0 64 64" class="w-full h-full">
                <polygon points="18,16 46,16 54,32 46,48 18,48 10,32" fill="#44403C" stroke="#1C1917" stroke-width="2.5" stroke-linejoin="round"/>
                <polygon points="22,20 42,20 47,32 42,44 22,44 17,32" fill="#57534E"/>
                <path d="M22 20 L42 20 L38 27 L26 27 Z" fill="#FACC15" opacity="0.9"/>
                <rect x="26" y="30" width="12" height="5" rx="1" fill="#78716C"/>
              </svg>
            </div>
            <h3 class="text-xl font-heading font-black text-vice-gold text-center">Netherite Kit</h3>
            <p class="text-[11px] text-slate-300 text-center mt-1">Maxed Netherite Armor, Knockback-Resist, Totems &amp; Potions</p>

            <div class="mt-4 bg-[#090514]/95 border border-amber-900/60 rounded-xl p-3 space-y-1.5 text-xs">
              <div class="flex justify-between text-slate-400">
                <span>Base Price:</span>
                <span class="font-mono text-slate-200">&#8377;125</span>
              </div>
              <div class="flex justify-between text-vice-cyan">
                <span>10% Insurance GST:</span>
                <span class="font-mono">+&#8377;13</span>
              </div>
              <div class="border-t border-slate-800 pt-1.5 flex justify-between items-baseline">
                <span class="font-bold text-white">Total Payable:</span>
                <span class="font-heading font-black text-lg text-vice-gold">&#8377;138</span>
              </div>
            </div>
          </div>

          <button type="button" onclick="openKitCheckout('Netherite Kit', 125, 13, 138)" class="mc-btn shine-btn mt-4 w-full bg-gradient-to-r from-vice-orange to-vice-gold text-slate-950 font-black py-3 px-4 rounded-xl text-xs uppercase tracking-wider flex items-center justify-center gap-2">
            <i class="fa-solid fa-cart-shopping"></i>
            <span>Buy Netherite Kit</span>
          </button>
        </div>

        <!-- 5. ENDER KIT -->
        <div class="mc-panel rounded-2xl p-5 flex flex-col justify-between transition-all duration-300 hover:-translate-y-1.5 border-vice-pink/85 relative overflow-hidden group shadow-[0_0_32px_rgba(255,42,133,0.28)]">
          <div>
            <div class="flex items-center justify-between mb-3">
              <span class="text-[10px] font-extrabold uppercase tracking-wider px-2.5 py-0.5 rounded-md bg-gradient-to-r from-vice-pink to-vice-purple text-white shadow">Vice God Tier</span>
              <span class="text-[10px] font-bold text-vice-cyan flex items-center gap-1"><i class="fa-solid fa-shield-check"></i> 3d Insured</span>
            </div>
            <div class="w-16 h-16 mx-auto my-3 rounded-2xl bg-pink-950/70 border border-vice-pink/70 flex items-center justify-center p-2.5 group-hover:scale-110 transition-transform shadow-inner">
              <svg viewBox="0 0 64 64" class="w-full h-full">
                <circle cx="32" cy="32" r="22" fill="#3B0764" stroke="#FF2A85" stroke-width="3"/>
                <circle cx="32" cy="32" r="16" fill="#00F0FF"/>
                <ellipse cx="32" cy="32" rx="6" ry="13" fill="#090612"/>
                <circle cx="29" cy="26" r="2.5" fill="#FACC15"/>
              </svg>
            </div>
            <h3 class="text-xl font-heading font-black text-vice-pink text-center">Ender Kit</h3>
            <p class="text-[11px] text-slate-300 text-center mt-1">God-Enchanted Netherite, Elytra, End Crystals, Totems &amp; Pearls</p>

            <div class="mt-4 bg-[#090514]/95 border border-pink-900/70 rounded-xl p-3 space-y-1.5 text-xs">
              <div class="flex justify-between text-slate-400">
                <span>Base Price:</span>
                <span class="font-mono text-slate-200">&#8377;150</span>
              </div>
              <div class="flex justify-between text-vice-cyan">
                <span>10% Insurance GST:</span>
                <span class="font-mono">+&#8377;15</span>
              </div>
              <div class="border-t border-slate-800 pt-1.5 flex justify-between items-baseline">
                <span class="font-bold text-white">Total Payable:</span>
                <span class="font-heading font-black text-lg text-vice-pink">&#8377;165</span>
              </div>
            </div>
          </div>

          <button type="button" onclick="openKitCheckout('Ender Kit', 150, 15, 165)" class="mc-btn shine-btn mt-4 w-full bg-gradient-to-r from-vice-pink via-vice-magenta to-vice-cyan text-slate-950 font-black py-3 px-4 rounded-xl text-xs uppercase tracking-wider flex items-center justify-center gap-2">
            <i class="fa-solid fa-crown"></i>
            <span>Buy Ender Kit</span>
          </button>
        </div>

      </div>
    </section>

    <!-- DIRECT IN-SITE UPI CHECKOUT MODAL -->
    <div id="kit-checkout-modal" class="fixed inset-0 z-50 hidden items-center justify-center p-3 sm:p-4 bg-black/85 backdrop-blur-md overflow-y-auto">
      <div class="relative w-full max-w-lg my-auto mc-panel rounded-3xl border-2 border-vice-pink/85 shadow-[0_0_80px_rgba(255,42,133,0.4)] overflow-hidden">
        
        <button type="button" onclick="closeKitCheckout()" aria-label="Close Checkout" class="absolute top-3.5 right-3.5 z-20 w-9 h-9 rounded-full bg-slate-900/95 hover:bg-vice-pink text-slate-200 hover:text-white border-2 border-slate-600 hover:border-vice-cyan flex items-center justify-center transition-all shadow-lg">
          <i class="fa-solid fa-xmark text-lg"></i>
        </button>

        <div class="bg-gradient-to-r from-[#2D0B42] via-[#130A26] to-[#082438] px-5 sm:px-6 pt-5 pb-4 border-b border-vice-pink/40">
          <div class="text-[10px] font-pixel text-vice-cyan tracking-wider uppercase mb-1">Instant UPI Checkout</div>
          <h3 id="checkout-kit-title" class="font-heading font-black text-2xl text-white tracking-wide">
            Buy Diamond Kit
          </h3>
          <p class="text-xs text-slate-300 mt-0.5">Includes 10% GST for 3-Day Kit Damage Insurance Protection</p>
        </div>

        <div class="p-5 sm:p-6 space-y-4 max-h-[82vh] overflow-y-auto avatar-scroll">
          <div>
            <label for="checkout-ign-input" class="block text-xs font-bold uppercase tracking-wider text-vice-gold mb-1">
              Your Minecraft Username (IGN)
            </label>
            <input type="text" id="checkout-ign-input" oninput="updateCheckoutUpiLinks()" placeholder="Enter your Java or Bedrock IGN..." class="w-full bg-[#090514] border border-vice-pink/40 focus:border-vice-cyan rounded-xl px-3.5 py-2.5 text-xs sm:text-sm text-white placeholder-slate-500 outline-none font-mono">
          </div>

          <div class="bg-[#090514]/95 border border-slate-800 rounded-2xl p-4 space-y-2 text-xs">
            <div class="flex justify-between text-slate-300">
              <span id="checkout-base-label">Kit Base Price:</span>
              <span id="checkout-base-val" class="font-mono font-bold text-white">&#8377;100</span>
            </div>
            <div class="flex justify-between text-vice-cyan">
              <span>10% GST (3-Day Kit Damage Insurance):</span>
              <span id="checkout-gst-val" class="font-mono font-bold">+&#8377;10</span>
            </div>
            <div class="border-t border-slate-800 pt-2 flex justify-between items-center">
              <span class="font-extrabold uppercase tracking-wider text-white">Final Amount to Pay:</span>
              <span id="checkout-total-val" class="font-heading font-black text-2xl text-vice-gold">&#8377;110</span>
            </div>
          </div>

          <div class="bg-[#120A26]/95 border border-vice-cyan/45 rounded-2xl p-4 flex flex-col sm:flex-row items-center gap-4">
            <div class="w-36 h-36 bg-white p-2 rounded-xl shrink-0 shadow-lg flex items-center justify-center">
              <img id="checkout-qr-img" src="" alt="Scan UPI QR Code" class="w-full h-full object-contain">
            </div>
            <div class="flex-1 text-center sm:text-left space-y-2.5 w-full">
              <div class="text-[11px] font-bold uppercase tracking-wider text-vice-cyan">
                Scan QR or Pay via UPI ID
              </div>
              <div class="bg-[#090514] border border-vice-pink/40 rounded-xl px-3 py-2 flex items-center justify-between gap-2">
                <span class="font-mono font-bold text-vice-gold text-xs sm:text-sm truncate">ghostmc.fund@ybl</span>
                <button type="button" onclick="copyToClipboard('ghostmc.fund@ybl', 'Copied UPI ID: ghostmc.fund@ybl')" class="bg-[#1E113D] hover:bg-[#2B1957] text-white px-2.5 py-1 rounded-lg text-xs font-bold shrink-0 transition-colors">
                  <i class="fa-regular fa-copy mr-1"></i> Copy
                </button>
              </div>
              <a id="checkout-upi-deeplink" href="upi://pay?pa=ghostmc.fund@ybl&pn=PineappleSMP&cu=INR" class="mc-btn shine-btn w-full bg-gradient-to-r from-vice-pink via-vice-orange to-vice-gold text-slate-950 font-black py-2.5 px-4 rounded-xl text-xs uppercase tracking-wider flex items-center justify-center gap-2">
                <i class="fa-solid fa-mobile-screen-button"></i>
                <span>Pay Directly via UPI App</span>
              </a>
            </div>
          </div>

          <div class="bg-gradient-to-r from-[#280C42] via-[#120A26] to-[#0A253B] border-2 border-vice-pink/80 rounded-2xl p-4 space-y-2.5">
            <div class="flex items-center gap-2 text-xs font-black uppercase tracking-wider text-vice-gold">
              <i class="fa-solid fa-triangle-exclamation text-vice-pink text-sm"></i>
              <span>Important Claim &amp; Insurance Note</span>
            </div>
            <p class="text-xs text-slate-200 leading-relaxed">
              After completing your UPI payment, <strong class="text-white">take a clear screenshot of the transaction</strong> and <strong class="text-vice-gold">open a support ticket on our Discord Server</strong> to receive your kit and activate your <strong class="text-vice-cyan">3-Day Damage Insurance</strong>!
            </p>
            <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="shine-btn w-full bg-[#5865F2] hover:bg-[#4752c4] text-white font-extrabold py-2.5 px-4 rounded-xl text-xs uppercase tracking-wider flex items-center justify-center gap-2 shadow-lg">
              <i class="fa-brands fa-discord text-base"></i>
              <span>Open Ticket on Discord (discord.gg/Vp9Ss592cq)</span>
            </a>
          </div>
        </div>
      </div>
    </div>

    <!-- Vice City Neon Sunset Divider -->
    <div class="mc-grass-divider my-2"></div>

    <!-- 7. SERVER FUNDERS & SUPPORTERS SHOWCASE -->
    <section id="funders" class="py-14 max-w-5xl mx-auto px-4 sm:px-6 relative">
      <div class="text-center mb-10">
        <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-gradient-to-r from-vice-pink/20 to-vice-gold/20 border border-vice-gold/50 text-vice-gold text-xs font-extrabold uppercase tracking-widest mb-3 shadow-[0_0_20px_rgba(255,42,133,0.22)]">
          <i class="fa-solid fa-crown text-vice-gold"></i> Vice VIP Hall &bull; Official Network Backers
        </div>
        <h2 class="font-gta text-4xl sm:text-6xl text-white tracking-wider">
          SERVER <span class="text-transparent bg-clip-text bg-gradient-to-r from-vice-cyan via-vice-pink to-vice-gold">FUNDERS</span>
        </h2>
        <p class="text-slate-300 text-xs sm:text-sm mt-2 max-w-xl mx-auto leading-relaxed">
          A huge thank you to the generous legends who help keep PineappleSMP running 24/7 with lag-free VitalCloud performance!
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-6 items-stretch">
        <!-- Founding Funder Card: flaxxy444 -->
        <div class="md:col-span-2 mc-panel rounded-3xl p-6 sm:p-8 border-2 border-vice-pink/80 bg-gradient-to-br from-[#2B0C45]/80 via-[#120A26]/95 to-[#082438]/75 shadow-[0_0_50px_rgba(255,42,133,0.26)] relative overflow-hidden flex flex-col sm:flex-row items-center gap-6">
          <div class="relative shrink-0">
            <div class="absolute -inset-2 bg-gradient-to-tr from-vice-pink/35 to-vice-cyan/35 blur-xl rounded-2xl pointer-events-none"></div>
            <div class="relative w-24 h-24 sm:w-28 sm:h-28 rounded-2xl border-2 border-vice-cyan bg-[#090514] p-1.5 shadow-xl flex items-center justify-center overflow-hidden">
              <img src="https://mc-heads.net/avatar/flaxxy444/96" alt="flaxxy444 Minecraft Avatar" class="w-full h-full rounded-xl object-cover" onerror="this.onerror=null; this.src='https://mc-heads.net/avatar/MHF_Steve/96'">
            </div>
            <span class="absolute -top-2.5 -right-2.5 w-8 h-8 rounded-full bg-gradient-to-br from-vice-gold to-vice-pink text-slate-950 flex items-center justify-center shadow-lg border-2 border-[#090514]" title="Founding Funder">
              <i class="fa-solid fa-crown text-xs"></i>
            </span>
          </div>

          <div class="flex-1 text-center sm:text-left space-y-2">
            <div class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-vice-pink/20 border border-vice-pink/50 text-vice-gold text-[10px] font-black uppercase tracking-widest">
              <i class="fa-solid fa-gem text-vice-cyan"></i> Founding Funder #1
            </div>
            <h3 class="font-heading font-black text-2xl sm:text-3xl text-white tracking-wide">
              flaxxy444
            </h3>
            <p class="text-xs sm:text-sm text-slate-200 leading-relaxed">
              Official Founding Funder of <strong class="text-vice-gold">PineappleSMP Season 1</strong>. Recognized across the network for supporting server infrastructure, community events, and player rewards!
            </p>
            <div class="pt-1 flex flex-wrap items-center justify-center sm:justify-start gap-2 text-[11px] font-bold">
              <span class="px-2.5 py-1 rounded-lg bg-vice-cyan/15 border border-vice-cyan/45 text-vice-cyan">
                <i class="fa-solid fa-star mr-1"></i> Season 1 Patron
              </span>
              <span class="px-2.5 py-1 rounded-lg bg-[#090514] border border-vice-pink/40 text-slate-200 font-mono">
                IGN: flaxxy444
              </span>
            </div>
          </div>
        </div>

        <!-- Become a Funder Callout Card -->
        <div class="mc-panel rounded-3xl p-6 border border-vice-cyan/45 flex flex-col justify-between text-center">
          <div class="space-y-3">
            <div class="w-12 h-12 mx-auto rounded-2xl bg-vice-cyan/15 border border-vice-cyan/45 text-vice-cyan flex items-center justify-center text-xl">
              <i class="fa-solid fa-hand-holding-heart"></i>
            </div>
            <h3 class="font-heading font-black text-xl text-white">Become a Funder</h3>
            <p class="text-xs text-slate-300 leading-relaxed">
              Want your name and 3D Minecraft avatar featured in the official <strong class="text-vice-gold">Server Funders</strong> Hall of Honor? Support the SMP via our Kits Store or contact staff on Discord!
            </p>
          </div>
          <div class="mt-5 space-y-2">
            <a href="#kits-store" class="mc-btn shine-btn w-full bg-gradient-to-r from-vice-pink to-vice-orange text-white font-black py-2.5 px-4 rounded-xl text-xs uppercase tracking-wider flex items-center justify-center gap-2">
              <i class="fa-solid fa-shield-halved"></i>
              <span>Browse Battle Kits</span>
            </a>
            <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="w-full bg-[#1B1038] hover:bg-[#27174F] text-slate-200 border border-vice-cyan/40 font-bold py-2.5 px-4 rounded-xl text-xs flex items-center justify-center gap-1.5 transition-colors">
              <i class="fa-brands fa-discord text-vice-cyan"></i>
              <span>Message on Discord</span>
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Vice City Neon Sunset Divider -->
    <div class="mc-grass-divider my-2"></div>

    <!-- 7B. OFFICIAL NETWORK PARTNERSHIPS SECTION (PARTNERSHIP WITH FRIENDS SMP) -->
    <section id="partnerships" class="py-14 max-w-5xl mx-auto px-4 sm:px-6 relative">
      <div class="text-center mb-10">
        <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-gradient-to-r from-vice-cyan/20 to-vice-pink/20 border border-vice-cyan/50 text-vice-cyan text-xs font-extrabold uppercase tracking-widest mb-3 shadow-[0_0_20px_rgba(0,240,255,0.22)]">
          <i class="fa-solid fa-handshake-angle text-vice-pink"></i> Official Network Alliance &bull; Cross-Server Collaboration
        </div>
        <h2 class="font-gta text-4xl sm:text-6xl text-white tracking-wider">
          OFFICIAL <span class="text-transparent bg-clip-text bg-gradient-to-r from-vice-cyan via-vice-pink to-vice-gold">PARTNERSHIPS</span>
        </h2>
        <p class="text-slate-300 text-xs sm:text-sm mt-2 max-w-xl mx-auto leading-relaxed">
          Uniting top Minecraft communities for epic cross-server tournaments, joint giveaways, and shared Lifesteal adventures!
        </p>
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 items-stretch">
        <!-- Featured Partner Card: Partnership with Friends SMP -->
        <div class="lg:col-span-2 mc-panel rounded-3xl p-6 sm:p-8 border-2 border-vice-cyan/80 bg-gradient-to-br from-[#08263C]/85 via-[#120A26]/95 to-[#2B0C45]/80 shadow-[0_0_50px_rgba(0,240,255,0.22)] relative overflow-hidden flex flex-col sm:flex-row items-center gap-6">
          <!-- Custom Alliance Emblem SVG -->
          <div class="relative shrink-0">
            <div class="absolute -inset-2 bg-gradient-to-tr from-vice-cyan/35 to-vice-pink/35 blur-xl rounded-2xl pointer-events-none"></div>
            <div class="relative w-24 h-24 sm:w-28 sm:h-28 rounded-2xl border-2 border-vice-pink bg-[#090514] p-2 shadow-xl flex items-center justify-center overflow-hidden">
              <svg viewBox="0 0 120 120" class="w-full h-full drop-shadow-[0_4px_12px_rgba(0,240,255,0.5)]">
                <defs>
                  <linearGradient id="partnerShieldGrad" x1="0" y1="0" x2="1" y2="1">
                    <stop offset="0%" stop-color="#00F0FF"/>
                    <stop offset="50%" stop-color="#FF2A85"/>
                    <stop offset="100%" stop-color="#FACC15"/>
                  </linearGradient>
                </defs>
                <path d="M60 10 L102 28 V60 C102 86 84 103 60 112 C36 103 18 86 18 60 V28 Z" fill="#130926" stroke="url(#partnerShieldGrad)" stroke-width="5" stroke-linejoin="round"/>
                <!-- Interlocking Friendship Cubes -->
                <rect x="33" y="42" width="26" height="26" rx="5" fill="#00F0FF" opacity="0.9" stroke="#090514" stroke-width="2.5"/>
                <rect x="61" y="42" width="26" height="26" rx="5" fill="#FF2A85" opacity="0.9" stroke="#090514" stroke-width="2.5"/>
                <path d="M48 64 L60 76 L72 64" fill="none" stroke="#FACC15" stroke-width="4.5" stroke-linecap="round" stroke-linejoin="round"/>
                <circle cx="60" cy="30" r="4.5" fill="#FACC15"/>
              </svg>
            </div>
            <span class="absolute -top-2.5 -right-2.5 w-8 h-8 rounded-full bg-gradient-to-br from-vice-cyan to-vice-pink text-slate-950 flex items-center justify-center shadow-lg border-2 border-[#090514]" title="Verified Partner">
              <i class="fa-solid fa-handshake text-xs"></i>
            </span>
          </div>

          <!-- Partner Details -->
          <div class="flex-1 text-center sm:text-left space-y-2.5">
            <div class="inline-flex items-center gap-1.5 px-3 py-1 rounded-full bg-vice-cyan/20 border border-vice-cyan/55 text-vice-cyan text-[10px] font-black uppercase tracking-widest">
              <i class="fa-solid fa-circle-check text-vice-gold"></i> Official Alliance
            </div>
            <h3 class="font-heading font-black text-2xl sm:text-3xl text-white tracking-wide">
              Partnership with <span class="text-transparent bg-clip-text bg-gradient-to-r from-vice-cyan via-white to-vice-pink">Friends SMP</span>
            </h3>
            <p class="text-xs sm:text-sm text-slate-200 leading-relaxed">
              <strong class="text-vice-gold">PineappleSMP</strong> is proudly partnered with <strong class="text-vice-cyan">Friends SMP</strong>! Together we host cross-community PvP events, seasonal giveaways, and friendly survival collaborations across Bedrock &amp; Java.
            </p>
            <div class="pt-1 flex flex-wrap items-center justify-center sm:justify-start gap-2 text-[11px] font-bold">
              <span class="px-2.5 py-1 rounded-lg bg-vice-pink/15 border border-vice-pink/45 text-pink-200">
                <i class="fa-solid fa-trophy text-vice-gold mr-1"></i> Joint Events &amp; Giveaways
              </span>
              <span class="px-2.5 py-1 rounded-lg bg-[#090514] border border-vice-cyan/40 text-vice-cyan font-mono">
                PineappleSMP &times; Friends SMP
              </span>
            </div>
          </div>
        </div>

        <!-- Partner With Us Callout Card -->
        <div class="mc-panel rounded-3xl p-6 border border-vice-pink/45 flex flex-col justify-between text-center">
          <div class="space-y-3">
            <div class="w-12 h-12 mx-auto rounded-2xl bg-vice-pink/15 border border-vice-pink/45 text-vice-pink flex items-center justify-center text-xl">
              <i class="fa-solid fa-network-wired"></i>
            </div>
            <h3 class="font-heading font-black text-xl text-white">Want to Partner?</h3>
            <p class="text-xs text-slate-300 leading-relaxed">
              Own an active Minecraft SMP or gaming community? Apply for an official partnership with <strong class="text-vice-gold">PineappleSMP</strong> by opening a partnership ticket on our Discord server!
            </p>
          </div>
          <div class="mt-5">
            <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="mc-btn shine-btn w-full bg-gradient-to-r from-vice-cyan via-vice-pink to-vice-orange text-slate-950 font-black py-3 px-4 rounded-xl text-xs uppercase tracking-wider flex items-center justify-center gap-2">
              <i class="fa-brands fa-discord text-sm"></i>
              <span>Open Ticket on Discord</span>
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Vice City Neon Sunset Divider -->
    <div class="mc-grass-divider my-2"></div>

    <!-- 8. SERVER FEATURES & GAMEPLAY SECTION -->
    <section id="features" class="py-14 relative">
      <div class="max-w-6xl mx-auto px-4 sm:px-6">
        
        <div class="text-center mb-12">
          <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-vice-pink/15 border border-vice-pink/40 text-vice-gold text-xs font-bold uppercase tracking-widest mb-3">
            <i class="fa-solid fa-star text-vice-pink"></i> Why Play on PineappleSMP
          </div>
          <h2 class="font-gta text-4xl sm:text-6xl text-white tracking-wider">
            SERVER FEATURES &amp; GAMEPLAY
          </h2>
          <p class="text-slate-300 text-sm sm:text-base mt-2 max-w-xl mx-auto">
            Engineered for low latency, smooth PvP combat, active community trading, and intense lifesteal dynamics.
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          
          <!-- Feature 1: Lifesteal Combat -->
          <div class="mc-panel rounded-2xl p-6 transition-all duration-300 hover:-translate-y-1 group">
            <div class="w-12 h-12 rounded-xl bg-vice-pink/15 border border-vice-pink/40 text-vice-pink flex items-center justify-center text-xl mb-4 group-hover:scale-110 transition-transform">
              <i class="fa-solid fa-heart-crack"></i>
            </div>
            <h3 class="text-xl font-heading font-bold text-white mb-2">Lifesteal Combat</h3>
            <p class="text-xs sm:text-sm text-slate-300 leading-relaxed">
              Every kill steals a heart from your target. Eliminate your foes, claim their health, or craft revive beacons to save fallen teammates!
            </p>
          </div>

          <!-- Feature 2: Bedrock + Java Crossplay -->
          <div class="mc-panel rounded-2xl p-6 transition-all duration-300 hover:-translate-y-1 group">
            <div class="w-12 h-12 rounded-xl bg-vice-cyan/15 border border-vice-cyan/40 text-vice-cyan flex items-center justify-center text-xl mb-4 group-hover:scale-110 transition-transform">
              <i class="fa-solid fa-mobile-screen"></i>
            </div>
            <h3 class="text-xl font-heading font-bold text-white mb-2">Crossplay Bedrock + Java</h3>
            <p class="text-xs sm:text-sm text-slate-300 leading-relaxed">
              Play together across Android, iOS, Xbox, PlayStation, Nintendo Switch, and PC with synchronized inventory and combat mechanics.
            </p>
          </div>

          <!-- Feature 3: Hosted on VitalCloud -->
          <div class="mc-panel rounded-2xl p-6 transition-all duration-300 hover:-translate-y-1 group relative overflow-hidden">
            <div class="flex items-center justify-between mb-4">
              <div class="w-12 h-12 rounded-xl bg-vice-gold/15 border border-vice-gold/40 text-vice-gold flex items-center justify-center text-xl group-hover:scale-110 transition-transform">
                <i class="fa-solid fa-server text-vice-cyan"></i>
              </div>
              <span class="text-[10px] font-extrabold uppercase tracking-wider px-2.5 py-1 rounded-full bg-vice-cyan/15 border border-vice-cyan/40 text-vice-cyan">
                24/7 Low Ping
              </span>
            </div>
            <h3 class="text-xl font-heading font-bold text-white mb-2">Hosted on VitalCloud</h3>
            <p class="text-xs sm:text-sm text-slate-300 leading-relaxed">
              Powered by <strong class="text-vice-gold">VitalCloud Hosting</strong> for ultra-low ping across India &amp; global nodes, 24/7 uninterrupted uptime, enterprise DDoS protection, and smooth lag-free PvP &amp; survival gameplay.
            </p>
          </div>

        </div>

        <!-- Discord Community Callout Box -->
        <div class="mt-10 bg-gradient-to-r from-[#2D0A45]/85 via-[#130A29] to-[#08263C]/85 border-2 border-vice-pink/55 rounded-3xl p-8 sm:p-10 shadow-[0_0_45px_rgba(255,42,133,0.2)] text-center relative overflow-hidden">
          <div class="inline-flex p-3 rounded-2xl bg-vice-cyan/15 text-vice-cyan border border-vice-cyan/40 mb-3 text-3xl">
            <i class="fa-brands fa-discord"></i>
          </div>
          <h3 class="font-gta text-3xl sm:text-5xl text-white tracking-wider">JOIN OUR OFFICIAL DISCORD</h3>
          <p class="text-slate-200 text-sm sm:text-base mt-2 max-w-xl mx-auto">
            Participate in community giveaways, team up with SMP clans, claim purchased kits via ticket, and chat directly with staff!
          </p>
          <div class="mt-6 flex flex-wrap justify-center gap-4">
            <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="mc-btn shine-btn inline-flex items-center gap-2.5 bg-gradient-to-r from-vice-pink via-vice-magenta to-vice-cyan text-slate-950 font-black px-8 py-4 rounded-xl text-sm sm:text-base transition-all">
              <i class="fa-brands fa-discord text-xl"></i>
              <span>Join PineappleSMP Discord (discord.gg/Vp9Ss592cq) &rarr;</span>
            </a>
          </div>
        </div>

      </div>
    </section>

    <!-- Vice City Neon Sunset Divider -->
    <div class="mc-grass-divider my-2"></div>

    <!-- 9. PINEAPPLEBOT AI SUPPORT ASSISTANT (DIRECTLY ABOVE FOUNDER CARD & WATERMARK) -->
    <section id="ai-support" class="py-14 max-w-5xl mx-auto px-4 sm:px-6">
      <div class="text-center mb-8">
        <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-vice-pink/15 border border-vice-pink/45 text-vice-gold text-xs font-bold uppercase tracking-widest mb-3">
          <i class="fa-solid fa-robot text-vice-cyan"></i> 24/7 Smart Companion &amp; Error Helper
        </div>
        <h2 class="font-gta text-4xl sm:text-5xl text-white tracking-wider">
          PINEAPPLE SMP <span class="text-transparent bg-clip-text bg-gradient-to-r from-vice-cyan via-vice-pink to-vice-gold">AI SUPPORT</span>
        </h2>
        <p class="text-slate-300 text-xs sm:text-sm mt-2 max-w-xl mx-auto">
          Chat naturally, ask about server IPs, Battle Kits &amp; 3-Day Insurance, or paste any Minecraft error for a fresh, tailored answer every time!
        </p>
      </div>

      <!-- Vice Neon AI Console Panel -->
      <div class="mc-panel rounded-3xl border-2 border-vice-pink/65 overflow-hidden shadow-[0_0_50px_rgba(255,42,133,0.22)]">
        
        <!-- AI Top Control Header & 3-Language Switcher -->
        <div class="bg-gradient-to-r from-[#2B0C45] via-[#120A26] to-[#082438] px-4 sm:px-6 py-4 border-b border-vice-pink/35 flex flex-col sm:flex-row sm:items-center justify-between gap-3">
          <div class="flex items-center gap-3">
            <div class="w-10 h-10 rounded-xl bg-gradient-to-br from-vice-pink/35 to-vice-cyan/35 border border-vice-cyan/60 flex items-center justify-center text-vice-cyan text-lg shadow-inner shrink-0">
              <i class="fa-solid fa-microchip"></i>
            </div>
            <div>
              <div class="flex items-center gap-2">
                <h3 class="font-heading font-black text-base sm:text-lg text-white tracking-wide">PineappleBot AI</h3>
                <span class="inline-flex items-center gap-1 text-[10px] font-bold uppercase px-2 py-0.5 rounded-full bg-vice-cyan/20 text-vice-cyan border border-vice-cyan/45">
                  <span class="w-1.5 h-1.5 rounded-full bg-vice-cyan animate-ping"></span> Online &bull; Dynamic Replies
                </span>
              </div>
              <p class="text-[11px] text-slate-300">Choose your preferred response language below</p>
            </div>
          </div>

          <!-- 3-Language Switcher (English, Hindi, Hinglish) -->
          <div class="flex items-center gap-1.5 bg-[#090514]/95 p-1.5 rounded-xl border border-vice-pink/35 self-start sm:self-auto" role="group" aria-label="AI Response Language">
            <span class="text-[10px] font-bold uppercase text-slate-400 px-2 hidden md:inline">Language:</span>
            <button type="button" id="lang-btn-English" onclick="setAiLanguage('English')" class="px-3 py-1.5 rounded-lg text-xs font-extrabold transition-all bg-gradient-to-r from-vice-pink to-vice-orange text-white shadow">
              English
            </button>
            <button type="button" id="lang-btn-Hindi" onclick="setAiLanguage('Hindi')" class="px-3 py-1.5 rounded-lg text-xs font-extrabold transition-all text-slate-300 hover:text-white hover:bg-[#1B1038]">
              Hindi
            </button>
            <button type="button" id="lang-btn-Hinglish" onclick="setAiLanguage('Hinglish')" class="px-3 py-1.5 rounded-lg text-xs font-extrabold transition-all text-slate-300 hover:text-white hover:bg-[#1B1038]">
              Hinglish
            </button>
          </div>
        </div>

        <!-- Quick Error & Topic Prompt Chips -->
        <div class="bg-[#0B061A]/85 px-4 sm:px-6 py-3 border-b border-vice-pink/25 flex items-center gap-2 overflow-x-auto">
          <span class="text-[10px] font-bold uppercase tracking-wider text-vice-gold shrink-0">Quick Help:</span>
          <button type="button" onclick="sendQuickAiPrompt('Unable to connect to world error fix')" class="shrink-0 text-xs font-semibold bg-[#160D2E] hover:bg-[#221445] text-slate-200 border border-slate-700 hover:border-vice-pink/70 px-3 py-1.5 rounded-lg transition-all">
            Unable to connect to world
          </button>
          <button type="button" onclick="sendQuickAiPrompt('How do Battle Kits and the 10% 3-Day Damage Insurance work?')" class="shrink-0 text-xs font-semibold bg-[#160D2E] hover:bg-[#221445] text-vice-cyan border border-vice-cyan/40 hover:border-vice-cyan px-3 py-1.5 rounded-lg transition-all">
            Kits &amp; 3-Day Insurance
          </button>
          <button type="button" onclick="sendQuickAiPrompt('Outdated Client or Outdated Server error fix')" class="shrink-0 text-xs font-semibold bg-[#160D2E] hover:bg-[#221445] text-slate-200 border border-slate-700 hover:border-vice-pink/70 px-3 py-1.5 rounded-lg transition-all">
            Outdated Client / Server
          </button>
          <button type="button" onclick="sendQuickAiPrompt('What is the Bedrock Edition IP and Port?')" class="shrink-0 text-xs font-semibold bg-[#160D2E] hover:bg-[#221445] text-slate-200 border border-slate-700 hover:border-vice-pink/70 px-3 py-1.5 rounded-lg transition-all">
            Bedrock IP &amp; Port
          </button>
          <button type="button" onclick="sendQuickAiPrompt('Hey PineappleBot! How are you doing today?')" class="shrink-0 text-xs font-semibold bg-[#160D2E] hover:bg-[#221445] text-vice-gold border border-vice-gold/40 hover:border-vice-gold px-3 py-1.5 rounded-lg transition-all">
            Say Hello
          </button>
        </div>

        <!-- AI Chat Messages Feed -->
        <div id="ai-chat-messages" class="p-4 sm:p-6 space-y-4 max-h-[440px] overflow-y-auto avatar-scroll scroll-smooth bg-gradient-to-b from-[#090514]/80 to-[#0E0820]/95">
          <!-- Initial Welcome Message -->
          <div class="flex items-start gap-3 chat-msg-enter">
            <div class="w-9 h-9 rounded-xl bg-gradient-to-br from-vice-pink to-vice-cyan text-slate-950 font-black flex items-center justify-center shrink-0 shadow-md">
              <i class="fa-solid fa-robot"></i>
            </div>
            <div class="flex-1 bg-[#140C2B]/95 border border-vice-pink/40 rounded-2xl rounded-tl-none p-4 text-xs sm:text-sm text-slate-200 leading-relaxed shadow-md">
              <div class="font-bold text-vice-gold mb-1">Welcome to PineappleSMP AI Support!</div>
              <p>
                Talk to me casually or ask anything about <strong>PineappleSMP Season 1</strong>, <strong>Battle Kits &amp; 3-Day Damage Insurance</strong>, Bedrock &amp; Java connection details, or paste any Minecraft error message! Every message gets a <strong>fresh, unique response</strong> every time.
              </p>
              <div class="mt-3 pt-2.5 border-t border-slate-800 flex flex-wrap items-center justify-between gap-2 text-[11px] text-slate-400">
                <span>Still stuck after trying troubleshooting steps?</span>
                <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-1.5 bg-[#5865F2] hover:bg-[#4752c4] text-white font-bold px-3 py-1.5 rounded-lg transition-colors">
                  <i class="fa-brands fa-discord"></i>
                  <span>Open Support Ticket on Discord</span>
                </a>
              </div>
            </div>
          </div>
        </div>

        <!-- AI Input Bar & Direct Discord Ticket Escalation Footer -->
        <div class="p-4 sm:px-6 bg-[#090514]/95 border-t border-vice-pink/30 space-y-3">
          <form id="ai-chat-form" onsubmit="handleAiChatSubmit(event)" class="flex items-center gap-2.5">
            <div class="relative flex-1">
              <span class="absolute inset-y-0 left-0 pl-3.5 flex items-center text-vice-cyan">
                <i class="fa-solid fa-terminal text-xs"></i>
              </span>
              <input type="text" id="ai-user-input" required maxlength="500" placeholder="Chat normally or paste any Minecraft error (e.g., Unable to connect to world)..." class="w-full bg-[#130A29] border border-vice-pink/40 focus:border-vice-cyan rounded-xl pl-10 pr-4 py-3 text-xs sm:text-sm text-white placeholder-slate-500 outline-none transition-colors">
            </div>
            <button type="submit" id="ai-send-btn" class="mc-btn shine-btn bg-gradient-to-r from-vice-pink via-vice-orange to-vice-cyan text-slate-950 font-black px-5 py-3 rounded-xl text-xs sm:text-sm uppercase tracking-wider flex items-center gap-2 shrink-0">
              <span>Send</span>
              <i class="fa-solid fa-paper-plane"></i>
            </button>
          </form>

          <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-2 text-[11px] text-slate-400 px-1">
            <span>
              <i class="fa-solid fa-circle-info text-vice-gold mr-1"></i>
              If your issue is not solved by AI troubleshooting, create a support ticket on our Discord server.
            </span>
            <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-1.5 text-vice-cyan hover:text-white font-bold transition-colors shrink-0">
              <i class="fa-brands fa-discord text-vice-pink"></i>
              <span>Create Ticket on Discord &rarr;</span>
            </a>
          </div>
        </div>

      </div>
    </section>

    <!-- Vice City Neon Sunset Divider -->
    <div class="mc-grass-divider my-2"></div>

    <!-- 10. LIVE FOUNDER DISCORD PROFILE SHOWCASE (DIRECTLY ABOVE FOOTER & POWERED BY DEVESH WATERMARK) -->
    <section id="founder-discord" class="py-12 max-w-4xl mx-auto px-4 sm:px-6 relative">
      <div class="text-center mb-6">
        <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-vice-pink/15 border border-vice-pink/50 text-vice-cyan text-xs font-extrabold uppercase tracking-widest mb-2">
          <i class="fa-brands fa-discord text-vice-pink"></i> Developer &amp; Network Founder &bull; Live Discord Sync
        </div>
        <h2 class="font-gta text-3xl sm:text-5xl text-white tracking-wider">
          CONNECT WITH <span class="text-transparent bg-clip-text bg-gradient-to-r from-vice-cyan via-vice-pink to-vice-gold">DEVESH</span>
        </h2>
      </div>

      <!-- Vice City Neon Discord Profile Card -->
      <div class="mc-panel rounded-3xl border-2 border-vice-pink/75 overflow-hidden shadow-[0_0_55px_rgba(255,42,133,0.28)] relative">
        
        <!-- Top Discord Profile Banner -->
        <div id="discord-card-banner" class="h-24 sm:h-28 w-full bg-gradient-to-r from-vice-pink via-vice-purple to-vice-cyan relative overflow-hidden">
          <div class="absolute inset-0 bg-grid-pattern opacity-35"></div>
          <div class="absolute top-3 right-3 flex items-center gap-2">
            <span id="discord-live-sync-badge" class="inline-flex items-center gap-1.5 px-2.5 py-1 rounded-full bg-[#090514]/85 backdrop-blur-md border border-vice-cyan/55 text-vice-cyan text-[10px] font-extrabold uppercase tracking-wider shadow">
              <span class="w-1.5 h-1.5 rounded-full bg-vice-cyan animate-ping"></span>
              <span id="discord-sync-label">Live Sync (15s)</span>
            </span>
            <button type="button" onclick="syncFounderDiscordProfile(true)" title="Refresh Discord Profile Now" class="w-8 h-8 rounded-full bg-[#090514]/85 hover:bg-[#160D2E] text-slate-200 hover:text-vice-gold border border-vice-pink/40 flex items-center justify-center transition-all active:scale-90">
              <i id="discord-sync-icon" class="fa-solid fa-arrows-rotate text-xs"></i>
            </button>
            <button type="button" onclick="toggleDiscordConfigDrawer()" title="Configure Live Discord User ID / Bio Sync" class="w-8 h-8 rounded-full bg-[#090514]/85 hover:bg-[#160D2E] text-slate-200 hover:text-vice-gold border border-vice-pink/40 flex items-center justify-center transition-all active:scale-90">
              <i class="fa-solid fa-gear text-xs"></i>
            </button>
          </div>
        </div>

        <!-- Profile Avatar, Status Ring, Display Name, Username & Bio -->
        <div class="px-5 sm:px-8 pb-6 pt-0 relative">
          <div class="flex flex-col sm:flex-row sm:items-end justify-between gap-4 -mt-12 sm:-mt-14 mb-4">
            
            <!-- Live Discord PFP & Status Indicator -->
            <div class="flex items-end gap-4">
              <div class="relative w-24 h-24 sm:w-28 sm:h-28 rounded-full p-1 bg-[#090514] border-4 border-[#090514] shadow-2xl shrink-0">
                <img id="discord-founder-pfp" src="https://cdn.discordapp.com/embed/avatars/0.png" alt="Devesh Discord PFP" referrerpolicy="no-referrer" class="w-full h-full rounded-full object-cover bg-slate-900">
                <img id="discord-founder-decoration" src="" alt="" class="hidden absolute -inset-2 w-[calc(100%+16px)] h-[calc(100%+16px)] pointer-events-none object-contain">
                <!-- Live Presence Status Dot -->
                <span id="discord-founder-status-dot" title="Discord Status" class="absolute bottom-1 right-1 w-6 h-6 rounded-full bg-emerald-500 border-4 border-[#090514] shadow-md"></span>
              </div>

              <div class="pb-1">
                <div class="flex flex-wrap items-center gap-2">
                  <h3 id="discord-founder-displayname" class="font-heading font-black text-2xl sm:text-3xl text-white tracking-tight leading-none">
                    Devesh
                  </h3>
                  <span class="inline-flex items-center gap-1 px-2 py-0.5 rounded-md bg-vice-pink/25 border border-vice-pink/60 text-pink-200 text-[10px] font-black uppercase tracking-wider">
                    <i class="fa-solid fa-code text-vice-cyan"></i> Founder &amp; Dev
                  </span>
                </div>
                <div class="flex items-center gap-2 mt-1.5">
                  <span id="discord-founder-username" class="font-mono font-bold text-sm text-vice-gold select-all">devesh_37.</span>
                  <button type="button" onclick="copyToClipboard('devesh_37.', 'Copied Discord Username: devesh_37.')" class="text-xs text-slate-300 hover:text-white bg-[#160D2E]/95 hover:bg-[#221445] px-2 py-0.5 rounded border border-vice-cyan/40 transition-colors" title="Copy Discord Username">
                    <i class="fa-regular fa-copy mr-1"></i>Copy
                  </button>
                </div>
              </div>
            </div>

            <!-- Action Buttons -->
            <div class="flex flex-wrap items-center gap-2.5">
              <button type="button" onclick="copyToClipboard('devesh_37.', 'Copied Discord Username: devesh_37.')" class="mc-btn bg-[#180E33] hover:bg-[#24154B] text-vice-gold border border-vice-gold/50 font-extrabold px-4 py-2.5 rounded-xl text-xs flex items-center gap-2">
                <i class="fa-solid fa-user-plus text-vice-cyan"></i>
                <span>Add Friend: devesh_37.</span>
              </button>
              <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="mc-btn shine-btn bg-gradient-to-r from-vice-pink to-vice-purple text-white font-extrabold px-4 py-2.5 rounded-xl text-xs flex items-center gap-2">
                <i class="fa-brands fa-discord text-sm"></i>
                <span>Join Server</span>
              </a>
            </div>
          </div>

          <!-- Custom Status / Live Activity Pill -->
          <div id="discord-activity-bar" class="mb-3 px-3.5 py-2 rounded-xl bg-[#090514]/90 border border-vice-pink/30 flex items-center gap-2.5 text-xs text-slate-200">
            <span id="discord-status-text-pill" class="font-bold text-emerald-400 uppercase tracking-wider text-[10px] px-2 py-0.5 rounded bg-emerald-500/15 border border-emerald-500/30">Online</span>
            <span id="discord-custom-status" class="truncate text-slate-200">Building &amp; managing PineappleSMP Season 1</span>
          </div>

          <!-- Live Discord Bio Box -->
          <div class="bg-[#090514]/95 border border-vice-cyan/30 rounded-2xl p-4 space-y-1.5">
            <div class="flex items-center justify-between text-[10px] font-extrabold uppercase tracking-widest text-vice-cyan">
              <span>About Me (Discord Bio)</span>
              <span id="discord-last-synced-time" class="font-mono text-slate-400">Synced</span>
            </div>
            <p id="discord-founder-bio" class="text-xs sm:text-sm text-slate-200 leading-relaxed whitespace-pre-line">
              PineappleSMP Founder &amp; Developer | Bedrock &amp; Java Crossplay Lifesteal Network | DM or open a ticket on Discord!
            </p>
          </div>

          <!-- Collapsible Live Sync Configuration Drawer -->
          <div id="discord-config-drawer" class="hidden mt-4 bg-[#120A26]/95 border border-vice-pink/55 rounded-2xl p-4 space-y-3 text-xs">
            <div class="flex items-center justify-between">
              <div class="font-heading font-bold text-vice-gold flex items-center gap-2">
                <i class="fa-solid fa-satellite-dish text-vice-cyan"></i>
                <span>Real-Time Discord Profile Sync Settings (<span class="font-mono text-white">devesh_37.</span>)</span>
              </div>
              <button type="button" onclick="toggleDiscordConfigDrawer()" class="text-slate-400 hover:text-white">
                <i class="fa-solid fa-xmark"></i>
              </button>
            </div>
            <p class="text-[11px] text-slate-300 leading-relaxed">
              Enter your 18-digit <strong>Discord User ID</strong> below (join <a href="https://discord.gg/lanyard" target="_blank" rel="noopener noreferrer" class="underline text-vice-cyan">discord.gg/lanyard</a> once for instant live PFP, status &amp; activity streaming) or update your live Bio override anytime:
            </p>
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
              <div>
                <label for="discord-snowflake-input" class="block text-[10px] font-bold uppercase tracking-wider text-slate-400 mb-1">Discord Numeric User ID (Optional)</label>
                <input type="text" id="discord-snowflake-input" placeholder="e.g. 112233445566778899" class="w-full bg-[#090514] border border-slate-700 focus:border-vice-cyan rounded-xl px-3 py-2 text-xs text-white font-mono outline-none">
              </div>
              <div>
                <label for="discord-bio-override-input" class="block text-[10px] font-bold uppercase tracking-wider text-slate-400 mb-1">Custom Bio / Tagline Sync</label>
                <input type="text" id="discord-bio-override-input" placeholder="Update live bio text..." class="w-full bg-[#090514] border border-slate-700 focus:border-vice-cyan rounded-xl px-3 py-2 text-xs text-white outline-none">
              </div>
            </div>
            <div class="flex justify-end gap-2">
              <button type="button" onclick="saveFounderDiscordSettings()" class="mc-btn bg-gradient-to-r from-vice-pink to-vice-cyan text-slate-950 font-black px-4 py-2 rounded-xl text-xs uppercase tracking-wider">
                Save &amp; Sync Live Now
              </button>
            </div>
          </div>

        </div>
      </div>
    </section>

  </main>

  <!-- 11. VICE NEON FOOTER WITH POWERED BY DEVESH WATERMARK & DISCORD LINK -->
  <footer class="border-t border-vice-pink/40 bg-[#06030D] py-10 text-slate-400 text-xs relative z-10">
    <div class="max-w-7xl mx-auto px-4 flex flex-col md:flex-row items-center justify-between gap-4">
      <div class="flex items-center gap-3">
        <div class="w-11 h-11 rounded-xl border border-vice-cyan/60 bg-gradient-to-br from-[#2B0B3F] to-[#082436] flex items-center justify-center p-1 shadow-[0_0_16px_rgba(255,42,133,0.35)]">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 300" class="w-full h-full">
            <defs>
              <linearGradient id="ftrViceTop" x1="0" y1="0" x2="1" y2="1">
                <stop offset="0%" stop-color="#FEF08A"/>
                <stop offset="100%" stop-color="#FF8C24"/>
              </linearGradient>
              <linearGradient id="ftrViceFront" x1="0" y1="0" x2="0" y2="1">
                <stop offset="0%" stop-color="#FF7A2F"/>
                <stop offset="100%" stop-color="#FF2A85"/>
              </linearGradient>
              <linearGradient id="ftrViceSide" x1="0" y1="0" x2="1" y2="1">
                <stop offset="0%" stop-color="#D946EF"/>
                <stop offset="100%" stop-color="#6D28D9"/>
              </linearGradient>
              <linearGradient id="ftrViceLeaf" x1="0" y1="1" x2="0" y2="0">
                <stop offset="0%" stop-color="#0891B2"/>
                <stop offset="60%" stop-color="#00F0FF"/>
                <stop offset="100%" stop-color="#A5F3FC"/>
              </linearGradient>
            </defs>
            <path d="M160 66 C152 30, 145 10, 160 4 C175 10, 168 30, 160 66 Z" fill="url(#ftrViceLeaf)" stroke="#1E1B4B" stroke-width="4"/>
            <path d="M152 68 C130 38, 108 26, 102 38 C114 58, 134 68, 152 74 Z" fill="url(#ftrViceLeaf)" stroke="#1E1B4B" stroke-width="4"/>
            <path d="M168 68 C190 38, 212 26, 218 38 C206 58, 186 68, 168 74 Z" fill="url(#ftrViceLeaf)" stroke="#1E1B4B" stroke-width="4"/>
            <polygon points="160,64 226,88 160,112 94,88" fill="url(#ftrViceTop)" stroke="#1E1B4B" stroke-width="5" stroke-linejoin="round"/>
            <polygon points="94,88 160,112 160,188 94,162" fill="url(#ftrViceSide)" stroke="#1E1B4B" stroke-width="5" stroke-linejoin="round"/>
            <polygon points="160,112 226,88 226,162 160,188" fill="url(#ftrViceFront)" stroke="#1E1B4B" stroke-width="5" stroke-linejoin="round"/>
            <rect x="46" y="176" width="228" height="54" rx="12" fill="#1E0B36" stroke="#00F0FF" stroke-width="4"/>
            <text x="160" y="213" font-family="'Outfit', sans-serif" font-weight="900" font-size="34" text-anchor="middle" fill="#FACC15" letter-spacing="1.5">PINEAPPLE</text>
            <rect x="96" y="232" width="128" height="44" rx="8" fill="#FF2A85" stroke="#1E0B36" stroke-width="5"/>
            <text x="160" y="263" font-family="'Outfit', sans-serif" font-weight="900" font-size="28" text-anchor="middle" fill="#FFFFFF" letter-spacing="3">SMP</text>
          </svg>
        </div>
        <div class="flex flex-col text-left">
          <span class="font-gta text-xl text-white tracking-wider">PINEAPPLE SMP</span>
          <button onclick="copyToClipboard('basic.vitalcloud.in:19126', 'Copied IP: basic.vitalcloud.in:19126')" class="text-[10px] text-vice-gold hover:text-vice-cyan font-mono text-left transition-colors">
            Java: basic.vitalcloud.in:19126 | Bedrock: 19149
          </button>
        </div>
      </div>
      <div>
        Official Community Hub &copy; 2026 PineappleSMP. Not an official Minecraft product. Not approved by or associated with Mojang or Microsoft.
      </div>
      <div class="flex items-center gap-4 text-base">
        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="text-vice-cyan hover:text-vice-pink transition-colors" title="Discord">
          <i class="fa-brands fa-discord text-lg"></i>
        </a>
      </div>
    </div>

    <!-- Powered by Devesh Watermark -->
    <div class="mt-8 pt-6 border-t border-vice-pink/20 text-center flex flex-col sm:flex-row items-center justify-center gap-2">
      <div class="inline-flex items-center gap-2 px-5 py-1.5 rounded-full bg-gradient-to-r from-[#2B0C45] via-[#120A26] to-[#082438] border border-vice-pink/60 shadow-[0_0_25px_rgba(255,42,133,0.3)]">
        <i class="fa-solid fa-bolt text-vice-cyan text-xs animate-pulse"></i>
        <span class="text-xs uppercase tracking-widest font-semibold text-slate-200">
          POWERED BY <strong class="text-transparent bg-clip-text bg-gradient-to-r from-vice-cyan via-vice-pink to-vice-gold font-extrabold tracking-wider text-sm">DEVESH</strong>
        </span>
        <i class="fa-solid fa-bolt text-vice-pink text-xs"></i>
      </div>
    </div>
  </footer>

  <!-- Clean Self-Contained Application Logic (No Login / Auth System) -->
  <script>
    // Server Telemetry Configuration
    const SERVER_IP = "basic.vitalcloud.in";
    const JAVA_PORT = 19126;
    const BEDROCK_PORT = 19149;
    const JAVA_FULL_ADDRESS = `${SERVER_IP}:${JAVA_PORT}`;
    const BEDROCK_FULL_ADDRESS = `${SERVER_IP}:${BEDROCK_PORT}`;

    // =========================================================================
    // TOAST NOTIFICATION & CLIPBOARD HELPER
    // =========================================================================
    let toastTimer = null;
    function showToast(message) {
      const toast = document.getElementById('toast');
      const toastText = document.getElementById('toast-text');
      if (!toast || !toastText) return;
      toastText.textContent = message;
      toast.classList.remove('translate-y-24', 'opacity-0');
      toast.classList.add('translate-y-0', 'opacity-100');
      clearTimeout(toastTimer);
      toastTimer = setTimeout(() => {
        toast.classList.add('translate-y-24', 'opacity-0');
        toast.classList.remove('translate-y-0', 'opacity-100');
      }, 2800);
    }

    function copyToClipboard(text, successMsg) {
      const tempInput = document.createElement('textarea');
      tempInput.value = text;
      tempInput.style.position = 'fixed';
      tempInput.style.opacity = '0';
      document.body.appendChild(tempInput);
      tempInput.select();
      try {
        document.execCommand('copy');
        showToast(successMsg || `Copied: ${text}`);
      } catch (err) {
        showToast(`Copy: ${text}`);
      }
      document.body.removeChild(tempInput);
    }

    // =========================================================================
    // 5-SECOND AUTO-SYNC LIVE SERVER TELEMETRY (JAVA + BEDROCK)
    // =========================================================================
    async function fetchLiveServerStatus(manual = false) {
      const refreshIcon = document.getElementById('refresh-icon');
      if (manual && refreshIcon) refreshIcon.classList.add('fa-spin');

      const statusBadge = document.getElementById('server-status-badge');
      const statusDot = document.getElementById('server-status-dot');
      const statusText = document.getElementById('server-status-text');
      const pingBadge = document.getElementById('ping-latency-badge');
      const playersOnlineEl = document.getElementById('server-players-online');
      const playersMaxEl = document.getElementById('server-players-max');
      const playersStatusEl = document.getElementById('server-players-status');
      const playersPulseDot = document.getElementById('players-pulse-dot');
      const rosterListEl = document.getElementById('card-players-list');
      const lastUpdatedEl = document.getElementById('last-updated-text');
      const navDot = document.getElementById('nav-status-dot');

      try {
        const [javaRes, bedrockRes] = await Promise.allSettled([
          fetch(`https://api.mcstatus.io/v2/status/java/${JAVA_FULL_ADDRESS}`),
          fetch(`https://api.mcstatus.io/v2/status/bedrock/${BEDROCK_FULL_ADDRESS}`)
        ]);

        let javaData = null;
        let bedrockData = null;

        if (javaRes.status === 'fulfilled' && javaRes.value.ok) {
          javaData = await javaRes.value.json();
        }
        if (bedrockRes.status === 'fulfilled' && bedrockRes.value.ok) {
          bedrockData = await bedrockRes.value.json();
        }

        const isOnline = Boolean((javaData && javaData.online) || (bedrockData && bedrockData.online));

        if (isOnline) {
          const onlineCount = Math.max(
            javaData?.players?.online || 0,
            bedrockData?.players?.online || 0
          );
          const maxCount = Math.max(
            javaData?.players?.max || 0,
            bedrockData?.players?.max || 0,
            50
          );

          if (statusBadge) statusBadge.className = 'font-bold flex items-center gap-2 text-base mt-1.5 text-emerald-400';
          if (statusDot) statusDot.className = 'w-2.5 h-2.5 rounded-full bg-emerald-400 shadow-[0_0_10px_#10b981] animate-pulse';
          if (statusText) statusText.textContent = 'ONLINE';
          if (pingBadge) {
            pingBadge.textContent = 'ACTIVE';
            pingBadge.className = 'text-[10px] bg-emerald-500/20 border border-emerald-500/40 px-2 py-0.5 rounded text-emerald-300 font-mono font-bold';
          }
          if (navDot) navDot.className = 'w-2 h-2 rounded-full bg-emerald-400 animate-pulse';

          if (playersOnlineEl) playersOnlineEl.textContent = onlineCount;
          if (playersMaxEl) playersMaxEl.textContent = `/ ${maxCount}`;
          if (playersPulseDot) playersPulseDot.className = 'w-1.5 h-1.5 rounded-full bg-emerald-400 animate-ping';
          if (playersStatusEl) {
            playersStatusEl.textContent = onlineCount === 1
              ? '1 warrior online now'
              : `${onlineCount} warriors online now`;
            playersStatusEl.className = 'text-[10px] text-emerald-300 font-medium mt-0.5 flex items-center gap-1';
          }

          // Collect unique player names from Java sample list
          const samplePlayers = Array.isArray(javaData?.players?.list) ? javaData.players.list : [];
          if (rosterListEl) {
            if (samplePlayers.length > 0) {
              rosterListEl.innerHTML = samplePlayers.map(p => {
                const rawName = (p.name_clean || p.name_raw || p.name || 'Player').replace(/§[0-9a-fk-or]/gi, '');
                const safeName = escapeHtml(rawName);
                return `
                  <span class="inline-flex items-center gap-1.5 bg-slate-900 border border-emerald-500/40 px-2 py-0.5 rounded-md text-[10px] font-mono text-white shadow-sm">
                    <img src="https://mc-heads.net/avatar/${encodeURIComponent(rawName)}/16" alt="${safeName}" class="w-3.5 h-3.5 rounded-sm" onerror="this.style.display='none'">
                    <span>${safeName}</span>
                  </span>
                `;
              }).join('');
            } else if (onlineCount > 0) {
              rosterListEl.innerHTML = `<span class="text-[11px] text-emerald-300 font-semibold">${onlineCount} player(s) connected via Crossplay</span>`;
            } else {
              rosterListEl.innerHTML = `<span class="text-[11px] text-slate-400 italic">0 players online — arena open!</span>`;
            }
          }
        } else {
          if (statusBadge) statusBadge.className = 'font-bold flex items-center gap-2 text-base mt-1.5 text-amber-400';
          if (statusDot) statusDot.className = 'w-2.5 h-2.5 rounded-full bg-amber-400 shadow-[0_0_10px_#f59e0b] animate-pulse';
          if (statusText) statusText.textContent = 'SEASON 1 READY';
          if (pingBadge) {
            pingBadge.textContent = 'STANDBY';
            pingBadge.className = 'text-[10px] bg-amber-500/20 border border-amber-500/40 px-2 py-0.5 rounded text-amber-300 font-mono';
          }
          if (playersOnlineEl) playersOnlineEl.textContent = '0';
          if (playersMaxEl) playersMaxEl.textContent = '/ 50';
          if (playersStatusEl) playersStatusEl.textContent = 'Waiting for warriors...';
          if (rosterListEl) {
            rosterListEl.innerHTML = `<span class="text-[11px] text-slate-400 italic">No active players right now</span>`;
          }
        }
      } catch (err) {
        if (statusText) statusText.textContent = 'SEASON 1 READY';
      } finally {
        if (lastUpdatedEl) {
          const now = new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit', second: '2-digit' });
          lastUpdatedEl.textContent = `(Synced ${now})`;
        }
        if (manual && refreshIcon) {
          setTimeout(() => refreshIcon.classList.remove('fa-spin'), 450);
        }
      }
    }

    // =========================================================================
    // BATTLE KITS & 10% GST 3-DAY DAMAGE INSURANCE UPI CHECKOUT MODAL
    // =========================================================================
    let activeCheckoutKit = { name: 'Diamond Kit', base: 100, gst: 10, total: 110 };

    function openKitCheckout(name, base, gst, total) {
      activeCheckoutKit = { name, base, gst, total };
      const modal = document.getElementById('kit-checkout-modal');
      document.getElementById('checkout-kit-title').textContent = `Buy ${name}`;
      document.getElementById('checkout-base-label').textContent = `${name} Base Price:`;
      document.getElementById('checkout-base-val').textContent = `₹${base}`;
      document.getElementById('checkout-gst-val').textContent = `+₹${gst}`;
      document.getElementById('checkout-total-val').textContent = `₹${total}`;

      updateCheckoutUpiLinks();
      modal.classList.remove('hidden');
      modal.classList.add('flex');
    }

    function closeKitCheckout() {
      const modal = document.getElementById('kit-checkout-modal');
      modal.classList.add('hidden');
      modal.classList.remove('flex');
    }

    function updateCheckoutUpiLinks() {
      const ignVal = (document.getElementById('checkout-ign-input')?.value || '').trim();
      const note = ignVal ? `${activeCheckoutKit.name} - IGN: ${ignVal}` : `${activeCheckoutKit.name} (3d Insured)`;
      const upiUri = `upi://pay?pa=ghostmc.fund@ybl&pn=PineappleSMP&am=${activeCheckoutKit.total}&cu=INR&tn=${encodeURIComponent(note)}`;

      const deepLink = document.getElementById('checkout-upi-deeplink');
      const qrImg = document.getElementById('checkout-qr-img');
      if (deepLink) deepLink.href = upiUri;
      if (qrImg) {
        qrImg.src = `https://api.qrserver.com/v1/create-qr-code/?size=220x220&data=${encodeURIComponent(upiUri)}`;
      }
    }

    // =========================================================================
    // PINEAPPLEBOT AI SUPPORT ENGINE (3-LANGUAGE + FRESH VARIED REPLY EVERY TIME)
    // =========================================================================
    let selectedAiLanguage = 'English';
    const aiConversationHistory = [];
    const aiMessageStore = {};
    let lastLocalVariantIndex = -1;

    function setAiLanguage(lang) {
      selectedAiLanguage = lang;
      ['English', 'Hindi', 'Hinglish'].forEach(item => {
        const btn = document.getElementById(`lang-btn-${item}`);
        if (!btn) return;
        if (item === lang) {
          btn.className = 'px-3 py-1.5 rounded-lg text-xs font-extrabold transition-all bg-gradient-to-r from-pineapple-500 to-amber-500 text-slate-950 shadow';
        } else {
          btn.className = 'px-3 py-1.5 rounded-lg text-xs font-extrabold transition-all text-slate-300 hover:text-white hover:bg-slate-800';
        }
      });
      showToast(`AI Language set to ${lang}`);
    }

    function escapeHtml(str) {
      const div = document.createElement('div');
      div.textContent = str;
      return div.innerHTML;
    }

    function formatAiText(rawText) {
      const escaped = escapeHtml(rawText);
      return escaped
        .replace(/\*\*(.*?)\*\*/g, '<strong class="text-pineapple-300 font-bold">$1</strong>')
        .replace(/`(.*?)`/g, '<code class="bg-slate-950 text-emerald-300 px-1.5 py-0.5 rounded font-mono text-xs border border-slate-800">$1</code>')
        .replace(/^\s*[\*\-]\s+(.*)$/gm, '<div class="flex items-start gap-2 my-1"><span class="text-emerald-400 font-bold">&bull;</span><span>$1</span></div>')
        .replace(/\n/g, '<br>');
    }

    function appendUserChatMessage(text) {
      const feed = document.getElementById('ai-chat-messages');
      if (!feed) return;
      const wrapper = document.createElement('div');
      wrapper.className = 'flex items-start justify-end gap-3 chat-msg-enter';
      wrapper.innerHTML = `
        <div class="max-w-[82%] bg-gradient-to-br from-amber-500/20 to-emerald-500/20 border border-pineapple-400/50 rounded-2xl rounded-tr-none px-4 py-3 text-xs sm:text-sm text-white leading-relaxed shadow">
          <div class="text-[10px] font-bold uppercase tracking-wider text-pineapple-300 mb-0.5 text-right">You</div>
          <div>${escapeHtml(text)}</div>
        </div>
        <div class="w-9 h-9 rounded-xl bg-slate-800 border border-pineapple-400/60 text-pineapple-300 flex items-center justify-center shrink-0">
          <i class="fa-solid fa-user"></i>
        </div>
      `;
      feed.appendChild(wrapper);
      feed.scrollTo({ top: feed.scrollHeight, behavior: 'smooth' });
    }

    function appendAiChatMessage(replyText, originalQuestion) {
      const feed = document.getElementById('ai-chat-messages');
      if (!feed) return;

      const msgId = 'ai-msg-' + Date.now() + '-' + Math.floor(Math.random() * 1000);
      aiMessageStore[msgId] = { question: originalQuestion, lastReply: replyText };

      const wrapper = document.createElement('div');
      wrapper.className = 'flex items-start gap-3 chat-msg-enter';
      wrapper.innerHTML = `
        <div class="w-9 h-9 rounded-xl bg-gradient-to-br from-pineapple-500 to-emerald-600 text-slate-950 font-black flex items-center justify-center shrink-0 shadow-md">
          <i class="fa-solid fa-robot"></i>
        </div>
        <div class="flex-1 bg-slate-900/95 border border-pineapple-500/35 rounded-2xl rounded-tl-none p-4 text-xs sm:text-sm text-slate-200 leading-relaxed shadow-md">
          <div class="flex flex-wrap items-center justify-between gap-2 mb-2 pb-2 border-b border-slate-800/80">
            <div class="text-[11px] font-bold text-emerald-400 flex items-center gap-1.5">
              <i class="fa-solid fa-sparkles text-pineapple-300"></i>
              <span>PineappleBot AI (${escapeHtml(selectedAiLanguage)})</span>
            </div>
            <button type="button" id="${msgId}-regen" onclick="regenerateAiMessage('${msgId}')" class="px-2.5 py-1 rounded-lg text-[10px] font-extrabold uppercase tracking-wider transition-all bg-slate-800/90 hover:bg-pineapple-500 text-pineapple-300 hover:text-slate-950 border border-pineapple-500/40 flex items-center gap-1.5">
              <i class="fa-solid fa-arrows-rotate"></i>
              <span>New Answer</span>
            </button>
          </div>

          <div id="${msgId}-body" class="transition-opacity duration-150">${formatAiText(replyText)}</div>

          <div class="mt-3 pt-2.5 border-t border-slate-800 flex flex-wrap items-center justify-between gap-2 text-[11px] text-slate-400">
            <span>Issue not resolved? Create a ticket on Discord:</span>
            <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-1.5 bg-[#5865F2] hover:bg-[#4752c4] text-white font-bold px-3 py-1 rounded-lg transition-colors">
              <i class="fa-brands fa-discord"></i>
              <span>Create Discord Ticket</span>
            </a>
          </div>
        </div>
      `;
      feed.appendChild(wrapper);
      feed.scrollTo({ top: feed.scrollHeight, behavior: 'smooth' });
    }

    function pickDistinctVariant(pool) {
      if (!pool || pool.length === 0) return '';
      if (pool.length === 1) return pool[0];
      let idx = Math.floor(Math.random() * pool.length);
      if (idx === lastLocalVariantIndex) {
        idx = (idx + 1 + Math.floor(Math.random() * (pool.length - 1))) % pool.length;
      }
      lastLocalVariantIndex = idx;
      return pool[idx];
    }

    function buildFreshLocalAnswer(question, lang, previousReply = '') {
      const q = question.toLowerCase();
      const isGreeting = /^(hi|hello|hey|yo|namaste|kya hal|kaise ho|how are you|sup|hii|helo)\b/.test(q.trim());
      const isFunder = q.includes('funder') || q.includes('flaxxy') || q.includes('sponsor') || q.includes('donor');
      const isKits = q.includes('kit') || q.includes('insurance') || q.includes('gst') || q.includes('upi') || q.includes('buy') || q.includes('price') || q.includes('stone') || q.includes('iron') || q.includes('diamond') || q.includes('netherite') || q.includes('ender');
      const isBedrock = q.includes('bedrock') || q.includes('pocket') || q.includes('mobile') || q.includes('port') || q.includes('19149');
      const isJava = q.includes('java') || q.includes('pc') || q.includes('19126');

      let pool = [];

      if (lang === 'Hindi') {
        if (isGreeting) {
          pool = [
            `नमस्ते योद्धा! मैं **PineappleBot AI** हूँ — बिल्कुल बढ़िया हूँ! बताइए, क्या आप आज **PineappleSMP Season 1** खेलने के लिए तैयार हैं?`,
            `हेल्लो दोस्त! PineappleSMP में आपका स्वागत है। आप मुझसे सामान्य बातचीत कर सकते हैं, या सर्वर IP (\`basic.vitalcloud.in\`), Battle Kits, या किसी भी Minecraft एरर के बारे में पूछ सकते हैं!`,
            `नमस्कार! आज मैं आपकी क्या मदद कर सकता हूँ? चाहे Minecraft में कोई एरर आ रहा हो या Lifesteal SMP के बारे में जानना हो, बेझिझक पूछें!`
          ];
        } else if (isFunder) {
          pool = [
            `**PineappleSMP के आधिकारिक Founding Funder:** हमारे सर्वर के वर्तमान Funder **flaxxy444** हैं! उनका नाम हमारे Server Funders हॉल ऑफ ऑनर में गर्व से शामिल है।`,
            `हमारे नेट्वर्क को सपोर्ट करने वाले मुख्य Funder **flaxxy444** हैं। यदि आप भी Funder बनना चाहते हैं, तो Battle Kits Store से किट खरीदें या Discord (**https://discord.gg/Vp9Ss592cq**) पर संपर्क करें!`
          ];
        } else if (isKits) {
          pool = [
            `**PineappleSMP Battle Kits और 3-Day Damage Insurance (10% GST):**\n1. **Stone Kit:** ₹30 + ₹3 (10% GST) = **₹33**\n2. **Iron Kit:** ₹50 + ₹5 (10% GST) = **₹55**\n3. **Diamond Kit:** ₹100 + ₹10 (10% GST) = **₹110**\n4. **Netherite Kit:** ₹125 + ₹13 (10% GST) = **₹138**\n5. **Ender Kit:** ₹150 + ₹15 (10% GST) = **₹165**\n\nUPI ID \`ghostmc.fund@ybl\` पर पेमेंट करने के बाद **स्क्रीनशॉट लेकर Discord (https://discord.gg/Vp9Ss592cq) पर टिकट बनाएं**!`,
            `**3-Day Kit Damage Insurance नियम:** हर किट पर 10% GST के रूप में 3 दिन का डैमेज इंश्योरेंस शामिल है। यदि खरीदने के 3 दिन के अंदर आपकी किट डैमेज होती है, तो हमारी स्टाफ टीम उसे रिपेयर करेगी या नई किट देगी।`
          ];
        } else if (isBedrock) {
          pool = [
            `**Bedrock Edition कनेक्शन विवरण:**\n1. **Server Address:** \`basic.vitalcloud.in\`\n2. **Port:** \`19149\`\n3. अगर एरर आए तो Minecraft रीस्टार्ट करें और मोबाइल डेटा/Wi-Fi चेक करें।`,
            `**मोबाइल / कंसोल से जुड़ने के स्टेप्स:** Minecraft खोलें &rarr; **Play** &rarr; **Servers** &rarr; **Add Server** पर जाएं, IP \`basic.vitalcloud.in\` और Port \`19149\` डालकर Save करें।`
          ];
        } else if (isJava) {
          pool = [
            `**Java Edition (PC) कनेक्शन विवरण:**\n1. **Server Address:** \`basic.vitalcloud.in:19126\`\n2. Multiplayer &rarr; Direct Connection या Add Server में जाकर जुड़ें।`,
            `**PC प्लेयर्स के लिए टिप:** Java 1.19 से 1.21+ के सभी वर्जन सपोर्टेड हैं। \`basic.vitalcloud.in:19126\` डालें और Lifesteal Season 1 का आनंद लें!`
          ];
        } else {
          pool = [
            `**PineappleSMP त्वरित सहायता:**\n1. **Java IP:** \`basic.vitalcloud.in:19126\`\n2. **Bedrock IP:** \`basic.vitalcloud.in\` | **Port:** \`19149\`\n3. किसी भी एरर के लिए अपना गेम रीस्टार्ट करें और इंटरनेट चेक करें।`,
            `**स्टेप-बाय-स्टेप समाधान:**\n1. Minecraft वर्जन 1.20 - 1.21+ अपडेट रखें।\n2. सर्वर एड्रेस बिना किसी स्पेस के सही टाइप करें।\n3. समस्या हल न होने पर हमारे Discord (https://discord.gg/Vp9Ss592cq) पर टिकट बनाएं।`
          ];
        }
      } else if (lang === 'Hinglish') {
        if (isGreeting) {
          pool = [
            `Hey bhai! Main **PineappleBot AI** hoon — ekdum mast! Batao aaj **PineappleSMP Season 1** me Lifesteal khelne ka plan hai kya?`,
            `Hello warrior! Swagat hai PineappleSMP par. Tum mujhse normal baat bhi kar sakte ho, ya IP (\`basic.vitalcloud.in\`), Battle Kits, aur Minecraft errors ke baare me pooch sakte ho!`,
            `Yo! Kaise ho bhai? Koi Minecraft error aa raha ho, kit buy karni ho, ya bas timepass baat karni ho — main hamesha ready hoon!`
          ];
        } else if (isFunder) {
          pool = [
            `**PineappleSMP Server Funders:** Abhi hamare official Founding Funder **flaxxy444** hain! Unhone Season 1 ko support kiya hai. Agar aap bhi Funder banna chahte hain toh Discord (**https://discord.gg/Vp9Ss592cq**) par message karein!`,
            `Hamare Server Funders list me abhi **flaxxy444** shamil hain — unka 3D avatar website ke Funders section me featured hai!`
          ];
        } else if (isKits) {
          pool = [
            `**PineappleSMP Battle Kits & 3-Day Damage Insurance (10% GST):**\n1. **Stone Kit:** ₹30 + ₹3 (10% GST) = **₹33**\n2. **Iron Kit:** ₹50 + ₹5 (10% GST) = **₹55**\n3. **Diamond Kit:** ₹100 + ₹10 (10% GST) = **₹110**\n4. **Netherite Kit:** ₹125 + ₹13 (10% GST) = **₹138**\n5. **Ender Kit:** ₹150 + ₹15 (10% GST) = **₹165**\n\nUPI ID \`ghostmc.fund@ybl\` par payment ke baad **screenshot lekar Discord (https://discord.gg/Vp9Ss592cq) par ticket zaroor banayein**!`,
            `**3-Day Insurance Policy:** 10% GST insurance me agar purchase ke **3 din ke andar** aapki kit damage hoti hai, toh hum aapko **new kit denge ya usi kit ko repair karke denge**!`
          ];
        } else if (isBedrock) {
          pool = [
            `**Bedrock / Pocket Edition Join Details:**\n1. **Server Address:** \`basic.vitalcloud.in\`\n2. **Port:** \`19149\`\n3. Error aaye toh Minecraft restart karein aur DNS \`1.1.1.1\` try karein.`,
            `**Mobile & Console Setup:** Minecraft kholein &rarr; **Play** &rarr; **Servers** &rarr; **Add Server** par click karein, IP \`basic.vitalcloud.in\` aur Port \`19149\` daal kar Save karein.`
          ];
        } else if (isJava) {
          pool = [
            `**Java Edition (PC) Join Details:**\n1. **Server Address:** \`basic.vitalcloud.in:19126\`\n2. Multiplayer &rarr; Direct Connection me jaakar turant join karein!`,
            `**PC Warriors ke liye:** Java 1.19 se 1.21+ sabhi versions supported hain. Bas \`basic.vitalcloud.in:19126\` enter karein aur Season 1 enjoy karein.`
          ];
        } else {
          pool = [
            `**PineappleSMP Quick Help:**\n1. **Java IP:** \`basic.vitalcloud.in:19126\`\n2. **Bedrock IP:** \`basic.vitalcloud.in\` | **Port:** \`19149\`\n3. Agar koi error aa raha hai toh game restart karke dobara try karein.`,
            `**Step-by-Step Troubleshooting:**\n1. Apna Minecraft version 1.20 - 1.21+ par rakhein.\n2. IP aur Port me koi extra space na chhodein.\n3. Phir bhi solve na ho toh Discord (https://discord.gg/Vp9Ss592cq) par ticket banayein!`
          ];
        }
      } else {
        if (isGreeting) {
          pool = [
            `Hey there, warrior! I'm **PineappleBot AI** and I'm doing awesome! Ready to jump into **PineappleSMP Season 1** today?`,
            `Hello! Welcome to PineappleSMP. Feel free to chat casually with me, or ask anything about server IPs (\`basic.vitalcloud.in\`), Battle Kits, or Minecraft troubleshooting!`,
            `Hey! How's your day going? Whether you need help fixing a Minecraft error, checking out our 3-day insured Battle Kits, or just want to chat, I've got your back!`
          ];
        } else if (isFunder) {
          pool = [
            `**PineappleSMP Official Server Funders:** Our current Founding Funder is **flaxxy444**, honored in our Server Funders showcase! Want to become a funder too? Check out the Battle Kits Store or reach out on Discord (**https://discord.gg/Vp9Ss592cq**).`,
            `Shoutout to **flaxxy444**, our Founding Funder for PineappleSMP Season 1! You can view their badge in the **Server Funders** section right above.`
          ];
        } else if (isKits) {
          pool = [
            `**PineappleSMP Battle Kits & 3-Day Damage Insurance (10% GST):**\n1. **Stone Kit:** ₹30 + ₹3 (10% GST) = **₹33 Total**\n2. **Iron Kit:** ₹50 + ₹5 (10% GST) = **₹55 Total**\n3. **Diamond Kit:** ₹100 + ₹10 (10% GST) = **₹110 Total**\n4. **Netherite Kit:** ₹125 + ₹13 (10% GST) = **₹138 Total**\n5. **Ender Kit:** ₹150 + ₹15 (10% GST) = **₹165 Total**\n\nPay via UPI \`ghostmc.fund@ybl\`, take a **transaction screenshot**, and open a ticket on Discord (**https://discord.gg/Vp9Ss592cq**)!`,
            `**3-Day Kit Damage Insurance Policy:** Every kit includes +10% GST for 3-day damage protection. If your kit gets damaged within 3 days of purchase, our staff will repair it or replace it with a brand-new kit!`
          ];
        } else if (isBedrock) {
          pool = [
            `**Bedrock / Pocket Edition Connection Details:**\n1. **Server Address:** \`basic.vitalcloud.in\`\n2. **Port:** \`19149\`\n3. Restart Minecraft and check your network if you see a connection error.`,
            `**Step-by-Step Mobile & Console Setup:** Open Minecraft &rarr; **Play** &rarr; **Servers** &rarr; **Add Server**, enter IP \`basic.vitalcloud.in\` and Port \`19149\`, then tap **Save** and join!`
          ];
        } else if (isJava) {
          pool = [
            `**Java Edition (PC) Connection Details:**\n1. **Server Address:** \`basic.vitalcloud.in:19126\`\n2. Open Multiplayer &rarr; Direct Connection or Add Server to join immediately!`,
            `**Supported PC Versions:** Java Edition 1.19 through 1.21+ are all supported. Enter \`basic.vitalcloud.in:19126\` to enter Season 1 Lifesteal.`
          ];
        } else {
          pool = [
            `**PineappleSMP Quick Guide:**\n1. **Java IP:** \`basic.vitalcloud.in:19126\`\n2. **Bedrock IP:** \`basic.vitalcloud.in\` | **Port:** \`19149\`\n3. Restart your Minecraft client and check your connection if an error occurs.`,
            `**Troubleshooting Steps:**\n1. Verify you are on Minecraft 1.20 - 1.21+.\n2. Ensure there are no trailing spaces in the IP or Port.\n3. If the issue isn't solved, open a support ticket on Discord (**https://discord.gg/Vp9Ss592cq**).`
          ];
        }
      }

      const filtered = pool.filter(item => item !== previousReply);
      return pickDistinctVariant(filtered.length > 0 ? filtered : pool);
    }

    async function fetchSingleFreshAiReply(userQuestion, previousReply = '') {
      let languageInstruction = 'Respond strictly in clear, natural English.';
      if (selectedAiLanguage === 'Hindi') {
        languageInstruction = 'Respond strictly in Hindi using Devanagari script (हिंदी में जवाब दें).';
      } else if (selectedAiLanguage === 'Hinglish') {
        languageInstruction = 'Respond strictly in Hinglish (natural conversational Hindi written in English/Latin script, e.g., "Bhai aap ye steps follow karo...").';
      }

      const styleAngles = [
        'Tone: Energetic, friendly Minecraft Lifesteal buddy with crisp formatting.',
        'Tone: Calm, crystal-clear technical mentor with numbered actionable steps.',
        'Tone: Warm, witty community helper who explains things simply and naturally.',
        'Tone: Enthusiastic pro SMP veteran giving practical insider advice.'
      ];
      const randomStyle = styleAngles[Math.floor(Math.random() * styleAngles.length)];
      const uniquenessNonce = `${Date.now()}-${Math.floor(Math.random() * 100000)}`;

      const avoidNote = previousReply
        ? `\nCRITICAL: Do NOT repeat your previous wording. Write a completely fresh, newly phrased response different from: "${previousReply.slice(0, 180)}..."`
        : '';

      const systemPrompt = `You are PineappleBot AI, the friendly 24/7 companion and technical support assistant for the PineappleSMP Minecraft Lifesteal server.
Official Server Facts:
- Server Name: PineappleSMP (Season 1 Launched, Hosted on VitalCloud for 24/7 ultra-low ping)
- Founding Funder: flaxxy444 (featured in our Server Funders showcase)
- Game Mode: Lifesteal SMP (Kill = +1 Heart, Death = -1 Heart, Revive Beacons, Crossplay)
- Java Edition IP & Port: basic.vitalcloud.in:19126
- Bedrock / Pocket Edition IP: basic.vitalcloud.in | Port: 19149
- Official Discord Server: https://discord.gg/Vp9Ss592cq
- Official Store UPI ID: ghostmc.fund@ybl
- Battle Kits & 10% Insurance GST Pricing:
  * Stone Kit: ₹30 + ₹3 (10% GST) = ₹33 Total
  * Iron Kit: ₹50 + ₹5 (10% GST) = ₹55 Total
  * Diamond Kit: ₹100 + ₹10 (10% GST) = ₹110 Total
  * Netherite Kit: ₹125 + ₹13 (10% GST) = ₹138 Total
  * Ender Kit: ₹150 + ₹15 (10% GST) = ₹165 Total
- 3-Day Kit Damage Insurance Policy: Every kit includes 10% GST for 3-Day Kit Damage Insurance. If a purchased kit gets damaged within 3 days of purchase, staff will repair it or replace it with a brand-new kit.
- Claiming Kits: After paying via UPI (ghostmc.fund@ybl), players MUST take a screenshot of the transaction and open a support ticket on Discord (https://discord.gg/Vp9Ss592cq) to claim their kit and activate insurance.

Rules:
1. ${languageInstruction}
2. ${randomStyle} (Variation Seed: ${uniquenessNonce})
3. Provide ONE single, clean, natural, well-structured response. Never output multiple numbered options like "Answer 1 / Answer 2".
4. Support both natural casual conversation AND technical Minecraft troubleshooting.
5. For any error or bug, provide clear numbered step-by-step fixes and remind them to open a Discord ticket (https://discord.gg/Vp9Ss592cq) if unresolved.${avoidNote}`;

      try {
        const apiKey = "";
        const endpoint = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${apiKey}`;

        const response = await fetch(endpoint, {
          method: 'POST',
          headers: { 'Content-Type': 'application/json' },
          body: JSON.stringify({
            systemInstruction: { parts: [{ text: systemPrompt }] },
            contents: aiConversationHistory,
            generationConfig: {
              temperature: 0.95,
              topP: 0.95,
              maxOutputTokens: 650
            }
          })
        });

        if (response.ok) {
          const result = await response.json();
          const textReply = result?.candidates?.[0]?.content?.parts?.[0]?.text;
          if (textReply && textReply.trim().length > 0) {
            return textReply.trim();
          }
        }
      } catch (err) {}

      return buildFreshLocalAnswer(userQuestion, selectedAiLanguage, previousReply);
    }

    async function queryPineappleAi(userQuestion) {
      const feed = document.getElementById('ai-chat-messages');
      const sendBtn = document.getElementById('ai-send-btn');
      if (!feed) return;

      if (sendBtn) sendBtn.disabled = true;

      const typingId = 'ai-typing-' + Date.now();
      const typingDiv = document.createElement('div');
      typingDiv.id = typingId;
      typingDiv.className = 'flex items-center gap-3 chat-msg-enter';
      typingDiv.innerHTML = `
        <div class="w-9 h-9 rounded-xl bg-gradient-to-br from-pineapple-500 to-emerald-600 text-slate-950 font-black flex items-center justify-center shrink-0">
          <i class="fa-solid fa-robot"></i>
        </div>
        <div class="bg-slate-900/95 border border-pineapple-500/35 rounded-2xl rounded-tl-none px-4 py-3 text-xs text-pineapple-300 flex items-center gap-2.5 shadow-md">
          <span class="flex gap-1">
            <span class="w-1.5 h-1.5 rounded-full bg-pineapple-400 animate-bounce" style="animation-delay: 0ms"></span>
            <span class="w-1.5 h-1.5 rounded-full bg-amber-400 animate-bounce" style="animation-delay: 150ms"></span>
            <span class="w-1.5 h-1.5 rounded-full bg-emerald-400 animate-bounce" style="animation-delay: 300ms"></span>
          </span>
          <span>Thinking in ${selectedAiLanguage}...</span>
        </div>
      `;
      feed.appendChild(typingDiv);
      feed.scrollTo({ top: feed.scrollHeight, behavior: 'smooth' });

      aiConversationHistory.push({ role: 'user', parts: [{ text: userQuestion }] });
      if (aiConversationHistory.length > 10) {
        aiConversationHistory.splice(0, aiConversationHistory.length - 10);
      }

      const freshReply = await fetchSingleFreshAiReply(userQuestion);
      aiConversationHistory.push({ role: 'model', parts: [{ text: freshReply }] });

      const typingEl = document.getElementById(typingId);
      if (typingEl) typingEl.remove();

      appendAiChatMessage(freshReply, userQuestion);
      if (sendBtn) sendBtn.disabled = false;
    }

    async function regenerateAiMessage(msgId) {
      const record = aiMessageStore[msgId];
      if (!record) return;

      const bodyEl = document.getElementById(`${msgId}-body`);
      const regenBtn = document.getElementById(`${msgId}-regen`);
      if (!bodyEl || !regenBtn) return;

      regenBtn.disabled = true;
      regenBtn.innerHTML = `<i class="fa-solid fa-arrows-rotate fa-spin"></i><span>Writing...</span>`;
      bodyEl.style.opacity = '0.4';

      const newReply = await fetchSingleFreshAiReply(record.question, record.lastReply);
      record.lastReply = newReply;

      bodyEl.innerHTML = formatAiText(newReply);
      bodyEl.style.opacity = '1';
      regenBtn.disabled = false;
      regenBtn.innerHTML = `<i class="fa-solid fa-arrows-rotate"></i><span>New Answer</span>`;
    }

    function handleAiChatSubmit(e) {
      e.preventDefault();
      const inputEl = document.getElementById('ai-user-input');
      if (!inputEl) return;
      const question = inputEl.value.trim();
      if (!question) return;

      inputEl.value = '';
      appendUserChatMessage(question);
      queryPineappleAi(question);
    }

    function sendQuickAiPrompt(promptText) {
      appendUserChatMessage(promptText);
      queryPineappleAi(promptText);
    }

    // =========================================================================
    // LIVE FOUNDER DISCORD PROFILE SYNC (devesh_37.)
    // =========================================================================
    const FOUNDER_DISCORD_USERNAME = 'devesh_37.';
    const DISCORD_CONFIG_STORAGE_KEY = 'pineapplesmp_founder_discord_cfg_v1';

    let founderDiscordConfig = {
      userId: '',
      displayName: 'Devesh',
      username: FOUNDER_DISCORD_USERNAME,
      bio: 'PineappleSMP Founder & Developer | Bedrock & Java Crossplay Lifesteal Network | DM or open a ticket on Discord!',
      avatarUrl: ''
    };

    try {
      const savedCfg = localStorage.getItem(DISCORD_CONFIG_STORAGE_KEY);
      if (savedCfg) {
        founderDiscordConfig = { ...founderDiscordConfig, ...JSON.parse(savedCfg) };
      }
    } catch (e) {}

    function toggleDiscordConfigDrawer() {
      const drawer = document.getElementById('discord-config-drawer');
      if (!drawer) return;
      drawer.classList.toggle('hidden');
      if (!drawer.classList.contains('hidden')) {
        const idInp = document.getElementById('discord-snowflake-input');
        const bioInp = document.getElementById('discord-bio-override-input');
        if (idInp) idInp.value = founderDiscordConfig.userId || '';
        if (bioInp) bioInp.value = founderDiscordConfig.bio || '';
      }
    }

    async function saveFounderDiscordSettings() {
      const idInp = document.getElementById('discord-snowflake-input');
      const bioInp = document.getElementById('discord-bio-override-input');
      const newUserId = idInp ? idInp.value.trim().replace(/\D/g, '') : '';
      const newBio = bioInp ? bioInp.value.trim() : '';

      founderDiscordConfig.userId = newUserId;
      if (newBio) founderDiscordConfig.bio = newBio;

      try {
        localStorage.setItem(DISCORD_CONFIG_STORAGE_KEY, JSON.stringify(founderDiscordConfig));
      } catch (e) {}

      toggleDiscordConfigDrawer();
      await syncFounderDiscordProfile(true);
      showToast('Founder Discord sync settings updated!');
    }

    function applyDiscordProfileToUI(data) {
      const pfpEl = document.getElementById('discord-founder-pfp');
      const decoEl = document.getElementById('discord-founder-decoration');
      const nameEl = document.getElementById('discord-founder-displayname');
      const userEl = document.getElementById('discord-founder-username');
      const bioEl = document.getElementById('discord-founder-bio');
      const statusDotEl = document.getElementById('discord-founder-status-dot');
      const statusPillEl = document.getElementById('discord-status-text-pill');
      const customStatusEl = document.getElementById('discord-custom-status');
      const bannerEl = document.getElementById('discord-card-banner');
      const timeEl = document.getElementById('discord-last-synced-time');

      if (pfpEl && data.avatarUrl) pfpEl.src = data.avatarUrl;
      if (decoEl) {
        if (data.decorationUrl) {
          decoEl.src = data.decorationUrl;
          decoEl.classList.remove('hidden');
        } else {
          decoEl.classList.add('hidden');
        }
      }
      if (nameEl) nameEl.textContent = data.displayName || 'Devesh';
      if (userEl) userEl.textContent = data.username || FOUNDER_DISCORD_USERNAME;
      if (bioEl) bioEl.textContent = data.bio || founderDiscordConfig.bio;

      if (bannerEl && data.bannerUrl) {
        bannerEl.style.backgroundImage = `url('${data.bannerUrl}')`;
        bannerEl.style.backgroundSize = 'cover';
        bannerEl.style.backgroundPosition = 'center';
      }

      const status = (data.status || 'online').toLowerCase();
      if (statusDotEl && statusPillEl) {
        if (status === 'dnd') {
          statusDotEl.className = 'absolute bottom-1 right-1 w-6 h-6 rounded-full bg-rose-500 border-4 border-slate-950 shadow-md';
          statusPillEl.className = 'font-bold text-rose-400 uppercase tracking-wider text-[10px] px-2 py-0.5 rounded bg-rose-500/15 border border-rose-500/30';
          statusPillEl.textContent = 'Do Not Disturb';
        } else if (status === 'idle') {
          statusDotEl.className = 'absolute bottom-1 right-1 w-6 h-6 rounded-full bg-amber-400 border-4 border-slate-950 shadow-md';
          statusPillEl.className = 'font-bold text-amber-300 uppercase tracking-wider text-[10px] px-2 py-0.5 rounded bg-amber-500/15 border border-amber-500/30';
          statusPillEl.textContent = 'Idle';
        } else if (status === 'offline') {
          statusDotEl.className = 'absolute bottom-1 right-1 w-6 h-6 rounded-full bg-slate-500 border-4 border-slate-950 shadow-md';
          statusPillEl.className = 'font-bold text-slate-400 uppercase tracking-wider text-[10px] px-2 py-0.5 rounded bg-slate-500/15 border border-slate-500/30';
          statusPillEl.textContent = 'Offline';
        } else {
          statusDotEl.className = 'absolute bottom-1 right-1 w-6 h-6 rounded-full bg-emerald-500 border-4 border-slate-950 shadow-md';
          statusPillEl.className = 'font-bold text-emerald-400 uppercase tracking-wider text-[10px] px-2 py-0.5 rounded bg-emerald-500/15 border border-emerald-500/30';
          statusPillEl.textContent = 'Online';
        }
      }

      if (customStatusEl) {
        customStatusEl.textContent = data.activity || 'Building & managing PineappleSMP Season 1';
      }

      if (timeEl) {
        const nowStr = new Date().toLocaleTimeString([], { hour: '2-digit', minute: '2-digit', second: '2-digit' });
        timeEl.textContent = `Live Synced • ${nowStr}`;
      }
    }

    async function syncFounderDiscordProfile(manual = false) {
      const iconEl = document.getElementById('discord-sync-icon');
      if (manual && iconEl) iconEl.classList.add('fa-spin');

      let resolved = false;
      const cacheBust = `?_=${Date.now()}`;

      if (founderDiscordConfig.userId) {
        try {
          const res = await fetch(`https://api.lanyard.rest/v1/users/${founderDiscordConfig.userId}${cacheBust}`);
          if (res.ok) {
            const json = await res.json();
            if (json && json.success && json.data && json.data.discord_user) {
              const u = json.data.discord_user;
              const ext = u.avatar && u.avatar.startsWith('a_') ? 'gif' : 'png';
              const avatarUrl = u.avatar
                ? `https://cdn.discordapp.com/avatars/${u.id}/${u.avatar}.${ext}?size=256`
                : `https://cdn.discordapp.com/embed/avatars/0.png`;
              const decorationUrl = u.avatar_decoration_data?.asset
                ? `https://cdn.discordapp.com/avatar-decoration-presets/${u.avatar_decoration_data.asset}.png?size=256`
                : '';

              let activityText = 'Building & managing PineappleSMP Season 1';
              if (Array.isArray(json.data.activities) && json.data.activities.length > 0) {
                const customAct = json.data.activities.find(a => a.type === 4);
                const gameAct = json.data.activities.find(a => a.type !== 4);
                if (customAct && customAct.state) {
                  activityText = customAct.state;
                } else if (gameAct) {
                  activityText = `Playing ${gameAct.name}${gameAct.details ? ' — ' + gameAct.details : ''}`;
                }
              }

              applyDiscordProfileToUI({
                displayName: u.global_name || u.display_name || u.username || 'Devesh',
                username: FOUNDER_DISCORD_USERNAME,
                avatarUrl,
                decorationUrl,
                status: json.data.discord_status || 'online',
                activity: activityText,
                bio: json.data.kv?.bio || founderDiscordConfig.bio
              });
              resolved = true;
            }
          }
        } catch (err) {}
      }

      if (!resolved) {
        const lookupTargets = founderDiscordConfig.userId
          ? [`https://discordlookup.mesalytic.moe/v1/user/${founderDiscordConfig.userId}`]
          : [`https://discordlookup.mesalytic.moe/v1/user/${encodeURIComponent(FOUNDER_DISCORD_USERNAME)}`];

        for (const url of lookupTargets) {
          try {
            const res = await fetch(url);
            if (res.ok) {
              const u = await res.json();
              if (u && (u.id || u.username)) {
                const avatarLink = u.avatar?.link
                  ? `${u.avatar.link}?size=256`
                  : (u.id && u.avatar?.id
                      ? `https://cdn.discordapp.com/avatars/${u.id}/${u.avatar.id}.png?size=256`
                      : `https://cdn.discordapp.com/embed/avatars/0.png`);
                const bannerLink = u.banner?.link ? `${u.banner.link}?size=600` : '';

                applyDiscordProfileToUI({
                  displayName: u.global_name || u.display_name || u.username || 'Devesh',
                  username: u.username || FOUNDER_DISCORD_USERNAME,
                  avatarUrl: avatarLink,
                  bannerUrl: bannerLink,
                  status: 'online',
                  activity: 'Building & managing PineappleSMP Season 1',
                  bio: u.bio || founderDiscordConfig.bio
                });
                resolved = true;
                break;
              }
            }
          } catch (err) {}
        }
      }

      if (!resolved) {
        applyDiscordProfileToUI({
          displayName: founderDiscordConfig.displayName || 'Devesh',
          username: FOUNDER_DISCORD_USERNAME,
          avatarUrl: founderDiscordConfig.avatarUrl || 'https://mc-heads.net/avatar/Devesh/128',
          status: 'online',
          activity: 'Building & managing PineappleSMP Season 1',
          bio: founderDiscordConfig.bio
        });
      }

      if (manual && iconEl) {
        setTimeout(() => iconEl.classList.remove('fa-spin'), 450);
      }
    }

    // Initialize Live Server Telemetry (Every 5s) & Live Founder Discord Sync (Every 15s)
    window.addEventListener('DOMContentLoaded', () => {
      fetchLiveServerStatus(true);
      setInterval(() => fetchLiveServerStatus(false), 5000);
      syncFounderDiscordProfile(false);
      setInterval(() => syncFounderDiscordProfile(false), 15000);
    });
  </script>
</body>
</html>
