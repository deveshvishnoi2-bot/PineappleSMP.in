<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>PineappleSMP | Minecraft Lifesteal & Survival Adventure</title>
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Font Awesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@700;900&family=Inter:wght@400;500;600;700;800&family=Outfit:wght@600;800;900&family=Press+Start+2P&family=VT323&display=swap" rel="stylesheet">
  
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            pineapple: {
              300: '#FDE047',
              400: '#FACC15',
              500: '#EAB308',
              600: '#CA8A04',
              700: '#A16207',
            },
            jungle: {
              400: '#34D399',
              500: '#10B981',
              600: '#059669',
              700: '#047857',
            },
            smpDark: '#070B08',
            smpCard: '#111914',
            smpBorder: '#243A2B'
          },
          fontFamily: {
            heading: ['Outfit', 'sans-serif'],
            pixel: ['"Press Start 2P"', 'monospace'],
            mc: ['VT323', 'monospace'],
            cinzel: ['Cinzel', 'serif'],
            sans: ['Inter', 'sans-serif']
          }
        }
      }
    }
  </script>
  <style>
    body {
      background-color: #060907;
      color: #E2E8F0;
      overflow-x: hidden;
      font-family: 'Inter', sans-serif;
    }

    /* Authentic Minecraft Beveled Block Card */
    .mc-panel {
      background: linear-gradient(180deg, rgba(22, 34, 26, 0.96) 0%, rgba(12, 18, 14, 0.98) 100%);
      border: 2px solid #2A4332;
      box-shadow:
        inset 2px 2px 0px rgba(255, 255, 255, 0.08),
        inset -2px -2px 0px rgba(0, 0, 0, 0.65),
        0 10px 30px rgba(0, 0, 0, 0.55);
    }
    .mc-panel:hover {
      border-color: rgba(250, 204, 21, 0.55);
    }

    /* Minecraft 3D Beveled Button */
    .mc-btn {
      box-shadow:
        inset 2px 2px 0px rgba(255, 255, 255, 0.35),
        inset -2px -3px 0px rgba(0, 0, 0, 0.45),
        0 4px 14px rgba(0, 0, 0, 0.4);
      transition: transform 0.12s ease, filter 0.15s ease;
    }
    .mc-btn:active {
      transform: translateY(2px);
      box-shadow:
        inset 2px 2px 0px rgba(0, 0, 0, 0.4),
        inset -1px -1px 0px rgba(255, 255, 255, 0.2);
    }

    /* Minecraft Grass & Dirt Pixel Divider */
    .mc-grass-divider {
      height: 12px;
      width: 100%;
      background-image:
        linear-gradient(90deg, #10B981 0%, #10B981 25%, #059669 25%, #059669 50%, #34D399 50%, #34D399 75%, #059669 75%, #059669 100%),
        linear-gradient(90deg, #5C3A21 0%, #5C3A21 33%, #4A2E1B 33%, #4A2E1B 66%, #6B4423 66%, #6B4423 100%);
      background-size: 32px 5px, 32px 7px;
      background-position: 0 0, 0 5px;
      background-repeat: repeat-x;
      border-top: 1px solid #6EE7B7;
      border-bottom: 2px solid #29180D;
    }
    
    .pineapple-glow {
      box-shadow: 0 0 30px rgba(250, 204, 21, 0.35);
    }
    
    .pineapple-glow-lg {
      box-shadow: 0 0 55px rgba(250, 204, 21, 0.5);
    }

    .pineapple-text-glow {
      text-shadow: 0 0 24px rgba(250, 204, 21, 0.7);
    }

    /* Ambient background grid */
    .bg-grid-pattern {
      background-image: radial-gradient(rgba(234, 179, 8, 0.16) 1px, transparent 1px),
                        radial-gradient(rgba(16, 185, 129, 0.22) 1px, transparent 1px);
      background-size: 32px 32px;
      background-position: 0 0, 16px 16px;
    }

    @keyframes floating {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-10px); }
    }
    .animate-float {
      animation: floating 4s ease-in-out infinite;
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
      width: 20%;
      height: 200%;
      background: rgba(255, 255, 255, 0.25);
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
      animation: tickerSlide 28s linear infinite;
    }
    .ticker-wrapper:hover {
      animation-play-state: paused;
    }

    /* Custom Scrollbar for Avatar Grid */
    .avatar-scroll::-webkit-scrollbar {
      width: 6px;
    }
    .avatar-scroll::-webkit-scrollbar-track {
      background: rgba(15, 23, 42, 0.6);
      border-radius: 8px;
    }
    .avatar-scroll::-webkit-scrollbar-thumb {
      background: rgba(234, 179, 8, 0.5);
      border-radius: 8px;
    }
  </style>
</head>
<body class="bg-smpDark text-slate-100 min-h-screen relative selection:bg-pineapple-500 selection:text-slate-900">

  <!-- Ambient Grid & Glow Effects -->
  <div class="fixed inset-0 bg-grid-pattern opacity-40 pointer-events-none z-0"></div>
  <div class="fixed top-0 left-1/2 -translate-x-1/2 w-[600px] h-[300px] bg-pineapple-500/15 blur-[130px] rounded-full pointer-events-none z-0"></div>

  <!-- Toast Notification -->
  <div id="toast" class="fixed bottom-6 right-6 z-50 transform translate-y-24 opacity-0 transition-all duration-300 bg-gradient-to-r from-pineapple-500 to-emerald-500 text-slate-950 font-extrabold px-5 py-3 rounded-xl shadow-2xl flex items-center gap-2.5 text-xs sm:text-sm pointer-events-none">
    <i class="fa-solid fa-circle-check text-slate-950 text-base"></i>
    <span id="toast-text">Copied to clipboard!</span>
  </div>

  <!-- TOP RUNNING UPDATE / NEWS BROADCAST TICKER -->
  <div class="relative z-40 bg-gradient-to-r from-amber-950 via-smpCard to-emerald-950 border-b border-pineapple-500/40 py-2 overflow-hidden shadow-md">
    <div class="ticker-wrapper flex items-center gap-10 text-xs font-extrabold tracking-wider uppercase text-pineapple-200">
      <div class="flex items-center gap-10 shrink-0">
        <span class="flex items-center gap-2 text-pineapple-300">
          <span class="w-2 h-2 rounded-full bg-emerald-400 animate-ping"></span>
          🍍 PINEAPPLE SMP — SEASON 1 LAUNCHED! JOIN NOW!
        </span>
        <span class="text-slate-600">|</span>
        <span class="flex items-center gap-2 text-amber-200">
          ⚔️ LIFESTEAL SEASON 1 IS LIVE — GRAB YOUR GEAR!
        </span>
        <span class="text-slate-600">|</span>
        <span class="flex items-center gap-2 text-emerald-300">
          <i class="fa-solid fa-server text-pineapple-400"></i>
          🌐 JAVA: <strong class="font-mono text-white">basic.vitalcloud.in:19126</strong> &bull; BEDROCK PORT: <strong class="font-mono text-pineapple-300">19149</strong>
        </span>
        <span class="text-slate-600">|</span>
        <span class="flex items-center gap-2 text-amber-200">
          <i class="fa-brands fa-discord text-[#5865F2] text-sm"></i>
          💬 DISCORD: <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="underline text-pineapple-300 hover:text-white">discord.gg/Vp9Ss592cq</a>
        </span>
        <span class="text-slate-600">|</span>
      </div>
      <!-- Duplicate track for seamless infinite marquee loop -->
      <div class="flex items-center gap-10 shrink-0" aria-hidden="true">
        <span class="flex items-center gap-2 text-pineapple-300">
          <span class="w-2 h-2 rounded-full bg-emerald-400 animate-ping"></span>
          🍍 PINEAPPLE SMP — SEASON 1 LAUNCHED! JOIN NOW!
        </span>
        <span class="text-slate-600">|</span>
        <span class="flex items-center gap-2 text-amber-200">
          ⚔️ LIFESTEAL SEASON 1 IS LIVE — GRAB YOUR GEAR!
        </span>
        <span class="text-slate-600">|</span>
        <span class="flex items-center gap-2 text-emerald-300">
          <i class="fa-solid fa-server text-pineapple-400"></i>
          🌐 JAVA: <strong class="font-mono text-white">basic.vitalcloud.in:19126</strong> &bull; BEDROCK PORT: <strong class="font-mono text-pineapple-300">19149</strong>
        </span>
        <span class="text-slate-600">|</span>
        <span class="flex items-center gap-2 text-amber-200">
          <i class="fa-brands fa-discord text-[#5865F2] text-sm"></i>
          💬 DISCORD: <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="underline text-pineapple-300 hover:text-white">discord.gg/Vp9Ss592cq</a>
        </span>
        <span class="text-slate-600">|</span>
      </div>
      <!-- Duplicate track for seamless infinite marquee loop -->
      <div class="flex items-center gap-10 shrink-0" aria-hidden="true">
        <span class="flex items-center gap-2 text-pineapple-300">
          <span class="w-2 h-2 rounded-full bg-emerald-400 animate-ping"></span>
          🍍 PINEAPPLE SMP — SEASON 1 LAUNCHED! JOIN NOW!
        </span>
        <span class="text-slate-600">|</span>
        <span class="flex items-center gap-2 text-amber-200">
          ⚔️ LIFESTEAL SEASON 1 IS LIVE — GRAB YOUR GEAR!
        </span>
        <span class="text-slate-600">|</span>
        <span class="flex items-center gap-2 text-emerald-300">
          <i class="fa-solid fa-server text-pineapple-400"></i>
          🌐 IP: <strong class="font-mono text-white">basic.vitalcloud.in</strong> &bull; PORT: <strong class="font-mono text-pineapple-300">19126</strong>
        </span>
        <span class="text-slate-600">|</span>
        <span class="flex items-center gap-2 text-amber-200">
          <i class="fa-brands fa-discord text-[#5865F2] text-sm"></i>
          💬 DISCORD: <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="underline text-pineapple-300 hover:text-white">discord.gg/Vp9Ss592cq</a>
        </span>
        <span class="text-slate-600">|</span>
      </div>
    </div>
  </div>

  <!-- STICKY TOP NAVBAR (BRANDING ON LEFT, LOGIN/AVATAR CIRCLE ON FAR RIGHT) -->
  <header class="sticky top-0 z-30 bg-smpDark/90 backdrop-blur-xl border-b border-smpBorder/80 shadow-lg">
    <div class="w-full max-w-7xl mx-auto px-4 sm:px-6 py-3 flex items-center justify-between gap-4">
      
      <!-- Left: PineappleSMP Brand Logo & Title -->
      <a href="#home" class="flex items-center gap-3 group shrink-0">
        <div class="w-11 h-11 sm:w-12 sm:h-12 rounded-xl border border-pineapple-400/60 bg-gradient-to-br from-amber-950 to-slate-950 p-1 flex items-center justify-center shadow-md shadow-amber-500/20 group-hover:scale-105 transition-transform">
          <!-- Bespoke Inline Vector Logo (Navbar) -->
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 300" class="w-full h-full drop-shadow-[0_2px_6px_rgba(250,204,21,0.5)]">
            <defs>
              <linearGradient id="navPTop" x1="0" y1="0" x2="1" y2="1">
                <stop offset="0%" stop-color="#FEF08A"/>
                <stop offset="100%" stop-color="#FACC15"/>
              </linearGradient>
              <linearGradient id="navPFront" x1="0" y1="0" x2="0" y2="1">
                <stop offset="0%" stop-color="#FACC15"/>
                <stop offset="100%" stop-color="#EA580C"/>
              </linearGradient>
              <linearGradient id="navPSide" x1="0" y1="0" x2="1" y2="1">
                <stop offset="0%" stop-color="#EAB308"/>
                <stop offset="100%" stop-color="#B45309"/>
              </linearGradient>
              <linearGradient id="navLeaf" x1="0" y1="1" x2="0" y2="0">
                <stop offset="0%" stop-color="#047857"/>
                <stop offset="60%" stop-color="#10B981"/>
                <stop offset="100%" stop-color="#6EE7B7"/>
              </linearGradient>
            </defs>
            <!-- Emerald Crown Leaves -->
            <path d="M160 66 C152 30, 145 10, 160 4 C175 10, 168 30, 160 66 Z" fill="url(#navLeaf)" stroke="#064E3B" stroke-width="4"/>
            <path d="M152 68 C130 38, 108 26, 102 38 C114 58, 134 68, 152 74 Z" fill="url(#navLeaf)" stroke="#064E3B" stroke-width="4"/>
            <path d="M168 68 C190 38, 212 26, 218 38 C206 58, 186 68, 168 74 Z" fill="url(#navLeaf)" stroke="#064E3B" stroke-width="4"/>
            <path d="M144 74 C118 58, 94 56, 88 68 C106 80, 128 82, 146 80 Z" fill="#059669" stroke="#064E3B" stroke-width="3.5"/>
            <path d="M176 74 C202 58, 226 56, 232 68 C214 80, 192 82, 174 80 Z" fill="#059669" stroke="#064E3B" stroke-width="3.5"/>
            <!-- 3D Isometric Cube Pineapple -->
            <polygon points="160,64 226,88 160,112 94,88" fill="url(#navPTop)" stroke="#451A03" stroke-width="5" stroke-linejoin="round"/>
            <polygon points="94,88 160,112 160,188 94,162" fill="url(#navPSide)" stroke="#451A03" stroke-width="5" stroke-linejoin="round"/>
            <polygon points="160,112 226,88 226,162 160,188" fill="url(#navPFront)" stroke="#451A03" stroke-width="5" stroke-linejoin="round"/>
            <!-- Crossed Grid Texture -->
            <path d="M104 102 L152 174 M124 108 L156 156 M148 100 L102 154 M126 94 L98 130" stroke="#78350F" stroke-width="3" opacity="0.55"/>
            <path d="M170 118 L218 156 M192 106 L222 132 M214 102 L168 174 M194 108 L164 156" stroke="#9A3412" stroke-width="3" opacity="0.5"/>
            <!-- Cute Pixel Face on Front Face -->
            <rect x="172" y="132" width="11" height="14" rx="2" fill="#1E293B"/>
            <rect x="174" y="134" width="4" height="4" fill="#FFFFFF"/>
            <rect x="204" y="120" width="11" height="14" rx="2" fill="#1E293B"/>
            <rect x="206" y="122" width="4" height="4" fill="#FFFFFF"/>
            <ellipse cx="169" cy="148" rx="5" ry="3" fill="#F43F5E" opacity="0.85"/>
            <ellipse cx="218" cy="133" rx="5" ry="3" fill="#F43F5E" opacity="0.85"/>
            <path d="M187 143 Q194 152 200 140 Z" fill="#881337"/>
            <!-- Bold Emblem Letters & Wooden Signplate -->
            <rect x="46" y="176" width="228" height="54" rx="12" fill="#451A03" stroke="#FDE047" stroke-width="4"/>
            <text x="160" y="213" font-family="'Outfit', sans-serif" font-weight="900" font-size="34" text-anchor="middle" fill="#FACC15" letter-spacing="1.5">PINEAPPLE</text>
            <rect x="96" y="232" width="128" height="44" rx="8" fill="#78350F" stroke="#290F02" stroke-width="5"/>
            <text x="160" y="263" font-family="'Outfit', sans-serif" font-weight="900" font-size="28" text-anchor="middle" fill="#FFFFFF" letter-spacing="3">SMP</text>
          </svg>
        </div>
        <div class="flex flex-col text-left">
          <span class="font-heading font-black text-base sm:text-xl tracking-wide text-white leading-none">
            PINEAPPLE<span class="text-pineapple-400">SMP</span>
          </span>
          <span class="text-[10px] font-bold uppercase tracking-widest text-emerald-400 mt-0.5">
            Lifesteal Network
          </span>
        </div>
      </a>

      <!-- Center Navigation Links (Desktop) -->
      <nav class="hidden lg:flex items-center gap-6 text-xs font-bold uppercase tracking-wider text-slate-300">
        <a href="#home" class="hover:text-pineapple-300 transition-colors">Home</a>
        <a href="#status" class="hover:text-pineapple-300 transition-colors">Status</a>
        <a href="#join-guide" class="hover:text-pineapple-300 transition-colors">How to Join</a>
        <a href="#features" class="hover:text-pineapple-300 transition-colors">Features</a>
      </nav>

      <!-- Far Right: Quick IP, Discord & Circular Login / Profile Avatar Button -->
      <div class="ml-auto flex items-center justify-end gap-2.5 sm:gap-3">
        <button onclick="copyToClipboard('basic.vitalcloud.in:19126', 'Copied Server IP & Port: basic.vitalcloud.in:19126')" title="Click to copy IP & Port" class="hidden md:flex items-center gap-2 bg-smpCard hover:bg-slate-800 text-slate-200 px-3.5 py-2 rounded-lg border border-pineapple-600/60 text-xs font-semibold tracking-wider transition-all hover:border-pineapple-400/80 active:scale-95">
          <span id="nav-status-dot" class="w-2 h-2 rounded-full bg-amber-400 animate-pulse"></span>
          <span>IP: <strong class="text-pineapple-300 font-mono">basic.vitalcloud.in:19126</strong></span>
          <i class="fa-regular fa-copy text-slate-400 text-[11px]"></i>
        </button>

        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="shine-btn bg-gradient-to-r from-[#5865F2] to-indigo-600 hover:from-[#4752c4] hover:to-indigo-500 text-white font-bold px-3.5 py-2 sm:px-4 sm:py-2.5 rounded-lg text-xs sm:text-sm shadow-md shadow-[#5865F2]/30 transition-all flex items-center gap-2">
          <i class="fa-brands fa-discord text-sm"></i>
          <span class="hidden sm:inline">Discord</span>
        </a>

        <!-- Top-Right Circular Login / Profile Avatar Button -->
        <div class="relative shrink-0">
          <button id="nav-profile-btn" onclick="handleProfileCircleClick()" title="Sign Up / Profile" class="w-11 h-11 sm:w-12 sm:h-12 rounded-full border-2 border-pineapple-400/80 bg-gradient-to-br from-slate-900 via-amber-950/60 to-emerald-950/60 hover:border-pineapple-300 hover:scale-105 active:scale-95 transition-all shadow-[0_0_20px_rgba(250,204,21,0.35)] flex items-center justify-center overflow-hidden relative group">
            <!-- Default '?' state when not logged in -->
            <span id="nav-avatar-placeholder" class="font-heading font-black text-xl sm:text-2xl text-pineapple-300 group-hover:text-white transition-colors select-none">?</span>
            <!-- Selected SVG Avatar container when logged in -->
            <div id="nav-avatar-display" class="hidden w-full h-full p-0.5 flex items-center justify-center"></div>
          </button>
          <!-- Status indicator dot on circle -->
          <span id="nav-profile-badge" class="absolute -bottom-0.5 -right-0.5 w-3.5 h-3.5 rounded-full bg-amber-500 border-2 border-smpDark flex items-center justify-center text-[8px] font-bold text-slate-950 pointer-events-none">
            ?
          </span>

          <!-- Logged-In Profile Dropdown Menu -->
          <div id="profile-dropdown" class="hidden absolute right-0 mt-3 w-72 bg-slate-950/95 backdrop-blur-xl border-2 border-pineapple-500/70 rounded-2xl shadow-[0_20px_50px_rgba(0,0,0,0.85)] p-4 z-50 text-left">
            <div class="flex items-center gap-3 pb-3 border-b border-slate-800">
              <div id="dropdown-avatar-preview" class="w-12 h-12 rounded-full border-2 border-emerald-400/80 bg-slate-900 overflow-hidden shrink-0 p-0.5 flex items-center justify-center"></div>
              <div class="overflow-hidden flex-1">
                <div class="flex items-center gap-1.5">
                  <span class="text-[10px] uppercase tracking-wider text-emerald-400 font-bold">Warrior Profile</span>
                  <span id="dropdown-provider-badge" class="hidden text-[9px] bg-white/10 text-white px-1.5 py-0.5 rounded font-semibold">Google</span>
                </div>
                <div id="dropdown-username" class="font-heading font-extrabold text-white text-base truncate">Player</div>
                <div id="dropdown-email" class="text-[11px] text-slate-400 truncate">player@pineapplesmp.net</div>
                <div id="dropdown-avatar-name" class="text-[10px] text-pineapple-300 font-semibold truncate mt-0.5">Avatar</div>
              </div>
            </div>
            <div class="mt-3 space-y-2">
              <button onclick="openAuthModal('profile', true)" class="w-full flex items-center gap-2.5 px-3 py-2.5 rounded-xl bg-slate-900 hover:bg-slate-800 border border-slate-700 hover:border-pineapple-500/60 text-xs font-bold text-slate-200 transition-all">
                <i class="fa-solid fa-masks-theater text-pineapple-400"></i>
                <span>Change Avatar / Edit IGN</span>
              </button>
              <button onclick="logoutUser()" class="w-full flex items-center gap-2.5 px-3 py-2.5 rounded-xl bg-red-950/50 hover:bg-red-900/70 border border-red-800/60 text-xs font-bold text-red-300 transition-all">
                <i class="fa-solid fa-right-from-bracket text-red-400"></i>
                <span>Sign Out</span>
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </header>

  <!-- PROFESSIONAL AUTH MODAL WITH DIRECT GOOGLE SIGN-IN & PROMINENT CROSS (X) BUTTON -->
  <div id="auth-modal" class="fixed inset-0 z-50 hidden items-center justify-center p-3 sm:p-4 bg-black/85 backdrop-blur-md transition-opacity duration-300 overflow-y-auto">
    <div class="relative w-full max-w-lg my-auto mc-panel rounded-3xl border-2 border-pineapple-500/80 shadow-[0_0_70px_rgba(250,204,21,0.35)] overflow-hidden transform transition-all">
      
      <!-- Prominent Top-Right Cross (X) Close Button on the Sign Up Box -->
      <button onclick="dismissAuthModal()" aria-label="Close Sign Up Box" title="Close (Continue as Guest)" class="absolute top-3.5 right-3.5 z-20 w-9 h-9 rounded-full bg-slate-800/95 hover:bg-red-600 text-slate-200 hover:text-white border-2 border-slate-600 hover:border-red-400 flex items-center justify-center transition-all shadow-lg active:scale-90">
        <i class="fa-solid fa-xmark text-lg"></i>
      </button>

      <!-- Modal Header -->
      <div class="bg-gradient-to-r from-amber-950/90 via-slate-900 to-emerald-950/90 px-5 sm:px-6 pt-5 pb-4 border-b border-pineapple-500/40">
        <div class="flex items-center gap-3 pr-9">
          <div class="w-11 h-11 rounded-xl bg-gradient-to-br from-pineapple-500/30 to-emerald-500/30 border border-pineapple-400/60 flex items-center justify-center text-pineapple-300 text-lg shrink-0 shadow-inner">
            <i class="fa-solid fa-shield-halved"></i>
          </div>
          <div>
            <div class="text-[10px] font-pixel text-pineapple-400 tracking-wider uppercase mb-0.5">PineappleSMP Account</div>
            <h3 id="auth-modal-title" class="font-heading font-black text-xl sm:text-2xl text-white tracking-wide leading-tight">
              WARRIOR PORTAL
            </h3>
            <p id="auth-modal-subtitle" class="text-xs text-slate-300">Sign in with Google or create your Minecraft SMP profile!</p>
          </div>
        </div>

        <!-- Mode Switch Tabs (Sign Up / Sign In) -->
        <div id="auth-mode-tabs" class="grid grid-cols-2 gap-2 mt-4 bg-slate-950/95 p-1 rounded-xl border border-slate-800">
          <button type="button" id="tab-signup" onclick="switchAuthTab('signup')" class="py-2 rounded-lg text-xs font-extrabold uppercase tracking-wider transition-all bg-gradient-to-r from-pineapple-500 to-amber-500 text-slate-950 shadow">
            <i class="fa-solid fa-user-plus mr-1"></i> Sign Up
          </button>
          <button type="button" id="tab-login" onclick="switchAuthTab('login')" class="py-2 rounded-lg text-xs font-extrabold uppercase tracking-wider transition-all text-slate-400 hover:text-white">
            <i class="fa-solid fa-right-to-bracket mr-1"></i> Sign In
          </button>
        </div>
      </div>

      <!-- Modal Body -->
      <div class="p-5 sm:p-6 space-y-4 max-h-[82vh] overflow-y-auto avatar-scroll">
        
        <!-- DIRECT CONTINUE WITH GOOGLE BUTTON -->
        <div id="google-auth-wrapper">
          <button type="button" id="google-signin-btn" onclick="handleGoogleSignIn()" class="w-full bg-white hover:bg-slate-100 active:bg-slate-200 text-slate-900 font-extrabold py-3 px-4 rounded-xl text-xs sm:text-sm shadow-lg border border-slate-300 transition-all flex items-center justify-center gap-3 group">
            <!-- Official Google G SVG -->
            <svg class="w-5 h-5 shrink-0" viewBox="0 0 24 24">
              <path fill="#4285F4" d="M23.745 12.27c0-.7-.06-1.4-.19-2.07H12v4.51h6.6c-.29 1.52-1.14 2.82-2.4 3.68v3.05h3.88c2.27-2.09 3.665-5.17 3.665-9.17z"/>
              <path fill="#34A853" d="M12 24c3.24 0 5.95-1.08 7.93-2.91l-3.88-3.05c-1.08.72-2.45 1.16-4.05 1.16-3.12 0-5.77-2.11-6.72-4.96H1.29v3.14C3.26 21.3 7.31 24 12 24z"/>
              <path fill="#FBBC05" d="M5.28 14.24c-.24-.72-.38-1.49-.38-2.24s.14-1.52.38-2.24V6.62H1.29C.47 8.24 0 10.06 0 12s.47 3.76 1.29 5.38l3.99-3.14z"/>
              <path fill="#EA4335" d="M12 4.75c1.77 0 3.35.61 4.6 1.8l3.42-3.42C17.95 1.19 15.24 0 12 0 7.31 0 3.26 2.7 1.29 6.62l3.99 3.14c.95-2.85 3.6-4.96 6.72-4.96z"/>
            </svg>
            <span id="google-btn-text">Continue with Google</span>
          </button>

          <div class="relative flex py-3 items-center">
            <div class="flex-grow border-t border-slate-700/80"></div>
            <span class="flex-shrink mx-3 text-[10px] font-bold uppercase tracking-widest text-slate-400">OR WITH EMAIL &amp; IGN</span>
            <div class="flex-grow border-t border-slate-700/80"></div>
          </div>
        </div>

        <!-- Email / Password + IGN + Avatar Form -->
        <form id="auth-form" onsubmit="handleAuthSubmit(event)" class="space-y-3.5">
          
          <!-- Minecraft IGN Input -->
          <div id="ign-field-wrapper">
            <label for="auth-username" class="block text-xs font-bold uppercase tracking-wider text-pineapple-300 mb-1">
              Minecraft Username (IGN)
            </label>
            <div class="relative">
              <span class="absolute inset-y-0 left-0 pl-3.5 flex items-center text-slate-400">
                <i class="fa-solid fa-cube text-emerald-400"></i>
              </span>
              <input type="text" id="auth-username" minlength="2" maxlength="20" placeholder="e.g. PineappleKing" class="w-full bg-slate-950 border border-slate-700 focus:border-pineapple-400 rounded-xl pl-10 pr-4 py-2.5 text-sm text-white placeholder-slate-500 outline-none transition-colors font-mono">
            </div>
          </div>

          <!-- Email Input -->
          <div id="email-field-wrapper">
            <label for="auth-email" class="block text-xs font-bold uppercase tracking-wider text-pineapple-300 mb-1">
              Gmail / Email Address
            </label>
            <div class="relative">
              <span class="absolute inset-y-0 left-0 pl-3.5 flex items-center text-slate-400">
                <i class="fa-solid fa-envelope text-sky-400"></i>
              </span>
              <input type="email" id="auth-email" placeholder="warrior@gmail.com" class="w-full bg-slate-950 border border-slate-700 focus:border-pineapple-400 rounded-xl pl-10 pr-4 py-2.5 text-sm text-white placeholder-slate-500 outline-none transition-colors">
            </div>
          </div>

          <!-- Password Input -->
          <div id="password-field-wrapper">
            <label for="auth-password" class="block text-xs font-bold uppercase tracking-wider text-pineapple-300 mb-1">
              Password
            </label>
            <div class="relative">
              <span class="absolute inset-y-0 left-0 pl-3.5 flex items-center text-slate-400">
                <i class="fa-solid fa-lock text-amber-400"></i>
              </span>
              <input type="password" id="auth-password" minlength="6" placeholder="Min. 6 characters" class="w-full bg-slate-950 border border-slate-700 focus:border-pineapple-400 rounded-xl pl-10 pr-4 py-2.5 text-sm text-white placeholder-slate-500 outline-none transition-colors">
            </div>
          </div>

          <!-- 16 Custom Vector Avatars Selector (Minecraft Characters & Animals + Optional Google Photo) -->
          <div id="avatar-selector-section">
            <div class="flex items-center justify-between mb-1.5">
              <label class="text-xs font-bold uppercase tracking-wider text-emerald-400 flex items-center gap-1.5">
                <i class="fa-solid fa-paw"></i> Choose Avatar (Characters &amp; Animals)
              </label>
              <span id="selected-avatar-label" class="text-[11px] font-mono bg-pineapple-500/20 text-pineapple-300 border border-pineapple-500/40 px-2 py-0.5 rounded-md">
                Steve
              </span>
            </div>

            <div id="avatar-grid" class="grid grid-cols-4 gap-2 max-h-44 overflow-y-auto p-2 bg-slate-950/95 border border-slate-800 rounded-2xl avatar-scroll">
              <!-- Populated dynamically via JS with 16 custom SVG avatars + Google Photo option if signed in -->
            </div>
          </div>

          <!-- Error Message Box -->
          <div id="auth-error-msg" class="hidden text-xs font-semibold text-red-300 bg-red-950/70 border border-red-700/70 px-3.5 py-2.5 rounded-xl flex items-start gap-2">
            <i class="fa-solid fa-triangle-exclamation text-red-400 mt-0.5"></i>
            <span id="auth-error-text">Error message</span>
          </div>

          <!-- Submit & Continue as Guest Actions -->
          <div class="pt-1 flex flex-col sm:flex-row gap-2.5">
            <button type="submit" id="auth-submit-btn" class="mc-btn shine-btn flex-1 bg-gradient-to-r from-pineapple-500 via-amber-500 to-emerald-500 hover:from-pineapple-400 hover:to-emerald-400 text-slate-950 font-black py-3 px-4 rounded-xl text-xs sm:text-sm uppercase tracking-wider flex items-center justify-center gap-2">
              <i class="fa-solid fa-check-circle"></i>
              <span id="auth-submit-text">Create Account &amp; Save</span>
            </button>
            <button type="button" onclick="dismissAuthModal()" class="bg-slate-800 hover:bg-slate-700 text-slate-300 font-semibold py-3 px-4 rounded-xl text-xs border border-slate-700 transition-colors">
              Continue as Guest
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>

  <main class="relative z-10">

    <!-- Hero Section -->
    <section id="home" class="pt-8 pb-12 md:pt-14 md:pb-20 max-w-6xl mx-auto px-4 text-center">
      
      <!-- Bespoke Hand-Crafted PineappleSMP Vector Crest -->
      <div class="relative flex justify-center mb-6">
        <div class="relative w-64 h-64 sm:w-72 sm:h-72 md:w-84 md:h-84 animate-float flex items-center justify-center">
          <div class="absolute inset-0 bg-pineapple-500/25 blur-3xl rounded-full scale-95 pointer-events-none"></div>
          
          <div id="hero-logo-box" class="relative w-full h-full rounded-3xl p-3 sm:p-4 bg-gradient-to-br from-amber-950/60 via-slate-950/90 to-emerald-950/70 border-2 border-pineapple-400/60 shadow-[0_0_55px_rgba(250,204,21,0.45)] flex items-center justify-center overflow-hidden backdrop-blur-md">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 380 340" class="w-full h-full filter drop-shadow-[0_12px_24px_rgba(0,0,0,0.75)]">
              <defs>
                <!-- Pineapple Isometric Cube Gradients -->
                <linearGradient id="heroPTop" x1="0" y1="0" x2="1" y2="1">
                  <stop offset="0%" stop-color="#FEF9C3"/>
                  <stop offset="55%" stop-color="#FDE047"/>
                  <stop offset="100%" stop-color="#FACC15"/>
                </linearGradient>
                <linearGradient id="heroPFront" x1="0" y1="0" x2="0" y2="1">
                  <stop offset="0%" stop-color="#FACC15"/>
                  <stop offset="50%" stop-color="#F59E0B"/>
                  <stop offset="100%" stop-color="#D97706"/>
                </linearGradient>
                <linearGradient id="heroPSide" x1="0" y1="0" x2="1" y2="1">
                  <stop offset="0%" stop-color="#EAB308"/>
                  <stop offset="100%" stop-color="#B45309"/>
                </linearGradient>
                <!-- Emerald Crown Leaves Gradients -->
                <linearGradient id="heroLeafMain" x1="0" y1="1" x2="0" y2="0">
                  <stop offset="0%" stop-color="#047857"/>
                  <stop offset="55%" stop-color="#10B981"/>
                  <stop offset="100%" stop-color="#6EE7B7"/>
                </linearGradient>
                <linearGradient id="heroLeafDark" x1="0" y1="1" x2="0" y2="0">
                  <stop offset="0%" stop-color="#064E3B"/>
                  <stop offset="100%" stop-color="#059669"/>
                </linearGradient>
                <!-- Beveled Typography & Wood Plank Gradients -->
                <linearGradient id="heroGoldText" x1="0" y1="0" x2="0" y2="1">
                  <stop offset="0%" stop-color="#FEF9C3"/>
                  <stop offset="30%" stop-color="#FDE047"/>
                  <stop offset="70%" stop-color="#F59E0B"/>
                  <stop offset="100%" stop-color="#EA580C"/>
                </linearGradient>
                <linearGradient id="heroWoodPlank" x1="0" y1="0" x2="0" y2="1">
                  <stop offset="0%" stop-color="#92400E"/>
                  <stop offset="50%" stop-color="#78350F"/>
                  <stop offset="100%" stop-color="#451A03"/>
                </linearGradient>
              </defs>

              <!-- Ambient Radial Aura behind Mascot -->
              <circle cx="190" cy="145" r="115" fill="#FACC15" opacity="0.12"/>
              <circle cx="190" cy="145" r="85" fill="#10B981" opacity="0.1"/>

              <!-- Back Crown Leaves -->
              <path d="M174 78 C154 42, 134 24, 122 34 C132 54, 150 70, 170 82 Z" fill="url(#heroLeafDark)" stroke="#022C22" stroke-width="4" stroke-linejoin="round"/>
              <path d="M206 78 C226 42, 246 24, 258 34 C248 54, 230 70, 210 82 Z" fill="url(#heroLeafDark)" stroke="#022C22" stroke-width="4" stroke-linejoin="round"/>

              <!-- Front Layered Crown Leaves -->
              <path d="M190 74 C180 34, 174 10, 190 4 C206 10, 200 34, 190 74 Z" fill="url(#heroLeafMain)" stroke="#022C22" stroke-width="4.5" stroke-linejoin="round"/>
              <path d="M180 78 C156 46, 130 36, 120 48 C134 66, 158 76, 178 82 Z" fill="url(#heroLeafMain)" stroke="#022C22" stroke-width="4.5" stroke-linejoin="round"/>
              <path d="M200 78 C224 46, 250 36, 260 48 C246 66, 222 76, 202 82 Z" fill="url(#heroLeafMain)" stroke="#022C22" stroke-width="4.5" stroke-linejoin="round"/>
              <path d="M170 84 C140 68, 112 68, 104 80 C124 92, 148 92, 170 88 Z" fill="url(#heroLeafMain)" stroke="#022C22" stroke-width="4" stroke-linejoin="round"/>
              <path d="M210 84 C240 68, 268 68, 276 80 C256 92, 232 92, 210 88 Z" fill="url(#heroLeafMain)" stroke="#022C22" stroke-width="4" stroke-linejoin="round"/>

              <!-- 3D Isometric Minecraft Cube Pineapple Body -->
              <!-- Top Diamond Face -->
              <polygon points="190,68 264,96 190,124 116,96" fill="url(#heroPTop)" stroke="#451A03" stroke-width="5.5" stroke-linejoin="round"/>
              <!-- Left Shaded Face -->
              <polygon points="116,96 190,124 190,206 116,178" fill="url(#heroPSide)" stroke="#451A03" stroke-width="5.5" stroke-linejoin="round"/>
              <!-- Right Front Face -->
              <polygon points="190,124 264,96 264,178 190,206" fill="url(#heroPFront)" stroke="#451A03" stroke-width="5.5" stroke-linejoin="round"/>

              <!-- Crossed Golden-Amber Grid Texture (Top Face) -->
              <path d="M153 82 L227 110 M227 82 L153 110" stroke="#CA8A04" stroke-width="3" opacity="0.55"/>
              <!-- Crossed Grid Texture (Left Side Face) -->
              <path d="M126 112 L180 192 M148 118 L186 174 M176 122 L124 170 M152 112 L120 144" stroke="#78350F" stroke-width="3.2" opacity="0.5"/>
              <!-- Crossed Grid Texture (Right Front Face) -->
              <path d="M200 132 L254 172 M224 116 L260 146 M252 112 L198 192 M228 118 L194 172" stroke="#9A3412" stroke-width="3" opacity="0.42"/>

              <!-- Cute Pixel Eyes, Blush & Happy Expression -->
              <!-- Left Eye -->
              <rect x="203" y="146" width="12" height="16" rx="2.5" fill="#1E293B"/>
              <rect x="205" y="148" width="4.5" height="4.5" rx="1" fill="#FFFFFF"/>
              <rect x="210" y="156" width="2.5" height="2.5" fill="#FDE047"/>
              <!-- Right Eye -->
              <rect x="239" y="132" width="12" height="16" rx="2.5" fill="#1E293B"/>
              <rect x="241" y="134" width="4.5" height="4.5" rx="1" fill="#FFFFFF"/>
              <rect x="246" y="142" width="2.5" height="2.5" fill="#FDE047"/>
              <!-- Rosy Cheeks -->
              <ellipse cx="200" cy="164" rx="6" ry="3.5" fill="#FB7185" opacity="0.85"/>
              <ellipse cx="255" cy="147" rx="6" ry="3.5" fill="#FB7185" opacity="0.85"/>
              <!-- Happy Open Mouth & Tongue -->
              <path d="M220 157 Q228 168 235 153 Z" fill="#881337" stroke="#451A03" stroke-width="1.5"/>
              <path d="M223 160 Q228 165 232 158 Z" fill="#F43F5E"/>

              <!-- Floating Golden Pineapple Chunks -->
              <!-- Left Top Chunk -->
              <g transform="translate(56, 98) rotate(-18)">
                <path d="M4 14 Q16 0 28 14 L22 24 Q16 17 10 24 Z" fill="#FDE047" stroke="#451A03" stroke-width="3.5" stroke-linejoin="round"/>
                <path d="M10 14 Q16 8 22 14" stroke="#EA580C" stroke-width="2" fill="none"/>
              </g>
              <!-- Left Bottom Chunk -->
              <g transform="translate(46, 152) rotate(-32)">
                <rect x="0" y="0" width="22" height="16" rx="4" fill="#FACC15" stroke="#451A03" stroke-width="3.5"/>
                <line x1="5" y1="5" x2="17" y2="11" stroke="#B45309" stroke-width="2"/>
              </g>
              <!-- Right Top Chunk -->
              <g transform="translate(296, 92) rotate(22)">
                <path d="M4 14 Q16 0 28 14 L22 24 Q16 17 10 24 Z" fill="#FDE047" stroke="#451A03" stroke-width="3.5" stroke-linejoin="round"/>
                <path d="M10 14 Q16 8 22 14" stroke="#EA580C" stroke-width="2" fill="none"/>
              </g>
              <!-- Right Bottom Chunk -->
              <g transform="translate(304, 148) rotate(28)">
                <rect x="0" y="0" width="22" height="16" rx="4" fill="#FACC15" stroke="#451A03" stroke-width="3.5"/>
                <line x1="5" y1="11" x2="17" y2="5" stroke="#B45309" stroke-width="2"/>
              </g>

              <!-- Pixel Sparkles & Plus Glints -->
              <polygon points="82,66 85,73 92,76 85,79 82,86 79,79 72,76 79,73" fill="#FEF08A"/>
              <polygon points="300,64 303,71 310,74 303,77 300,84 297,77 290,74 297,71" fill="#FEF08A"/>
              <rect x="92" y="130" width="6" height="6" rx="1" fill="#34D399"/>
              <rect x="284" y="128" width="6" height="6" rx="1" fill="#FDE047"/>
              <rect x="64" y="132" width="4" height="4" fill="#FACC15"/>
              <rect x="316" y="124" width="4" height="4" fill="#34D399"/>

              <!-- Bold 3D Beveled 'PINEAPPLE' Typography -->
              <g filter="drop-shadow(0px 8px 6px rgba(0,0,0,0.85))">
                <!-- Deep Dark Brown 3D Extrusion Base -->
                <text x="190" y="255" font-family="'Outfit', 'Impact', sans-serif" font-weight="900" font-size="52" text-anchor="middle" fill="#290F02" stroke="#290F02" stroke-width="16" stroke-linejoin="round" letter-spacing="2">PINEAPPLE</text>
                <!-- Mid Amber-Brown Bevel -->
                <text x="190" y="250" font-family="'Outfit', 'Impact', sans-serif" font-weight="900" font-size="52" text-anchor="middle" fill="#78350F" stroke="#5A2508" stroke-width="9" stroke-linejoin="round" letter-spacing="2">PINEAPPLE</text>
                <!-- Bright Golden-Orange Front Face -->
                <text x="190" y="246" font-family="'Outfit', 'Impact', sans-serif" font-weight="900" font-size="52" text-anchor="middle" fill="url(#heroGoldText)" letter-spacing="2">PINEAPPLE</text>
              </g>

              <!-- Detailed Wooden Plank Signplate Reading 'SMP' -->
              <g filter="drop-shadow(0px 6px 8px rgba(0,0,0,0.75))">
                <!-- Outer Dark Wood Frame -->
                <rect x="106" y="268" width="168" height="54" rx="10" fill="#290F02" stroke="#1C0A01" stroke-width="4"/>
                <!-- Main Wood Plank Surface -->
                <rect x="111" y="272" width="158" height="46" rx="7" fill="url(#heroWoodPlank)" stroke="#B45309" stroke-width="2"/>
                <!-- Wood Grain Plank Seams & Notches -->
                <line x1="114" y1="295" x2="266" y2="295" stroke="#451A03" stroke-width="2.5"/>
                <path d="M135 273 L142 281 M238 317 L231 309 M112 286 L122 286 M268 304 L257 304" stroke="#451A03" stroke-width="2.5" stroke-linecap="round"/>
                <!-- Corner Iron Rivets -->
                <circle cx="121" cy="282" r="3" fill="#CBD5E1" stroke="#334155" stroke-width="1"/>
                <circle cx="259" cy="282" r="3" fill="#CBD5E1" stroke="#334155" stroke-width="1"/>
                <circle cx="121" cy="308" r="3" fill="#CBD5E1" stroke="#334155" stroke-width="1"/>
                <circle cx="259" cy="308" r="3" fill="#CBD5E1" stroke="#334155" stroke-width="1"/>
                <!-- Crisp Blocky White Minecraft 'SMP' Text -->
                <text x="190" y="305" font-family="'Press Start 2P', 'Outfit', monospace" font-weight="900" font-size="25" text-anchor="middle" fill="#290F02" letter-spacing="4">SMP</text>
                <text x="190" y="302" font-family="'Press Start 2P', 'Outfit', monospace" font-weight="900" font-size="25" text-anchor="middle" fill="#FFFFFF" letter-spacing="4">SMP</text>
              </g>
            </svg>
          </div>
        </div>
      </div>

      <!-- Hero Headlines -->
      <div class="inline-flex items-center gap-2 bg-gradient-to-r from-amber-500/20 to-emerald-500/20 border border-pineapple-500/50 px-5 py-2 rounded-full text-pineapple-300 text-xs sm:text-sm font-black uppercase tracking-widest mb-5 shadow-[0_0_20px_rgba(250,204,21,0.3)]">
        <i class="fa-solid fa-cube text-emerald-400"></i> BEDROCK (POCKET / CONSOLE / WIN10) + JAVA CROSSPLAY
      </div>

      <h1 class="text-4xl sm:text-6xl md:text-7xl font-extrabold font-heading text-white tracking-tight uppercase pineapple-text-glow leading-none">
        PINEAPPLE SMP <br/>
        <span class="text-transparent bg-clip-text bg-gradient-to-r from-pineapple-300 via-amber-300 to-emerald-400">SEASON 1 LAUNCHED</span>
      </h1>
      
      <p class="mt-5 text-slate-300 max-w-2xl mx-auto text-base sm:text-lg leading-relaxed font-normal">
        Season 1 Launched — Join Now! Jump into the ultimate Minecraft Lifesteal SMP adventure with Bedrock &amp; Java crossplay.
      </p>

      <!-- Quick Join Buttons -->
      <div class="mt-8 flex flex-wrap justify-center gap-4">
        <button onclick="copyToClipboard('basic.vitalcloud.in', 'Copied Server IP: basic.vitalcloud.in')" class="mc-btn shine-btn bg-gradient-to-r from-pineapple-500 via-amber-500 to-emerald-500 hover:from-pineapple-400 hover:to-emerald-400 text-slate-950 font-black px-6 py-3.5 rounded-xl text-sm flex items-center gap-2">
          <i class="fa-solid fa-copy text-base"></i>
          <span>IP: <span class="font-mono">basic.vitalcloud.in</span></span>
        </button>
        <button onclick="copyToClipboard('19149', 'Copied Bedrock Port: 19149')" class="mc-btn shine-btn bg-slate-800 hover:bg-slate-700 text-pineapple-300 border border-pineapple-500/60 font-bold px-6 py-3.5 rounded-xl text-sm flex items-center gap-2">
          <i class="fa-solid fa-plug text-sm text-emerald-400"></i>
          <span>Bedrock Port: <span class="font-mono text-white">19149</span></span>
        </button>
        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="mc-btn shine-btn bg-[#5865F2] hover:bg-[#4752c4] text-white font-extrabold px-6 py-3.5 rounded-xl text-sm flex items-center gap-2">
          <i class="fa-brands fa-discord text-lg"></i>
          <span>Join Discord</span>
        </a>
      </div>

      <!-- Server Status Bar -->
      <div id="status" class="mt-12 max-w-4xl mx-auto">
        <div class="flex items-center justify-between px-2 mb-2.5">
          <div class="flex items-center gap-2 text-xs text-slate-400">
            <span id="telemetry-dot" class="inline-block w-2 h-2 rounded-full bg-amber-400 animate-pulse"></span>
            <span>Live Telemetry (<span class="font-mono text-pineapple-300">Java :19126 | Bedrock :19149</span>)</span>
            <span id="last-updated-text" class="text-[11px] text-slate-500 font-mono">(Connecting...)</span>
          </div>
          <button id="refresh-status-btn" onclick="fetchLiveServerStatus()" class="flex items-center gap-1.5 bg-slate-800/90 hover:bg-slate-700 text-pineapple-300 hover:text-white text-xs font-semibold px-3 py-1.5 rounded-lg border border-pineapple-700/60 transition-all hover:border-pineapple-400/80 shadow-sm active:scale-95">
            <i id="refresh-icon" class="fa-solid fa-arrows-rotate text-[11px]"></i>
            <span>Refresh Status</span>
          </button>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4 text-left">
          
          <!-- Server Status Card -->
          <div class="mc-panel p-4 rounded-xl relative overflow-hidden group">
            <div class="text-xs text-slate-400 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Server Status</span>
              <span id="ping-latency-badge" class="text-[10px] bg-slate-800 px-2 py-0.5 rounded text-amber-300 font-mono">PINGING</span>
            </div>
            <div id="server-status-badge" class="font-bold flex items-center gap-2 text-base mt-1.5 text-amber-400">
              <span id="server-status-dot" class="w-2.5 h-2.5 rounded-full bg-amber-400 shadow-[0_0_10px_#f59e0b] animate-pulse"></span>
              <span id="server-status-text">Checking...</span>
            </div>
            <div id="server-version-text" class="text-[10px] text-slate-400 mt-1 font-mono truncate">Bedrock 1.20 - 1.21+ / Java</div>

            <!-- Stylized Callout Badge -->
            <div class="mt-3 pt-2.5 border-t border-slate-800/80 text-center">
              <div class="inline-block py-1 px-3 rounded-lg bg-gradient-to-r from-amber-600/30 via-pineapple-500/30 to-emerald-600/30 border border-pineapple-400/50 shadow-inner">
                <span id="status-callout-title" class="font-heading font-black text-xs sm:text-sm tracking-widest text-transparent bg-clip-text bg-gradient-to-r from-pineapple-200 via-amber-300 to-emerald-200 animate-pulse drop-shadow-[0_0_8px_rgba(250,204,21,0.8)]">
                  basic.vitalcloud.in
                </span>
              </div>
              <div id="status-callout-sub" class="text-[10px] font-bold text-emerald-400 mt-1 uppercase tracking-wider flex items-center justify-center gap-1">
                <span>⚔️ Java: 19126 | Bedrock: 19149 ⚔️</span>
              </div>
            </div>
          </div>

          <!-- Players Online Tracker -->
          <div class="mc-panel p-4 rounded-xl relative overflow-hidden group">
            <div class="text-xs text-slate-400 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Players Online</span>
              <i class="fa-solid fa-users text-pineapple-400 text-xs"></i>
            </div>
            <div class="flex items-baseline gap-1.5 mt-1">
              <span id="server-players-online" class="text-2xl font-black font-mono text-white tracking-tight">0</span>
              <span id="server-players-max" class="text-xs text-slate-500 font-mono">/ 50</span>
            </div>
            <div class="text-[10px] text-amber-300 font-medium mt-0.5 flex items-center gap-1">
              <span id="players-pulse-dot" class="w-1.5 h-1.5 rounded-full bg-amber-400 animate-pulse"></span>
              <span id="server-players-status">Querying live server...</span>
            </div>

            <!-- In-Card Username Roster -->
            <div class="mt-2.5 pt-2.5 border-t border-slate-800/80">
              <div class="text-[10px] uppercase font-bold text-slate-400 flex items-center justify-between mb-1.5">
                <span>Active Roster:</span>
                <span id="roster-count-tag" class="font-mono text-pineapple-300 text-[9px] bg-slate-900 px-1.5 py-0.5 rounded">LIVE</span>
              </div>
              <div id="card-players-list" class="flex flex-wrap gap-1.5 max-h-24 overflow-y-auto pr-1">
                <span class="text-[11px] text-slate-400 italic">Checking active players...</span>
              </div>
            </div>
          </div>

          <!-- SMP Mode Card -->
          <div class="mc-panel p-4 rounded-xl relative overflow-hidden">
            <div class="text-xs text-slate-400 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Game Mode</span>
              <i class="fa-solid fa-heart text-red-500 text-xs"></i>
            </div>
            <div class="text-white font-bold text-base mt-1.5 flex items-center gap-1.5">
              <span class="text-red-500">❤️</span> Lifesteal SMP
            </div>
            <div class="text-[10px] text-slate-400 mt-1">Kill = +1 Heart | Death = -1 Heart</div>
          </div>

          <!-- Crossplay Info Card -->
          <div onclick="copyToClipboard('19149', 'Copied Bedrock Port: 19149')" class="mc-panel p-4 rounded-xl relative overflow-hidden cursor-pointer group">
            <div class="text-xs text-slate-400 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Bedrock Port</span>
              <i class="fa-regular fa-copy text-emerald-400 text-xs group-hover:scale-110 transition-transform"></i>
            </div>
            <div class="text-pineapple-300 font-mono font-bold text-base mt-1.5">19149</div>
            <div class="text-[10px] text-emerald-400 mt-1 font-mono truncate">basic.vitalcloud.in</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Minecraft Grass & Dirt Pixel Divider -->
    <div class="mc-grass-divider my-2"></div>

    <!-- STEP-BY-STEP HOW TO JOIN (BEDROCK & JAVA) -->
    <section id="join-guide" class="py-14 max-w-5xl mx-auto px-4 sm:px-6">
      <div class="text-center mb-10">
        <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-emerald-500/10 border border-emerald-500/30 text-emerald-300 text-xs font-bold uppercase tracking-widest mb-3">
          <i class="fa-solid fa-gamepad"></i> Easy 1-Minute Setup
        </div>
        <h2 class="text-3xl sm:text-4xl font-heading font-black text-white">HOW TO JOIN PINEAPPLE SMP</h2>
        <p class="text-slate-400 text-sm mt-1">Supported on Phone (Pocket Edition), Console (Xbox, PS, Switch), Windows 10/11 & PC Java!</p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
        
        <!-- Bedrock Connection Card (Highlighted) -->
        <div class="bg-gradient-to-br from-amber-950/40 via-smpCard to-emerald-950/30 border-2 border-pineapple-500/80 p-6 rounded-2xl relative overflow-hidden shadow-xl">
          <div class="flex items-center justify-between mb-4">
            <span class="text-xs uppercase font-extrabold px-3 py-1 bg-gradient-to-r from-pineapple-500 to-amber-500 text-slate-950 rounded-lg shadow">
              📱 Bedrock / Pocket Edition
            </span>
            <span class="text-xs text-emerald-400 font-bold">Recommended</span>
          </div>

          <div class="space-y-3.5 text-xs text-slate-300">
            <div class="flex items-start gap-2.5">
              <span class="w-5 h-5 rounded-full bg-pineapple-500/20 text-pineapple-300 font-bold flex items-center justify-center shrink-0 border border-pineapple-500/40">1</span>
              <span>Open Minecraft on your phone, console, or Windows 10/11 PC.</span>
            </div>
            <div class="flex items-start gap-2.5">
              <span class="w-5 h-5 rounded-full bg-pineapple-500/20 text-pineapple-300 font-bold flex items-center justify-center shrink-0 border border-pineapple-500/40">2</span>
              <span>Tap <strong>Play</strong> &rarr; Click the <strong>Servers</strong> tab &rarr; Scroll down and tap <strong>Add Server</strong>.</span>
            </div>
            <div class="flex items-start gap-2.5">
              <span class="w-5 h-5 rounded-full bg-pineapple-500/20 text-pineapple-300 font-bold flex items-center justify-center shrink-0 border border-pineapple-500/40">3</span>
              <div class="flex-1">
                Enter the exact Bedrock server details below:
              </div>
            </div>
          </div>

          <!-- Bedrock Server Details Field Box -->
          <div class="mt-4 bg-slate-950/90 border border-pineapple-500/40 rounded-xl p-3.5 space-y-2.5 text-xs">
            <div class="flex items-center justify-between">
              <span class="text-slate-400 font-semibold">Server Name:</span>
              <span class="text-white font-bold font-mono">PineappleSMP</span>
            </div>
            <div class="flex items-center justify-between border-t border-slate-800/80 pt-2">
              <span class="text-slate-400 font-semibold">Server Address:</span>
              <div class="flex items-center gap-2">
                <span class="text-pineapple-300 font-mono font-bold">basic.vitalcloud.in</span>
                <button onclick="copyToClipboard('basic.vitalcloud.in', 'Copied Bedrock IP: basic.vitalcloud.in')" class="text-slate-400 hover:text-white" title="Copy IP">
                  <i class="fa-regular fa-copy"></i>
                </button>
              </div>
            </div>
            <div class="flex items-center justify-between border-t border-slate-800/80 pt-2">
              <span class="text-slate-400 font-semibold">Port:</span>
              <div class="flex items-center gap-2">
                <span class="text-emerald-400 font-mono font-extrabold text-sm">19149</span>
                <button onclick="copyToClipboard('19149', 'Copied Bedrock Port: 19149')" class="text-slate-400 hover:text-white" title="Copy Port">
                  <i class="fa-regular fa-copy"></i>
                </button>
              </div>
            </div>
          </div>

          <div class="mt-4 flex gap-2">
            <button onclick="copyToClipboard('basic.vitalcloud.in', 'Copied Bedrock IP: basic.vitalcloud.in')" class="flex-1 bg-gradient-to-r from-pineapple-500 to-amber-500 hover:from-pineapple-400 hover:to-amber-400 text-slate-950 font-black py-2.5 px-3 rounded-xl text-xs transition-all flex items-center justify-center gap-1.5 shadow-md">
              <i class="fa-regular fa-copy"></i>
              <span>Copy Bedrock IP</span>
            </button>
            <button onclick="copyToClipboard('19149', 'Copied Bedrock Port: 19149')" class="flex-1 bg-emerald-600 hover:bg-emerald-500 text-white font-black py-2.5 px-3 rounded-xl text-xs transition-all flex items-center justify-center gap-1.5 shadow-md">
              <i class="fa-solid fa-plug"></i>
              <span>Copy Port (19149)</span>
            </button>
          </div>
        </div>

        <!-- Java Connection Card -->
        <div class="mc-panel p-6 rounded-2xl relative overflow-hidden flex flex-col justify-between">
          <div>
            <div class="flex items-center justify-between mb-4">
              <span class="text-xs uppercase font-extrabold px-3 py-1 bg-slate-800 text-slate-300 border border-slate-700 rounded-lg">
                💻 Java Edition (PC)
              </span>
              <span class="text-xs text-slate-400">1.19 - 1.21+</span>
            </div>

            <div class="space-y-3.5 text-xs text-slate-300">
              <div class="flex items-start gap-2.5">
                <span class="w-5 h-5 rounded-full bg-slate-800 text-slate-300 font-bold flex items-center justify-center shrink-0 border border-slate-700">1</span>
                <span>Launch Minecraft Java Edition.</span>
              </div>
              <div class="flex items-start gap-2.5">
                <span class="w-5 h-5 rounded-full bg-slate-800 text-slate-300 font-bold flex items-center justify-center shrink-0 border border-slate-700">2</span>
                <span>Click <strong>Multiplayer</strong> &rarr; Click <strong>Direct Connection</strong> or <strong>Add Server</strong>.</span>
              </div>
              <div class="flex items-start gap-2.5">
                <span class="w-5 h-5 rounded-full bg-slate-800 text-slate-300 font-bold flex items-center justify-center shrink-0 border border-slate-700">3</span>
                <span>Enter the Server Address below to connect:</span>
              </div>
            </div>

            <!-- Java Server Address Box -->
            <div class="mt-4 bg-slate-950/90 border border-slate-800 rounded-xl p-3.5 space-y-2 text-xs">
              <div class="text-slate-400 uppercase font-semibold text-[10px]">Server Address:</div>
              <div class="flex items-center justify-between">
                <span class="font-mono font-bold text-pineapple-300 text-sm">basic.vitalcloud.in:19126</span>
                <button onclick="copyToClipboard('basic.vitalcloud.in:19126', 'Copied Java IP: basic.vitalcloud.in:19126')" class="text-slate-400 hover:text-white" title="Copy Address">
                  <i class="fa-regular fa-copy"></i>
                </button>
              </div>
            </div>
          </div>

          <div class="mt-4">
            <button onclick="copyToClipboard('basic.vitalcloud.in:19126', 'Copied Java Address: basic.vitalcloud.in:19126')" class="w-full bg-slate-800 hover:bg-slate-700 text-slate-200 border border-slate-700 font-bold py-2.5 px-4 rounded-xl text-xs transition-all flex items-center justify-center gap-2">
              <i class="fa-regular fa-copy text-pineapple-400"></i>
              <span>Copy Java IP &amp; Port</span>
            </button>
          </div>
        </div>

      </div>
    </section>

    <!-- SERVER FEATURES SECTION -->
    <section id="features" class="py-14 bg-smpDark relative">
      <div class="max-w-6xl mx-auto px-4 sm:px-6">
        
        <div class="text-center mb-12">
          <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-pineapple-500/10 border border-pineapple-500/30 text-pineapple-300 text-xs font-bold uppercase tracking-widest mb-3">
            <i class="fa-solid fa-star text-pineapple-400"></i> Why Play on PineappleSMP
          </div>
          <h2 class="text-3xl sm:text-5xl font-heading font-black text-white tracking-wide">
            SERVER FEATURES & GAMEPLAY
          </h2>
          <p class="text-slate-400 text-sm sm:text-base mt-3 max-w-xl mx-auto">
            Engineered for low latency, smooth PvP combat, active community trading, and intense lifesteal dynamics.
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          
          <!-- Feature 1 -->
          <div class="mc-panel rounded-2xl p-6 transition-all duration-300 hover:-translate-y-1 group">
            <div class="w-12 h-12 rounded-xl bg-amber-500/10 border border-amber-500/30 text-pineapple-400 flex items-center justify-center text-xl mb-4 group-hover:scale-110 transition-transform">
              <i class="fa-solid fa-heart-crack text-red-400"></i>
            </div>
            <h3 class="text-xl font-heading font-bold text-white mb-2">Lifesteal Combat</h3>
            <p class="text-xs sm:text-sm text-slate-300 leading-relaxed">
              Every kill steals a heart from your target. Eliminate your foes, claim their health, or craft revive beacons to save fallen teammates!
            </p>
          </div>

          <!-- Feature 2 -->
          <div class="mc-panel rounded-2xl p-6 transition-all duration-300 hover:-translate-y-1 group">
            <div class="w-12 h-12 rounded-xl bg-emerald-500/10 border border-emerald-500/30 text-emerald-400 flex items-center justify-center text-xl mb-4 group-hover:scale-110 transition-transform">
              <i class="fa-solid fa-mobile-screen"></i>
            </div>
            <h3 class="text-xl font-heading font-bold text-white mb-2">Crossplay Bedrock + Java</h3>
            <p class="text-xs sm:text-sm text-slate-300 leading-relaxed">
              Play together across Android, iOS, Xbox, PlayStation, Nintendo Switch, and PC with synchronized inventory and combat mechanics.
            </p>
          </div>

          <!-- Feature 3 -->
          <div class="mc-panel rounded-2xl p-6 transition-all duration-300 hover:-translate-y-1 group">
            <div class="w-12 h-12 rounded-xl bg-pineapple-500/10 border border-pineapple-500/30 text-pineapple-400 flex items-center justify-center text-xl mb-4 group-hover:scale-110 transition-transform">
              <i class="fa-solid fa-shield-halved text-emerald-400"></i>
            </div>
            <h3 class="text-xl font-heading font-bold text-white mb-2">High Performance Network</h3>
            <p class="text-xs sm:text-sm text-slate-300 leading-relaxed">
              Optimized low-ping servers guaranteed to deliver seamless PvP combat, active anti-cheat, dedicated DDoS protection, and maximum uptime.
            </p>
          </div>

        </div>

      </div>
    </section>

    <!-- Minecraft Grass & Dirt Pixel Divider -->
    <div class="mc-grass-divider my-2"></div>
      <div class="bg-gradient-to-r from-amber-950/60 via-slate-900 to-emerald-950/70 border-2 border-pineapple-500/40 rounded-3xl p-8 sm:p-10 shadow-2xl text-center relative overflow-hidden">
        <div class="inline-flex p-3 rounded-2xl bg-indigo-500/20 text-[#5865F2] mb-3 text-3xl">
          <i class="fa-brands fa-discord"></i>
        </div>
        <h3 class="text-2xl sm:text-4xl font-heading font-black text-white">JOIN OUR OFFICIAL DISCORD</h3>
        <p class="text-slate-300 text-sm sm:text-base mt-2 max-w-xl mx-auto">
          Participate in community giveaways, team up with SMP clans, report issues, and chat directly with staff and owners!
        </p>
        <div class="mt-6 flex flex-wrap justify-center gap-4">
          <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="shine-btn inline-flex items-center gap-2.5 bg-[#5865F2] hover:bg-[#4752c4] text-white font-extrabold px-8 py-4 rounded-xl text-sm sm:text-base transition-all shadow-xl shadow-[#5865F2]/30">
            <i class="fa-brands fa-discord text-xl"></i>
            <span>Join PineappleSMP Discord (discord.gg/Vp9Ss592cq) &rarr;</span>
          </a>
        </div>
      </div>
    </section>

    <!-- Minecraft Grass & Dirt Pixel Divider -->
    <div class="mc-grass-divider my-2"></div>

    <!-- PINEAPPLESMP AI SUPPORT ASSISTANT (DIRECTLY ABOVE FOOTER & WATERMARK) -->
    <section id="ai-support" class="py-14 max-w-5xl mx-auto px-4 sm:px-6">
      <div class="text-center mb-8">
        <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-pineapple-500/15 border border-pineapple-500/40 text-pineapple-300 text-xs font-bold uppercase tracking-widest mb-3">
          <i class="fa-solid fa-robot text-emerald-400"></i> 24/7 Smart Server Helper
        </div>
        <h2 class="text-3xl sm:text-4xl font-heading font-black text-white tracking-wide">
          PINEAPPLE SMP <span class="text-transparent bg-clip-text bg-gradient-to-r from-pineapple-300 to-emerald-400">AI SUPPORT</span>
        </h2>
        <p class="text-slate-400 text-xs sm:text-sm mt-2 max-w-xl mx-auto">
          Ask about server IPs, Lifesteal gameplay, or paste any Minecraft connection error for instant step-by-step troubleshooting.
        </p>
      </div>

      <!-- Minecraft Beveled AI Console Panel -->
      <div class="mc-panel rounded-3xl border-2 border-pineapple-500/60 overflow-hidden shadow-[0_0_50px_rgba(250,204,21,0.18)]">
        
        <!-- AI Top Control Header & 3-Language Switcher -->
        <div class="bg-gradient-to-r from-amber-950/90 via-slate-900 to-emerald-950/90 px-4 sm:px-6 py-4 border-b border-pineapple-500/30 flex flex-col sm:flex-row sm:items-center justify-between gap-3">
          <div class="flex items-center gap-3">
            <div class="w-10 h-10 rounded-xl bg-gradient-to-br from-pineapple-500/30 to-emerald-500/30 border border-pineapple-400/60 flex items-center justify-center text-pineapple-300 text-lg shadow-inner shrink-0">
              <i class="fa-solid fa-microchip"></i>
            </div>
            <div>
              <div class="flex items-center gap-2">
                <h3 class="font-heading font-black text-base sm:text-lg text-white tracking-wide">PineappleBot AI</h3>
                <span class="inline-flex items-center gap-1 text-[10px] font-bold uppercase px-2 py-0.5 rounded-full bg-emerald-500/20 text-emerald-300 border border-emerald-500/40">
                  <span class="w-1.5 h-1.5 rounded-full bg-emerald-400 animate-ping"></span> Online
                </span>
              </div>
              <p class="text-[11px] text-slate-400">Select your preferred response language below</p>
            </div>
          </div>

          <!-- 3-Language Switcher (English, Hindi, Hinglish) -->
          <div class="flex items-center gap-1.5 bg-slate-950/90 p-1.5 rounded-xl border border-slate-800 self-start sm:self-auto" role="group" aria-label="AI Response Language">
            <span class="text-[10px] font-bold uppercase text-slate-500 px-2 hidden md:inline">Language:</span>
            <button type="button" id="lang-btn-English" onclick="setAiLanguage('English')" class="px-3 py-1.5 rounded-lg text-xs font-extrabold transition-all bg-gradient-to-r from-pineapple-500 to-amber-500 text-slate-950 shadow">
              English
            </button>
            <button type="button" id="lang-btn-Hindi" onclick="setAiLanguage('Hindi')" class="px-3 py-1.5 rounded-lg text-xs font-extrabold transition-all text-slate-300 hover:text-white hover:bg-slate-800">
              Hindi
            </button>
            <button type="button" id="lang-btn-Hinglish" onclick="setAiLanguage('Hinglish')" class="px-3 py-1.5 rounded-lg text-xs font-extrabold transition-all text-slate-300 hover:text-white hover:bg-slate-800">
              Hinglish
            </button>
          </div>
        </div>

        <!-- Quick Error & Topic Prompt Chips (In English) -->
        <div class="bg-slate-950/75 px-4 sm:px-6 py-3 border-b border-slate-800/80 flex items-center gap-2 overflow-x-auto">
          <span class="text-[10px] font-bold uppercase tracking-wider text-pineapple-400 shrink-0">Quick Help:</span>
          <button type="button" onclick="sendQuickAiPrompt('Unable to connect to world error fix')" class="shrink-0 text-xs font-semibold bg-slate-900 hover:bg-slate-800 text-slate-200 border border-slate-700 hover:border-pineapple-500/60 px-3 py-1.5 rounded-lg transition-all">
            Unable to connect to world
          </button>
          <button type="button" onclick="sendQuickAiPrompt('Outdated Client or Outdated Server error fix')" class="shrink-0 text-xs font-semibold bg-slate-900 hover:bg-slate-800 text-slate-200 border border-slate-700 hover:border-pineapple-500/60 px-3 py-1.5 rounded-lg transition-all">
            Outdated Client / Server
          </button>
          <button type="button" onclick="sendQuickAiPrompt('What is the Bedrock Edition IP and Port?')" class="shrink-0 text-xs font-semibold bg-slate-900 hover:bg-slate-800 text-slate-200 border border-slate-700 hover:border-pineapple-500/60 px-3 py-1.5 rounded-lg transition-all">
            Bedrock IP &amp; Port
          </button>
          <button type="button" onclick="sendQuickAiPrompt('What is the Java Edition IP and Port?')" class="shrink-0 text-xs font-semibold bg-slate-900 hover:bg-slate-800 text-slate-200 border border-slate-700 hover:border-pineapple-500/60 px-3 py-1.5 rounded-lg transition-all">
            Java IP &amp; Port
          </button>
          <button type="button" onclick="sendQuickAiPrompt('Connection Timed Out or High Ping Lag Fix')" class="shrink-0 text-xs font-semibold bg-slate-900 hover:bg-slate-800 text-slate-200 border border-slate-700 hover:border-pineapple-500/60 px-3 py-1.5 rounded-lg transition-all">
            Connection Timed Out / Lag
          </button>
        </div>

        <!-- AI Chat Messages Feed -->
        <div id="ai-chat-messages" class="p-4 sm:p-6 space-y-4 max-h-[420px] overflow-y-auto avatar-scroll bg-gradient-to-b from-slate-950/60 to-smpDark/90">
          <!-- Initial Welcome Message -->
          <div class="flex items-start gap-3">
            <div class="w-9 h-9 rounded-xl bg-gradient-to-br from-pineapple-500 to-emerald-600 text-slate-950 font-black flex items-center justify-center shrink-0 shadow-md">
              <i class="fa-solid fa-robot"></i>
            </div>
            <div class="flex-1 bg-slate-900/95 border border-pineapple-500/35 rounded-2xl rounded-tl-none p-4 text-xs sm:text-sm text-slate-200 leading-relaxed shadow-md">
              <div class="font-bold text-pineapple-300 mb-1">Welcome to PineappleSMP AI Support!</div>
              <p>
                Ask me anything about <strong>PineappleSMP Season 1</strong>, Bedrock &amp; Java connection details, or paste any Minecraft error message you are facing. I will guide you step-by-step on how to fix it!
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
        <div class="p-4 sm:px-6 bg-slate-950/95 border-t border-slate-800/90 space-y-3">
          <form id="ai-chat-form" onsubmit="handleAiChatSubmit(event)" class="flex items-center gap-2.5">
            <div class="relative flex-1">
              <span class="absolute inset-y-0 left-0 pl-3.5 flex items-center text-pineapple-400">
                <i class="fa-solid fa-terminal text-xs"></i>
              </span>
              <input type="text" id="ai-user-input" required maxlength="500" placeholder="Describe your Minecraft error or ask a question (e.g., Unable to connect to world)..." class="w-full bg-slate-900 border border-slate-700 focus:border-pineapple-400 rounded-xl pl-10 pr-4 py-3 text-xs sm:text-sm text-white placeholder-slate-500 outline-none transition-colors">
            </div>
            <button type="submit" id="ai-send-btn" class="mc-btn shine-btn bg-gradient-to-r from-pineapple-500 via-amber-500 to-emerald-500 hover:from-pineapple-400 hover:to-emerald-400 text-slate-950 font-black px-5 py-3 rounded-xl text-xs sm:text-sm uppercase tracking-wider flex items-center gap-2 shrink-0">
              <span>Ask AI</span>
              <i class="fa-solid fa-paper-plane"></i>
            </button>
          </form>

          <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-2 text-[11px] text-slate-400 px-1">
            <span>
              <i class="fa-solid fa-circle-info text-pineapple-400 mr-1"></i>
              If your issue is not solved by AI troubleshooting, create a support ticket on our Discord server.
            </span>
            <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-1.5 text-indigo-300 hover:text-white font-bold transition-colors shrink-0">
              <i class="fa-brands fa-discord text-[#5865F2]"></i>
              <span>Create Ticket on Discord &rarr;</span>
            </a>
          </div>
        </div>

      </div>
    </section>

  </main>

  <!-- Footer -->
  <footer class="border-t border-smpBorder/60 bg-slate-950 py-10 text-slate-500 text-xs">
    <div class="max-w-7xl mx-auto px-4 flex flex-col md:flex-row items-center justify-between gap-4">
      <div class="flex items-center gap-3">
        <div class="w-11 h-11 rounded-xl border border-pineapple-500/50 bg-gradient-to-br from-amber-950 to-slate-950 flex items-center justify-center p-1 shadow-md shadow-amber-500/20">
          <!-- Bespoke Inline Vector Logo (Footer) -->
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 300" class="w-full h-full">
            <defs>
              <linearGradient id="ftrPTop" x1="0" y1="0" x2="1" y2="1">
                <stop offset="0%" stop-color="#FEF08A"/>
                <stop offset="100%" stop-color="#FACC15"/>
              </linearGradient>
              <linearGradient id="ftrPFront" x1="0" y1="0" x2="0" y2="1">
                <stop offset="0%" stop-color="#FACC15"/>
                <stop offset="100%" stop-color="#EA580C"/>
              </linearGradient>
              <linearGradient id="ftrPSide" x1="0" y1="0" x2="1" y2="1">
                <stop offset="0%" stop-color="#EAB308"/>
                <stop offset="100%" stop-color="#B45309"/>
              </linearGradient>
              <linearGradient id="ftrLeaf" x1="0" y1="1" x2="0" y2="0">
                <stop offset="0%" stop-color="#047857"/>
                <stop offset="60%" stop-color="#10B981"/>
                <stop offset="100%" stop-color="#6EE7B7"/>
              </linearGradient>
            </defs>
            <path d="M160 66 C152 30, 145 10, 160 4 C175 10, 168 30, 160 66 Z" fill="url(#ftrLeaf)" stroke="#064E3B" stroke-width="4"/>
            <path d="M152 68 C130 38, 108 26, 102 38 C114 58, 134 68, 152 74 Z" fill="url(#ftrLeaf)" stroke="#064E3B" stroke-width="4"/>
            <path d="M168 68 C190 38, 212 26, 218 38 C206 58, 186 68, 168 74 Z" fill="url(#ftrLeaf)" stroke="#064E3B" stroke-width="4"/>
            <polygon points="160,64 226,88 160,112 94,88" fill="url(#ftrPTop)" stroke="#451A03" stroke-width="5" stroke-linejoin="round"/>
            <polygon points="94,88 160,112 160,188 94,162" fill="url(#ftrPSide)" stroke="#451A03" stroke-width="5" stroke-linejoin="round"/>
            <polygon points="160,112 226,88 226,162 160,188" fill="url(#ftrPFront)" stroke="#451A03" stroke-width="5" stroke-linejoin="round"/>
            <rect x="172" y="132" width="11" height="14" rx="2" fill="#1E293B"/>
            <rect x="174" y="134" width="4" height="4" fill="#FFFFFF"/>
            <rect x="204" y="120" width="11" height="14" rx="2" fill="#1E293B"/>
            <rect x="206" y="122" width="4" height="4" fill="#FFFFFF"/>
            <path d="M187 143 Q194 152 200 140 Z" fill="#881337"/>
            <rect x="46" y="176" width="228" height="54" rx="12" fill="#451A03" stroke="#FDE047" stroke-width="4"/>
            <text x="160" y="213" font-family="'Outfit', sans-serif" font-weight="900" font-size="34" text-anchor="middle" fill="#FACC15" letter-spacing="1.5">PINEAPPLE</text>
            <rect x="96" y="232" width="128" height="44" rx="8" fill="#78350F" stroke="#290F02" stroke-width="5"/>
            <text x="160" y="263" font-family="'Outfit', sans-serif" font-weight="900" font-size="28" text-anchor="middle" fill="#FFFFFF" letter-spacing="3">SMP</text>
          </svg>
        </div>
        <div class="flex flex-col text-left">
          <span class="font-heading font-bold text-slate-300 text-sm tracking-wider">PINEAPPLE SMP</span>
          <button onclick="copyToClipboard('basic.vitalcloud.in:19126', 'Copied IP: basic.vitalcloud.in:19126')" class="text-[10px] text-pineapple-400 hover:text-pineapple-300 font-mono text-left transition-colors">
            basic.vitalcloud.in:19126
          </button>
        </div>
      </div>
      <div>
        Official Community Hub &copy; 2026 PineappleSMP. Not an official Minecraft product. Not approved by or associated with Mojang or Microsoft.
      </div>
      <div class="flex items-center gap-4 text-base">
        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="hover:text-pineapple-400 transition-colors" title="Discord">
          <i class="fa-brands fa-discord"></i>
        </a>
      </div>
    </div>

    <!-- Powered by Devesh Watermark -->
    <div class="mt-8 pt-6 border-t border-slate-900 text-center flex flex-col sm:flex-row items-center justify-center gap-2">
      <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-gradient-to-r from-amber-950 via-slate-900 to-emerald-950 border border-pineapple-500/50 shadow-[0_0_20px_rgba(250,204,21,0.25)]">
        <i class="fa-solid fa-bolt text-pineapple-300 text-xs animate-pulse"></i>
        <span class="text-xs uppercase tracking-widest font-semibold text-slate-300">
          POWERED BY <strong class="text-transparent bg-clip-text bg-gradient-to-r from-pineapple-300 via-amber-300 to-emerald-300 font-extrabold tracking-wider text-sm">DEVESH</strong>
        </span>
        <i class="fa-solid fa-bolt text-pineapple-300 text-xs"></i>
      </div>
    </div>
  </footer>

  <!-- Firebase Modular SDK & Complete Application Logic -->
  <script type="module">
    import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
    import {
      getAuth,
      GoogleAuthProvider,
      signInWithPopup,
      createUserWithEmailAndPassword,
      signInWithEmailAndPassword,
      signInWithCustomToken,
      signInAnonymously,
      onAuthStateChanged,
      signOut,
      updateProfile
    } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
    import {
      getFirestore,
      doc,
      getDoc,
      setDoc,
      serverTimestamp
    } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

    // Server Telemetry Endpoint Configuration
    const SERVER_IP = "basic.vitalcloud.in";
    const JAVA_PORT = 19126;
    const BEDROCK_PORT = 19149;
    const JAVA_FULL_ADDRESS = `${SERVER_IP}:${JAVA_PORT}`;
    const BEDROCK_FULL_ADDRESS = `${SERVER_IP}:${BEDROCK_PORT}`;

    // 16 Custom Hand-Crafted Vector SVG Avatars (8 Minecraft Characters + 8 Animals)
    const AVATAR_CATALOG = [
      // --- MINECRAFT CHARACTERS ---
      {
        id: 'mc_steve',
        name: 'Steve',
        category: 'Minecraft',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#0284C7"/><rect x="12" y="12" width="40" height="40" fill="#D99B72"/><rect x="12" y="12" width="40" height="10" fill="#4A2E1B"/><rect x="12" y="22" width="6" height="6" fill="#4A2E1B"/><rect x="46" y="22" width="6" height="6" fill="#4A2E1B"/><rect x="18" y="28" width="6" height="5" fill="#FFFFFF"/><rect x="24" y="28" width="5" height="5" fill="#3B277A"/><rect x="40" y="28" width="6" height="5" fill="#FFFFFF"/><rect x="35" y="28" width="5" height="5" fill="#3B277A"/><rect x="28" y="34" width="8" height="5" fill="#B57550"/><rect x="22" y="42" width="20" height="6" fill="#6E3B23"/><rect x="26" y="42" width="12" height="3" fill="#D99B72"/></svg>`
      },
      {
        id: 'mc_alex',
        name: 'Alex',
        category: 'Minecraft',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#059669"/><rect x="12" y="12" width="40" height="40" fill="#F3C39E"/><rect x="12" y="12" width="40" height="11" fill="#EA580C"/><rect x="12" y="23" width="7" height="16" fill="#EA580C"/><rect x="45" y="23" width="7" height="10" fill="#EA580C"/><rect x="18" y="29" width="6" height="5" fill="#FFFFFF"/><rect x="24" y="29" width="5" height="5" fill="#15803D"/><rect x="40" y="29" width="6" height="5" fill="#FFFFFF"/><rect x="35" y="29" width="5" height="5" fill="#15803D"/><rect x="26" y="41" width="12" height="4" fill="#E08B79"/></svg>`
      },
      {
        id: 'mc_creeper',
        name: 'Creeper',
        category: 'Minecraft',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#14532D"/><rect x="12" y="12" width="40" height="40" fill="#22C55E"/><rect x="12" y="12" width="10" height="10" fill="#16A34A"/><rect x="42" y="16" width="10" height="12" fill="#4ADE80"/><rect x="16" y="38" width="10" height="12" fill="#16A34A"/><rect x="18" y="22" width="10" height="10" fill="#090D0A"/><rect x="36" y="22" width="10" height="10" fill="#090D0A"/><rect x="28" y="32" width="8" height="12" fill="#090D0A"/><rect x="22" y="36" width="6" height="14" fill="#090D0A"/><rect x="36" y="36" width="6" height="14" fill="#090D0A"/></svg>`
      },
      {
        id: 'mc_enderman',
        name: 'Enderman',
        category: 'Minecraft',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#2E1065"/><rect x="12" y="12" width="40" height="40" fill="#0F0F12"/><rect x="14" y="14" width="12" height="8" fill="#1E1B24"/><rect x="16" y="30" width="12" height="5" fill="#E879F9"/><rect x="20" y="30" width="4" height="5" fill="#F5D0FE"/><rect x="36" y="30" width="12" height="5" fill="#E879F9"/><rect x="40" y="30" width="4" height="5" fill="#F5D0FE"/></svg>`
      },
      {
        id: 'mc_skeleton',
        name: 'Skeleton',
        category: 'Minecraft',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#334155"/><rect x="12" y="12" width="40" height="40" fill="#E2E8F0"/><rect x="12" y="12" width="40" height="8" fill="#CBD5E1"/><rect x="18" y="26" width="10" height="6" fill="#1E293B"/><rect x="36" y="26" width="10" height="6" fill="#1E293B"/><rect x="28" y="34" width="8" height="4" fill="#64748B"/><rect x="18" y="42" width="28" height="5" fill="#1E293B"/></svg>`
      },
      {
        id: 'mc_zombie',
        name: 'Zombie',
        category: 'Minecraft',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#064E3B"/><rect x="12" y="12" width="40" height="40" fill="#4D7C0F"/><rect x="12" y="12" width="40" height="10" fill="#365314"/><rect x="18" y="28" width="10" height="6" fill="#1A2E05"/><rect x="36" y="28" width="10" height="6" fill="#1A2E05"/><rect x="27" y="35" width="10" height="4" fill="#3F6212"/><rect x="24" y="42" width="16" height="5" fill="#365314"/></svg>`
      },
      {
        id: 'mc_piglin',
        name: 'Piglin',
        category: 'Minecraft',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#7F1D1D"/><rect x="12" y="12" width="40" height="40" fill="#FDBA74"/><rect x="12" y="12" width="40" height="9" fill="#FACC15"/><rect x="18" y="26" width="6" height="6" fill="#FFFFFF"/><rect x="22" y="26" width="4" height="6" fill="#1E293B"/><rect x="40" y="26" width="6" height="6" fill="#FFFFFF"/><rect x="38" y="26" width="4" height="6" fill="#1E293B"/><rect x="22" y="35" width="20" height="11" fill="#FB923C"/><rect x="25" y="38" width="4" height="5" fill="#7C2D12"/><rect x="35" y="38" width="4" height="5" fill="#7C2D12"/><rect x="19" y="41" width="3" height="6" fill="#FFFFFF"/><rect x="42" y="41" width="3" height="6" fill="#FFFFFF"/></svg>`
      },
      {
        id: 'mc_pineapple_knight',
        name: 'Pineapple Hero',
        category: 'Minecraft',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#78350F"/><polygon points="32,4 24,16 40,16" fill="#10B981"/><polygon points="20,7 16,17 28,17" fill="#059669"/><polygon points="44,7 48,17 36,17" fill="#059669"/><rect x="14" y="16" width="36" height="36" rx="6" fill="#FACC15"/><path d="M16 18 L48 50 M48 18 L16 50" stroke="#CA8A04" stroke-width="2" opacity="0.55"/><rect x="20" y="29" width="6" height="7" rx="1.5" fill="#1E293B"/><rect x="38" y="29" width="6" height="7" rx="1.5" fill="#1E293B"/><rect x="21" y="30" width="2" height="2" fill="#FFF"/><rect x="39" y="30" width="2" height="2" fill="#FFF"/><path d="M27 40 Q32 45 37 40 Z" fill="#991B1B"/></svg>`
      },

      // --- ANIMALS ---
      {
        id: 'ani_fox',
        name: 'Fox',
        category: 'Animal',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#065F46"/><polygon points="12,24 16,8 28,20" fill="#EA580C"/><polygon points="52,24 48,8 36,20" fill="#EA580C"/><rect x="12" y="20" width="40" height="30" rx="8" fill="#F97316"/><polygon points="12,36 26,50 12,50" fill="#FFF7ED"/><polygon points="52,36 38,50 52,50" fill="#FFF7ED"/><rect x="18" y="30" width="6" height="6" rx="1" fill="#1E293B"/><rect x="40" y="30" width="6" height="6" rx="1" fill="#1E293B"/><rect x="28" y="39" width="8" height="6" rx="2" fill="#1E293B"/></svg>`
      },
      {
        id: 'ani_wolf',
        name: 'Wolf',
        category: 'Animal',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#1E293B"/><polygon points="14,22 18,8 28,20" fill="#94A3B8"/><polygon points="50,22 46,8 36,20" fill="#94A3B8"/><rect x="13" y="18" width="38" height="32" rx="7" fill="#CBD5E1"/><rect x="22" y="34" width="20" height="16" rx="4" fill="#F8FAFC"/><rect x="18" y="27" width="6" height="5" fill="#0F172A"/><rect x="40" y="27" width="6" height="5" fill="#0F172A"/><rect x="28" y="36" width="8" height="5" rx="2" fill="#0F172A"/><rect x="24" y="45" width="16" height="4" fill="#EF4444"/></svg>`
      },
      {
        id: 'ani_axolotl',
        name: 'Axolotl',
        category: 'Animal',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#0E7490"/><rect x="6" y="18" width="10" height="5" rx="2" fill="#EC4899"/><rect x="6" y="28" width="10" height="5" rx="2" fill="#EC4899"/><rect x="48" y="18" width="10" height="5" rx="2" fill="#EC4899"/><rect x="48" y="28" width="10" height="5" rx="2" fill="#EC4899"/><rect x="14" y="16" width="36" height="34" rx="10" fill="#F9A8D4"/><circle cx="23" cy="31" r="3.5" fill="#1E293B"/><circle cx="41" cy="31" r="3.5" fill="#1E293B"/><path d="M27 39 Q32 44 37 39" stroke="#BE185D" stroke-width="3" fill="none" stroke-linecap="round"/></svg>`
      },
      {
        id: 'ani_panda',
        name: 'Panda',
        category: 'Animal',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#15803D"/><circle cx="17" cy="17" r="7" fill="#0F172A"/><circle cx="47" cy="17" r="7" fill="#0F172A"/><rect x="13" y="16" width="38" height="34" rx="12" fill="#FFFFFF"/><ellipse cx="23" cy="30" rx="6" ry="7" fill="#0F172A"/><ellipse cx="41" cy="30" rx="6" ry="7" fill="#0F172A"/><circle cx="24" cy="29" r="2" fill="#FFFFFF"/><circle cx="40" cy="29" r="2" fill="#FFFFFF"/><ellipse cx="32" cy="39" rx="5" ry="3.5" fill="#0F172A"/></svg>`
      },
      {
        id: 'ani_bee',
        name: 'Honey Bee',
        category: 'Animal',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#0284C7"/><rect x="20" y="8" width="4" height="10" fill="#1E293B"/><rect x="40" y="8" width="4" height="10" fill="#1E293B"/><rect x="13" y="17" width="38" height="32" rx="9" fill="#FACC15"/><rect x="13" y="25" width="38" height="5" fill="#1E293B"/><rect x="13" y="38" width="38" height="5" fill="#1E293B"/><rect x="17" y="28" width="7" height="7" rx="1.5" fill="#38BDF8"/><rect x="40" y="28" width="7" height="7" rx="1.5" fill="#38BDF8"/></svg>`
      },
      {
        id: 'ani_redpanda',
        name: 'Red Panda',
        category: 'Animal',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#14532D"/><circle cx="16" cy="17" r="7" fill="#7C2D12"/><circle cx="48" cy="17" r="7" fill="#7C2D12"/><rect x="13" y="16" width="38" height="34" rx="11" fill="#C2410C"/><ellipse cx="22" cy="27" rx="4" ry="3" fill="#FFF7ED"/><ellipse cx="42" cy="27" rx="4" ry="3" fill="#FFF7ED"/><circle cx="22" cy="32" r="3" fill="#0F172A"/><circle cx="42" cy="32" r="3" fill="#0F172A"/><ellipse cx="32" cy="41" rx="9" ry="7" fill="#FFF7ED"/><circle cx="32" cy="39" r="3" fill="#0F172A"/></svg>`
      },
      {
        id: 'ani_tiger',
        name: 'Tiger',
        category: 'Animal',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#064E3B"/><circle cx="17" cy="17" r="6" fill="#EA580C"/><circle cx="47" cy="17" r="6" fill="#EA580C"/><rect x="13" y="16" width="38" height="34" rx="10" fill="#FB923C"/><rect x="29" y="16" width="6" height="8" fill="#1E293B"/><rect x="13" y="28" width="6" height="4" fill="#1E293B"/><rect x="45" y="28" width="6" height="4" fill="#1E293B"/><circle cx="23" cy="31" r="3.5" fill="#FEF08A"/><circle cx="23" cy="31" r="1.8" fill="#0F172A"/><circle cx="41" cy="31" r="3.5" fill="#FEF08A"/><circle cx="41" cy="31" r="1.8" fill="#0F172A"/><ellipse cx="32" cy="41" rx="8" ry="6" fill="#FFF7ED"/><polygon points="29,38 35,38 32,42" fill="#EC4899"/></svg>`
      },
      {
        id: 'ani_penguin',
        name: 'Penguin',
        category: 'Animal',
        svg: `<svg viewBox="0 0 64 64" class="w-full h-full rounded-full"><rect width="64" height="64" fill="#1D4ED8"/><rect x="14" y="13" width="36" height="38" rx="14" fill="#0F172A"/><ellipse cx="32" cy="35" rx="13" ry="14" fill="#F8FAFC"/><circle cx="24" cy="27" r="3.5" fill="#FFFFFF"/><circle cx="24" cy="27" r="1.8" fill="#0F172A"/><circle cx="40" cy="27" r="3.5" fill="#FFFFFF"/><circle cx="40" cy="27" r="1.8" fill="#0F172A"/><polygon points="27,33 37,33 32,40" fill="#F59E0B"/></svg>`
      }
    ];

    // Firebase Initialization
    const appId = typeof __app_id !== 'undefined' ? __app_id : 'pineapplesmp-app';
    let firebaseApp = null;
    let auth = null;
    let db = null;
    let googleProvider = null;

    try {
      if (typeof __firebase_config !== 'undefined' && __firebase_config) {
        const firebaseConfig = JSON.parse(__firebase_config);
        firebaseApp = initializeApp(firebaseConfig);
        auth = getAuth(firebaseApp);
        db = getFirestore(firebaseApp);
        googleProvider = new GoogleAuthProvider();
        googleProvider.setCustomParameters({ prompt: 'select_account' });
      }
    } catch (initErr) {
      console.warn('Firebase configuration warning:', initErr);
    }

    // Application Auth & Profile State
    let currentUser = null;
    let currentProfile = null;
    let selectedAvatarId = AVATAR_CATALOG[0].id;
    let currentAuthMode = 'signup';
    let modalAutoShown = false;

    // Helper: Get Profile Firestore Document Reference (Strict Rule 1 Path)
    function getUserProfileDocRef(uid) {
      if (!db) return null;
      return doc(db, 'artifacts', appId, 'users', uid, 'profile', 'main');
    }

    // Load User Profile from Firestore
    async function loadUserProfile(firebaseUser) {
      if (!firebaseUser || firebaseUser.isAnonymous) {
        currentUser = null;
        currentProfile = null;
        updateNavbarProfileUI();
        return;
      }

      currentUser = firebaseUser;
      const isGoogle = firebaseUser.providerData && firebaseUser.providerData.some(p => p.providerId === 'google.com');
      const defaultIgn = firebaseUser.displayName
        ? firebaseUser.displayName.replace(/\s+/g, '_').slice(0, 16)
        : (firebaseUser.email ? firebaseUser.email.split('@')[0].slice(0, 16) : 'Warrior');

      const fallbackProfile = {
        uid: firebaseUser.uid,
        username: defaultIgn,
        email: firebaseUser.email || '',
        avatarId: firebaseUser.photoURL ? 'google_photo' : AVATAR_CATALOG[0].id,
        photoURL: firebaseUser.photoURL || '',
        provider: isGoogle ? 'google' : 'email'
      };

      try {
        const docRef = getUserProfileDocRef(firebaseUser.uid);
        if (docRef) {
          const snap = await getDoc(docRef);
          if (snap.exists()) {
            const data = snap.data();
            currentProfile = {
              ...fallbackProfile,
              ...data,
              photoURL: firebaseUser.photoURL || data.photoURL || ''
            };
          } else {
            currentProfile = fallbackProfile;
            await setDoc(docRef, {
              ...currentProfile,
              createdAt: serverTimestamp(),
              updatedAt: serverTimestamp()
            });
          }
        } else {
          currentProfile = fallbackProfile;
        }
      } catch (err) {
        console.warn('Firestore profile fetch notice:', err);
        currentProfile = fallbackProfile;
      }

      selectedAvatarId = currentProfile.avatarId || AVATAR_CATALOG[0].id;
      updateNavbarProfileUI();
    }

    // Save User Profile to Firestore
    async function saveUserProfile(firebaseUser, profileUpdates) {
      if (!firebaseUser || firebaseUser.isAnonymous) return;
      const isGoogle = firebaseUser.providerData && firebaseUser.providerData.some(p => p.providerId === 'google.com');
      const mergedProfile = {
        uid: firebaseUser.uid,
        username: profileUpdates.username || currentProfile?.username || firebaseUser.displayName || 'Warrior',
        email: firebaseUser.email || currentProfile?.email || '',
        avatarId: profileUpdates.avatarId || selectedAvatarId,
        photoURL: firebaseUser.photoURL || currentProfile?.photoURL || '',
        provider: isGoogle ? 'google' : 'email',
        updatedAt: serverTimestamp()
      };

      currentProfile = mergedProfile;

      try {
        if (firebaseUser.displayName !== mergedProfile.username) {
          await updateProfile(firebaseUser, { displayName: mergedProfile.username });
        }
      } catch (e) {
        // Non-blocking profile displayName sync
      }

      try {
        const docRef = getUserProfileDocRef(firebaseUser.uid);
        if (docRef) {
          await setDoc(docRef, mergedProfile, { merge: true });
        }
      } catch (err) {
        console.warn('Firestore save notice:', err);
      }

      updateNavbarProfileUI();
    }

    // Render Avatar Grid (16 Custom SVG Avatars + Google Photo Option if available)
    function renderAvatarGrid() {
      const grid = document.getElementById('avatar-grid');
      if (!grid) return;
      grid.innerHTML = '';

      const options = [...AVATAR_CATALOG];
      const activePhotoURL = currentUser?.photoURL || currentProfile?.photoURL;
      if (activePhotoURL) {
        options.unshift({
          id: 'google_photo',
          name: 'Google Photo',
          category: 'Google',
          photoURL: activePhotoURL
        });
      }

      options.forEach(avatar => {
        const isSelected = avatar.id === selectedAvatarId;
        const btn = document.createElement('button');
        btn.type = 'button';
        btn.onclick = () => {
          selectedAvatarId = avatar.id;
          renderAvatarGrid();
        };
        btn.className = `group flex flex-col items-center p-1.5 rounded-xl border-2 transition-all ${
          isSelected
            ? 'border-pineapple-400 bg-pineapple-500/20 shadow-[0_0_15px_rgba(250,204,21,0.35)] scale-105'
            : 'border-slate-800 bg-slate-900/80 hover:border-slate-600 hover:bg-slate-800'
        }`;

        const visualMarkup = avatar.photoURL
          ? `<img src="${avatar.photoURL}" alt="Google Avatar" referrerpolicy="no-referrer" class="w-full h-full object-cover rounded-full">`
          : avatar.svg;

        btn.innerHTML = `
          <div class="w-11 h-11 rounded-full overflow-hidden border border-slate-700 shadow-inner flex items-center justify-center">
            ${visualMarkup}
          </div>
          <span class="text-[10px] font-bold mt-1 truncate w-full text-center ${isSelected ? 'text-pineapple-300' : 'text-slate-400 group-hover:text-slate-200'}">
            ${avatar.name}
          </span>
        `;
        grid.appendChild(btn);
      });

      const activeObj = options.find(a => a.id === selectedAvatarId) || options[0];
      const labelElem = document.getElementById('selected-avatar-label');
      if (labelElem && activeObj) {
        labelElem.textContent = `${activeObj.name} (${activeObj.category})`;
      }
    }

    // Switch Between Sign Up, Sign In, and Profile Customization Modes
    function switchAuthTab(mode) {
      currentAuthMode = mode;
      const tabSignup = document.getElementById('tab-signup');
      const tabLogin = document.getElementById('tab-login');
      const authTabsWrapper = document.getElementById('auth-mode-tabs');
      const googleWrapper = document.getElementById('google-auth-wrapper');
      const modalTitle = document.getElementById('auth-modal-title');
      const modalSubtitle = document.getElementById('auth-modal-subtitle');
      const submitText = document.getElementById('auth-submit-text');
      const googleBtnText = document.getElementById('google-btn-text');
      const ignWrapper = document.getElementById('ign-field-wrapper');
      const emailWrapper = document.getElementById('email-field-wrapper');
      const passwordWrapper = document.getElementById('password-field-wrapper');
      const avatarSection = document.getElementById('avatar-selector-section');
      const errorBox = document.getElementById('auth-error-msg');

      const ignInput = document.getElementById('auth-username');
      const emailInput = document.getElementById('auth-email');
      const passInput = document.getElementById('auth-password');

      if (errorBox) errorBox.classList.add('hidden');

      if (mode === 'profile' && currentUser && !currentUser.isAnonymous) {
        authTabsWrapper.classList.add('hidden');
        googleWrapper.classList.add('hidden');
        emailWrapper.classList.add('hidden');
        passwordWrapper.classList.add('hidden');
        ignWrapper.classList.remove('hidden');
        avatarSection.classList.remove('hidden');

        ignInput.required = true;
        emailInput.required = false;
        passInput.required = false;

        modalTitle.textContent = 'CUSTOMIZE PROFILE';
        modalSubtitle.textContent = 'Update your Minecraft IGN & warrior avatar!';
        submitText.textContent = 'Save Profile & Avatar';
        return;
      }

      authTabsWrapper.classList.remove('hidden');
      googleWrapper.classList.remove('hidden');
      emailWrapper.classList.remove('hidden');
      passwordWrapper.classList.remove('hidden');

      if (mode === 'signup') {
        tabSignup.className = 'py-2 rounded-lg text-xs font-extrabold uppercase tracking-wider transition-all bg-gradient-to-r from-pineapple-500 to-amber-500 text-slate-950 shadow';
        tabLogin.className = 'py-2 rounded-lg text-xs font-extrabold uppercase tracking-wider transition-all text-slate-400 hover:text-white';
        modalTitle.textContent = 'WARRIOR PORTAL';
        modalSubtitle.textContent = 'Sign up with Google or Email & equip your avatar!';
        googleBtnText.textContent = 'Sign Up with Google';
        submitText.textContent = 'Create Account & Save';

        ignWrapper.classList.remove('hidden');
        avatarSection.classList.remove('hidden');
        ignInput.required = true;
        emailInput.required = true;
        passInput.required = true;
      } else {
        tabLogin.className = 'py-2 rounded-lg text-xs font-extrabold uppercase tracking-wider transition-all bg-gradient-to-r from-pineapple-500 to-amber-500 text-slate-950 shadow';
        tabSignup.className = 'py-2 rounded-lg text-xs font-extrabold uppercase tracking-wider transition-all text-slate-400 hover:text-white';
        modalTitle.textContent = 'WELCOME BACK';
        modalSubtitle.textContent = 'Sign in with Google or your registered Gmail!';
        googleBtnText.textContent = 'Sign In with Google';
        submitText.textContent = 'Sign In to Portal';

        ignWrapper.classList.add('hidden');
        avatarSection.classList.add('hidden');
        ignInput.required = false;
        emailInput.required = true;
        passInput.required = true;
      }
    }

    function openAuthModal(mode = 'signup', prefillExisting = false) {
      const modal = document.getElementById('auth-modal');
      const dropdown = document.getElementById('profile-dropdown');
      if (dropdown) dropdown.classList.add('hidden');

      switchAuthTab(mode);

      if (prefillExisting && currentProfile) {
        document.getElementById('auth-username').value = currentProfile.username || '';
        selectedAvatarId = currentProfile.avatarId || AVATAR_CATALOG[0].id;
      }

      renderAvatarGrid();
      modal.classList.remove('hidden');
      modal.classList.add('flex');
    }

    function dismissAuthModal() {
      const modal = document.getElementById('auth-modal');
      modal.classList.add('hidden');
      modal.classList.remove('flex');
      sessionStorage.setItem('pineapplesmp_auth_dismissed', 'true');
    }

    function showAuthError(msg) {
      const errorBox = document.getElementById('auth-error-msg');
      const errorText = document.getElementById('auth-error-text');
      if (errorText) errorText.textContent = msg;
      if (errorBox) errorBox.classList.remove('hidden');
    }

    // Direct Google Account Sign-In / Sign-Up Handler
    async function handleGoogleSignIn() {
      if (!auth || !googleProvider) {
        showAuthError('Authentication service is initializing. Please try again in a moment.');
        return;
      }

      const googleBtn = document.getElementById('google-signin-btn');
      const googleBtnText = document.getElementById('google-btn-text');
      const originalLabel = googleBtnText.textContent;
      googleBtn.disabled = true;
      googleBtnText.textContent = 'Connecting to Google...';

      try {
        const result = await signInWithPopup(auth, googleProvider);
        const signedInUser = result.user;
        await loadUserProfile(signedInUser);

        // If user selected a custom avatar before clicking Google Sign-In, apply it
        if (selectedAvatarId && selectedAvatarId !== 'google_photo' && currentProfile) {
          await saveUserProfile(signedInUser, {
            username: currentProfile.username,
            avatarId: selectedAvatarId
          });
        }

        dismissAuthModal();
        showToast(`Signed in with Google as ${currentProfile?.username || signedInUser.displayName}!`);
      } catch (err) {
        console.error('Google Sign-In error:', err);
        if (err.code === 'auth/popup-closed-by-user') {
          showAuthError('Google sign-in popup was closed. Click the button again to sign in.');
        } else if (err.code === 'auth/unauthorized-domain') {
          showAuthError('Google Sign-In domain authorization pending. Please use Email & Password sign-up below!');
        } else {
          showAuthError(err.message || 'Unable to sign in with Google. Try Email & Password below.');
        }
      } finally {
        googleBtn.disabled = false;
        googleBtnText.textContent = originalLabel;
      }
    }

    // Email/Password Sign-Up, Sign-In, & Profile Customization Submit Handler
    async function handleAuthSubmit(e) {
      e.preventDefault();
      const errorBox = document.getElementById('auth-error-msg');
      if (errorBox) errorBox.classList.add('hidden');

      if (!auth) {
        showAuthError('Authentication service is unavailable right now.');
        return;
      }

      const usernameInput = document.getElementById('auth-username').value.trim();
      const emailInput = document.getElementById('auth-email').value.trim();
      const passwordInput = document.getElementById('auth-password').value;
      const submitBtn = document.getElementById('auth-submit-btn');
      submitBtn.disabled = true;

      try {
        if (currentAuthMode === 'profile' && currentUser && !currentUser.isAnonymous) {
          if (usernameInput.length < 2) {
            showAuthError('Minecraft IGN must be at least 2 characters.');
            submitBtn.disabled = false;
            return;
          }
          await saveUserProfile(currentUser, {
            username: usernameInput,
            avatarId: selectedAvatarId
          });
          dismissAuthModal();
          showToast(`Profile updated! Equipped ${usernameInput}.`);
        } else if (currentAuthMode === 'signup') {
          if (usernameInput.length < 2) {
            showAuthError('Please enter your Minecraft IGN (at least 2 characters).');
            submitBtn.disabled = false;
            return;
          }
          const cred = await createUserWithEmailAndPassword(auth, emailInput, passwordInput);
          await saveUserProfile(cred.user, {
            username: usernameInput,
            avatarId: selectedAvatarId
          });
          dismissAuthModal();
          showToast(`Welcome ${usernameInput}! Account & avatar saved.`);
        } else {
          const cred = await signInWithEmailAndPassword(auth, emailInput, passwordInput);
          await loadUserProfile(cred.user);
          dismissAuthModal();
          showToast(`Welcome back, ${currentProfile?.username || 'Warrior'}!`);
        }
      } catch (err) {
        console.error('Auth error:', err);
        if (err.code === 'auth/email-already-in-use') {
          showAuthError('This email is already registered! Switch to the Sign In tab.');
        } else if (err.code === 'auth/invalid-credential' || err.code === 'auth/wrong-password' || err.code === 'auth/user-not-found') {
          showAuthError('Invalid email or password. Please check and try again.');
        } else if (err.code === 'auth/weak-password') {
          showAuthError('Password must be at least 6 characters long.');
        } else {
          showAuthError(err.message || 'Authentication failed. Please try again.');
        }
      } finally {
        submitBtn.disabled = false;
      }
    }

    async function logoutUser() {
      const dropdown = document.getElementById('profile-dropdown');
      if (dropdown) dropdown.classList.add('hidden');
      try {
        if (auth) {
          await signOut(auth);
        }
        currentUser = null;
        currentProfile = null;
        updateNavbarProfileUI();
        showToast('Signed out successfully.');
      } catch (err) {
        showToast('Error signing out.');
      }
    }

    function handleProfileCircleClick() {
      if (!currentUser || currentUser.isAnonymous || !currentProfile) {
        openAuthModal('signup', false);
      } else {
        const dropdown = document.getElementById('profile-dropdown');
        dropdown.classList.toggle('hidden');
      }
    }

    function updateNavbarProfileUI() {
      const placeholder = document.getElementById('nav-avatar-placeholder');
      const display = document.getElementById('nav-avatar-display');
      const badge = document.getElementById('nav-profile-badge');
      const btn = document.getElementById('nav-profile-btn');

      if (currentUser && !currentUser.isAnonymous && currentProfile) {
        const useGooglePhoto = currentProfile.avatarId === 'google_photo' && currentProfile.photoURL;
        const avatarObj = AVATAR_CATALOG.find(a => a.id === currentProfile.avatarId) || AVATAR_CATALOG[0];

        const visualHtml = useGooglePhoto
          ? `<img src="${currentProfile.photoURL}" alt="${currentProfile.username}" referrerpolicy="no-referrer" class="w-full h-full object-cover rounded-full">`
          : avatarObj.svg;

        placeholder.classList.add('hidden');
        display.classList.remove('hidden');
        display.innerHTML = visualHtml;

        btn.title = `${currentProfile.username} (${useGooglePhoto ? 'Google Photo' : avatarObj.name})`;
        btn.classList.remove('border-pineapple-400/80');
        btn.classList.add('border-emerald-400');

        badge.className = 'absolute -bottom-0.5 -right-0.5 w-3.5 h-3.5 rounded-full bg-emerald-400 border-2 border-smpDark pointer-events-none';
        badge.textContent = '';

        // Populate dropdown card
        const ddPreview = document.getElementById('dropdown-avatar-preview');
        const ddUser = document.getElementById('dropdown-username');
        const ddEmail = document.getElementById('dropdown-email');
        const ddAvatarName = document.getElementById('dropdown-avatar-name');
        const ddProviderBadge = document.getElementById('dropdown-provider-badge');

        if (ddPreview) ddPreview.innerHTML = visualHtml;
        if (ddUser) ddUser.textContent = currentProfile.username;
        if (ddEmail) ddEmail.textContent = currentProfile.email || 'PineappleSMP Warrior';
        if (ddAvatarName) ddAvatarName.textContent = useGooglePhoto ? 'Google Account Photo' : `${avatarObj.name} Avatar`;
        if (ddProviderBadge) {
          if (currentProfile.provider === 'google') {
            ddProviderBadge.classList.remove('hidden');
          } else {
            ddProviderBadge.classList.add('hidden');
          }
        }
      } else {
        placeholder.classList.remove('hidden');
        display.classList.add('hidden');
        display.innerHTML = '';

        btn.title = 'Not Signed In — Click to Sign In or Sign Up';
        btn.classList.add('border-pineapple-400/80');
        btn.classList.remove('border-emerald-400');

        badge.className = 'absolute -bottom-0.5 -right-0.5 w-3.5 h-3.5 rounded-full bg-amber-500 border-2 border-smpDark flex items-center justify-center text-[8px] font-bold text-slate-950 pointer-events-none';
        badge.textContent = '?';
      }
    }

    // Close profile dropdown when clicking outside
    document.addEventListener('click', (event) => {
      const dropdown = document.getElementById('profile-dropdown');
      const profileBtn = document.getElementById('nav-profile-btn');
      if (dropdown && !dropdown.classList.contains('hidden')) {
        if (!dropdown.contains(event.target) && !profileBtn.contains(event.target)) {
          dropdown.classList.add('hidden');
        }
      }
    });

    function renderRealPlayers(onlineCount, maxCount, playerList) {
      const cardPlayersList = document.getElementById('card-players-list');
      const rosterCountTag = document.getElementById('roster-count-tag');
      const playersOnlineElem = document.getElementById('server-players-online');
      const playersMaxElem = document.getElementById('server-players-max');
      const playersStatusElem = document.getElementById('server-players-status');
      const playersPulseDot = document.getElementById('players-pulse-dot');

      if (playersOnlineElem) playersOnlineElem.textContent = onlineCount !== undefined ? onlineCount : '0';
      if (playersMaxElem) playersMaxElem.textContent = `/ ${maxCount || '50'}`;
      if (rosterCountTag) rosterCountTag.textContent = onlineCount > 0 ? `${onlineCount} ONLINE` : '0 ONLINE';

      if (onlineCount > 0) {
        if (playersStatusElem) {
          playersStatusElem.textContent = `${onlineCount} warrior(s) active now!`;
          playersStatusElem.className = 'text-emerald-400 font-semibold';
        }
        if (playersPulseDot) playersPulseDot.className = 'w-1.5 h-1.5 rounded-full bg-emerald-400 animate-ping';

        if (cardPlayersList) {
          cardPlayersList.innerHTML = '';
          if (playerList && playerList.length > 0) {
            playerList.forEach(player => {
              const name = typeof player === 'string' ? player : (player.name_clean || player.name_raw || 'Player');
              const chip = document.createElement('div');
              chip.className = 'flex items-center gap-1.5 bg-slate-900 border border-pineapple-500/30 px-2 py-1 rounded-md text-[11px] font-semibold text-slate-200';
              chip.innerHTML = `
                <img src="https://mc-heads.net/avatar/${encodeURIComponent(name)}/18" alt="${name}" class="w-4 h-4 rounded-sm" onerror="this.src='https://mc-heads.net/avatar/MHF_Steve/18'">
                <span>${name}</span>
              `;
              cardPlayersList.appendChild(chip);
            });
          } else {
            cardPlayersList.innerHTML = `<span class="text-[11px] text-emerald-300 font-semibold"><i class="fa-solid fa-users mr-1"></i> ${onlineCount} Player(s) currently connected</span>`;
          }
        }
      } else {
        if (playersStatusElem) {
          playersStatusElem.textContent = '0 players online right now';
          playersStatusElem.className = 'text-slate-400 font-medium';
        }
        if (playersPulseDot) playersPulseDot.className = 'w-1.5 h-1.5 rounded-full bg-slate-500';
        if (cardPlayersList) {
          cardPlayersList.innerHTML = `<span class="text-[11px] text-slate-400 italic">0 players online right now (Waiting for warriors)</span>`;
        }
      }
    }

    async function fetchLiveServerStatus() {
      const refreshIcon = document.getElementById('refresh-icon');
      const statusText = document.getElementById('server-status-text');
      const statusBadge = document.getElementById('server-status-badge');
      const statusDot = document.getElementById('server-status-dot');
      const navStatusDot = document.getElementById('nav-status-dot');
      const telemetryDot = document.getElementById('telemetry-dot');
      const lastUpdatedElem = document.getElementById('last-updated-text');
      const serverVersionText = document.getElementById('server-version-text');
      const latencyBadge = document.getElementById('ping-latency-badge');

      if (refreshIcon) refreshIcon.classList.add('fa-spin');
      if (latencyBadge) latencyBadge.textContent = 'PINGING...';

      let isOnline = false;
      let onlinePlayers = 0;
      let maxPlayers = 50;
      let playerList = [];
      let versionInfo = 'Bedrock 1.20 - 1.21+ / Java';
      let protocolTag = 'BEDROCK';

      try {
        // Primary Query: Bedrock endpoint (basic.vitalcloud.in:19149)
        const bedrockRes = await fetch(`https://api.mcstatus.io/v2/status/bedrock/${BEDROCK_FULL_ADDRESS}`, { cache: 'no-store' });
        if (bedrockRes.ok) {
          const data = await bedrockRes.json();
          if (data && data.online) {
            isOnline = true;
            protocolTag = 'BEDROCK :19149';
            onlinePlayers = data.players?.online ?? 0;
            maxPlayers = data.players?.max ?? 50;
            playerList = data.players?.list || [];
            if (data.version?.name) {
              versionInfo = `Bedrock ${data.version.name} / Java`;
            }
          }
        }

        // Secondary Query: Java endpoint (basic.vitalcloud.in:19126)
        const javaRes = await fetch(`https://api.mcstatus.io/v2/status/java/${JAVA_FULL_ADDRESS}`, { cache: 'no-store' });
        if (javaRes.ok) {
          const jData = await javaRes.json();
          if (jData && jData.online) {
            isOnline = true;
            protocolTag = protocolTag.includes('BEDROCK') ? 'CROSSPLAY LIVE' : 'JAVA :19126';
            const jOnline = jData.players?.online ?? 0;
            if (jOnline > onlinePlayers) onlinePlayers = jOnline;
            if (jData.players?.max) maxPlayers = jData.players.max;
            if (jData.players?.list && jData.players.list.length > 0) {
              playerList = jData.players.list;
            }
            if (jData.version?.name_clean) {
              versionInfo = `Java ${jData.version.name_clean} / Bedrock`;
            }
          }
        }

        // Tertiary Fallback: mcsrvstat Bedrock API
        if (!isOnline) {
          const altRes = await fetch(`https://api.mcsrvstat.us/bedrock/3/${BEDROCK_FULL_ADDRESS}`, { cache: 'no-store' });
          if (altRes.ok) {
            const aData = await altRes.json();
            if (aData && aData.online) {
              isOnline = true;
              protocolTag = 'BEDROCK :19149';
              onlinePlayers = aData.players?.online ?? 0;
              maxPlayers = aData.players?.max ?? 50;
              playerList = aData.players?.list || [];
              if (aData.version) {
                versionInfo = `Bedrock ${aData.version}`;
              }
            }
          }
        }
      } catch (err) {
        console.warn('Live server status fetch error:', err);
      }

      if (isOnline) {
        if (statusText) statusText.textContent = 'ONLINE';
        if (statusBadge) statusBadge.className = 'font-bold flex items-center gap-2 text-base mt-1.5 text-emerald-400';
        if (statusDot) statusDot.className = 'w-2.5 h-2.5 rounded-full bg-emerald-400 shadow-[0_0_12px_#10b981] animate-ping';
        if (navStatusDot) navStatusDot.className = 'w-2 h-2 rounded-full bg-emerald-400 animate-ping';
        if (telemetryDot) telemetryDot.className = 'inline-block w-2 h-2 rounded-full bg-emerald-400 animate-ping';
        if (latencyBadge) {
          latencyBadge.textContent = protocolTag;
          latencyBadge.className = 'text-[10px] bg-emerald-950/90 border border-emerald-500/40 px-2 py-0.5 rounded text-emerald-300 font-mono';
        }
      } else {
        if (statusText) statusText.textContent = 'OFFLINE / STARTING';
        if (statusBadge) statusBadge.className = 'font-bold flex items-center gap-2 text-base mt-1.5 text-red-400';
        if (statusDot) statusDot.className = 'w-2.5 h-2.5 rounded-full bg-red-500 shadow-[0_0_10px_#ef4444]';
        if (navStatusDot) navStatusDot.className = 'w-2 h-2 rounded-full bg-red-500';
        if (telemetryDot) telemetryDot.className = 'inline-block w-2 h-2 rounded-full bg-red-500';
        if (latencyBadge) {
          latencyBadge.textContent = 'OFFLINE';
          latencyBadge.className = 'text-[10px] bg-red-950/80 border border-red-500/40 px-2 py-0.5 rounded text-red-300 font-mono';
        }
      }

      if (serverVersionText) serverVersionText.textContent = versionInfo;
      renderRealPlayers(onlinePlayers, maxPlayers, playerList);

      if (refreshIcon) refreshIcon.classList.remove('fa-spin');
      const now = new Date();
      const timeStr = now.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit', second: '2-digit' });
      if (lastUpdatedElem) lastUpdatedElem.textContent = `(Updated: ${timeStr})`;
    }

    function copyToClipboard(text, customMessage) {
      const tempInput = document.createElement('input');
      tempInput.style.position = 'absolute';
      tempInput.style.left = '-9999px';
      tempInput.value = text;
      document.body.appendChild(tempInput);
      tempInput.select();
      
      try {
        document.execCommand('copy');
        showToast(customMessage || 'Copied to clipboard!');
      } catch (err) {
        showToast('Failed to copy');
      }
      document.body.removeChild(tempInput);
    }

    let toastTimeout;
    function showToast(message) {
      const toast = document.getElementById('toast');
      const textElem = document.getElementById('toast-text');
      textElem.textContent = message;

      toast.classList.remove('translate-y-24', 'opacity-0');
      toast.classList.add('translate-y-0', 'opacity-100');

      clearTimeout(toastTimeout);
      toastTimeout = setTimeout(() => {
        toast.classList.remove('translate-y-0', 'opacity-100');
        toast.classList.add('translate-y-24', 'opacity-0');
      }, 3000);
    }

    // Expose functions globally for HTML inline event handlers
    window.copyToClipboard = copyToClipboard;
    window.fetchLiveServerStatus = fetchLiveServerStatus;
    window.handleProfileCircleClick = handleProfileCircleClick;
    window.openAuthModal = openAuthModal;
    window.dismissAuthModal = dismissAuthModal;
    window.switchAuthTab = switchAuthTab;
    window.handleGoogleSignIn = handleGoogleSignIn;
    window.handleAuthSubmit = handleAuthSubmit;
    window.logoutUser = logoutUser;

    // =========================================================================
    // PINEAPPLESMP AI SUPPORT ENGINE (GEMINI API + 3-LANGUAGE + TICKET ESCALATION)
    // =========================================================================
    let selectedAiLanguage = 'English';
    const aiConversationHistory = [];

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
      showToast(`AI Response Language set to ${lang}`);
    }

    function escapeHtml(str) {
      return str
        .replace(/&/g, '&amp;')
        .replace(/</g, '&lt;')
        .replace(/>/g, '&gt;')
        .replace(/"/g, '&quot;')
        .replace(/'/g, '&#039;');
    }

    function formatAiText(rawText) {
      const escaped = escapeHtml(rawText);
      return escaped
        .replace(/\*\*(.*?)\*\*/g, '<strong class="text-pineapple-300 font-bold">$1</strong>')
        .replace(/`(.*?)`/g, '<code class="bg-slate-950 text-emerald-300 px-1.5 py-0.5 rounded font-mono text-xs border border-slate-800">$1</code>')
        .replace(/\n/g, '<br>');
    }

    function appendChatMessage(sender, text, isErrorOrHelp = false) {
      const chatFeed = document.getElementById('ai-chat-messages');
      if (!chatFeed) return;

      const wrapper = document.createElement('div');
      if (sender === 'user') {
        wrapper.className = 'flex items-start justify-end gap-3';
        wrapper.innerHTML = `
          <div class="max-w-[85%] bg-gradient-to-r from-pineapple-500/20 to-emerald-500/20 border border-pineapple-500/50 rounded-2xl rounded-tr-none px-4 py-3 text-xs sm:text-sm text-white leading-relaxed shadow">
            ${escapeHtml(text)}
          </div>
          <div class="w-9 h-9 rounded-xl bg-slate-800 border border-pineapple-400/50 text-pineapple-300 font-bold flex items-center justify-center shrink-0">
            <i class="fa-solid fa-user"></i>
          </div>
        `;
      } else {
        wrapper.className = 'flex items-start gap-3';
        const ticketFooter = isErrorOrHelp
          ? `<div class="mt-3 pt-2.5 border-t border-slate-800 flex flex-wrap items-center justify-between gap-2 text-[11px] text-slate-400">
               <span>Not resolved yet? Our staff will help you directly:</span>
               <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-1.5 bg-[#5865F2] hover:bg-[#4752c4] text-white font-bold px-3 py-1.5 rounded-lg transition-colors shadow">
                 <i class="fa-brands fa-discord"></i>
                 <span>Create Ticket on Discord</span>
               </a>
             </div>`
          : '';

        wrapper.innerHTML = `
          <div class="w-9 h-9 rounded-xl bg-gradient-to-br from-pineapple-500 to-emerald-600 text-slate-950 font-black flex items-center justify-center shrink-0 shadow-md">
            <i class="fa-solid fa-robot"></i>
          </div>
          <div class="flex-1 bg-slate-900/95 border border-pineapple-500/35 rounded-2xl rounded-tl-none p-4 text-xs sm:text-sm text-slate-200 leading-relaxed shadow-md">
            <div class="flex items-center justify-between mb-1.5">
              <span class="text-[11px] font-extrabold uppercase tracking-wider text-pineapple-300">PineappleBot AI</span>
              <span class="text-[10px] font-mono px-2 py-0.5 rounded bg-slate-950 text-emerald-300 border border-slate-800">${selectedAiLanguage}</span>
            </div>
            <div>${formatAiText(text)}</div>
            ${ticketFooter}
          </div>
        `;
      }

      chatFeed.appendChild(wrapper);
      chatFeed.scrollTop = chatFeed.scrollHeight;
    }

    function buildLocalFallbackResponse(question, lang) {
      const q = question.toLowerCase();
      const isBedrock = q.includes('bedrock') || q.includes('pocket') || q.includes('mobile') || q.includes('port') || q.includes('19149');
      const isJava = q.includes('java') || q.includes('pc') || q.includes('19126');
      const isOutdated = q.includes('outdated') || q.includes('version');

      if (lang === 'Hindi') {
        if (isBedrock) {
          return `**PineappleSMP Bedrock / Pocket Edition विवरण:**\n1. **Server Name:** PineappleSMP\n2. **Server Address (IP):** \`basic.vitalcloud.in\`\n3. **Port:** \`19149\`\n4. **Status:** Season 1 Launched!\n\nयदि फिर भी कनेक्ट होने में कोई समस्या आती है, तो कृपया हमारे आधिकारिक Discord सर्वर (**https://discord.gg/Vp9Ss592cq**) पर जाकर Support Ticket बनाएं।`;
        }
        if (isJava) {
          return `**PineappleSMP Java Edition (PC) विवरण:**\n1. **Server Address:** \`basic.vitalcloud.in:19126\`\n2. **Supported Versions:** 1.19 से 1.21+\n3. **Status:** Season 1 Launched!\n\nयदि फिर भी कोई एरर आता है, तो कृपया हमारे Discord सर्वर (**https://discord.gg/Vp9Ss592cq**) पर Support Ticket खोलें।`;
        }
        if (isOutdated) {
          return `**Outdated Client / Server एरर कैसे ठीक करें:**\n1. अपने Minecraft ऐप या लॉन्चर को लेटेस्ट वर्जन (1.21+) पर अपडेट करें।\n2. सुनिश्चित करें कि आप सही IP और पोर्ट उपयोग कर रहे हैं — **Java:** \`basic.vitalcloud.in:19126\` | **Bedrock:** \`basic.vitalcloud.in\` (Port: \`19149\`)।\n3. गेम को पूरी तरह बंद करके दोबारा चालू करें।\n\nयदि इसके बाद भी समस्या हल नहीं होती है, तो कृपया हमारे Discord सर्वर (**https://discord.gg/Vp9Ss592cq**) पर Support Ticket बनाएं।`;
        }
        return `**Minecraft कनेक्शन एरर समाधान (Step-by-Step):**\n1. **IP और Port जांचें:** Java के लिए \`basic.vitalcloud.in:19126\` और Bedrock के लिए IP \`basic.vitalcloud.in\` व Port \`19149\` डालें (कोई एक्स्ट्रा स्पेस न रखें)।\n2. **इंटरनेट और DNS:** अपना Wi-Fi या मोबाइल डेटा रीस्टार्ट करें और VPN बंद रखें।\n3. **रीलॉगिन करें:** Minecraft को रीस्टार्ट करें और दोबारा जॉइन करने का प्रयास करें।\n\nयदि इन स्टेप्स के बाद भी समस्या हल नहीं होती है, तो कृपया हमारे Discord सर्वर (**https://discord.gg/Vp9Ss592cq**) पर जाकर एक **Support Ticket** बनाएं!`;
      }

      if (lang === 'Hinglish') {
        if (isBedrock) {
          return `**PineappleSMP Bedrock / Pocket Edition Details:**\n1. **Server Name:** PineappleSMP\n2. **Server Address (IP):** \`basic.vitalcloud.in\`\n3. **Port:** \`19149\`\n4. **Status:** Season 1 Launched!\n\nAgar phir bhi join karne me koi problem aaye, toh humare official Discord server (**https://discord.gg/Vp9Ss592cq**) par jakar Support Ticket zaroor banayein.`;
        }
        if (isJava) {
          return `**PineappleSMP Java Edition (PC) Details:**\n1. **Server Address:** \`basic.vitalcloud.in:19126\`\n2. **Supported Versions:** 1.19 se 1.21+\n3. **Status:** Season 1 Launched!\n\nAgar phir bhi koi error aaye, toh Discord server (**https://discord.gg/Vp9Ss592cq**) par Support Ticket open karein.`;
        }
        if (isOutdated) {
          return `**Outdated Client / Server Error Kaise Solve Karein:**\n1. Apne Minecraft game ko latest version (1.21+) par update karein.\n2. Sahi IP aur Port check karein — **Java:** \`basic.vitalcloud.in:19126\` | **Bedrock:** \`basic.vitalcloud.in\` (Port: \`19149\`).\n3. Game ko close karke restart karein.\n\nAgar iske baad bhi solve na ho toh humare Discord server (**https://discord.gg/Vp9Ss592cq**) par Support Ticket banayein!`;
        }
        return `**Minecraft Connection Error Fix (Step-by-Step):**\n1. **IP & Port Check Karein:** Java ke liye \`basic.vitalcloud.in:19126\` aur Bedrock ke liye IP \`basic.vitalcloud.in\` + Port \`19149\` bina kisi space ke enter karein.\n2. **Network & VPN:** Apna internet connection refresh karein aur agar koi VPN chal raha hai toh off karein.\n3. **Game Restart:** Minecraft close karke dubara open karein.\n\nAgar phir bhi problem solve nahi hoti hai, toh humare Discord server (**https://discord.gg/Vp9Ss592cq**) par jakar **Support Ticket** banayein — staff aapki turant help karega!`;
      }

      // Default English
      if (isBedrock) {
        return `**PineappleSMP Bedrock / Pocket Edition Connection Details:**\n1. **Server Name:** PineappleSMP\n2. **Server Address:** \`basic.vitalcloud.in\`\n3. **Port:** \`19149\`\n4. **Status:** Season 1 Launched!\n\nIf you still cannot connect, please open a **Support Ticket** on our official Discord server (**https://discord.gg/Vp9Ss592cq**).`;
      }
      if (isJava) {
        return `**PineappleSMP Java Edition (PC) Connection Details:**\n1. **Server Address:** \`basic.vitalcloud.in:19126\`\n2. **Supported Versions:** 1.19 – 1.21+\n3. **Status:** Season 1 Launched!\n\nIf you still face any connection issues, please create a **Support Ticket** on our official Discord server (**https://discord.gg/Vp9Ss592cq**).`;
      }
      if (isOutdated) {
        return `**How to Fix "Outdated Client / Outdated Server":**\n1. Update your Minecraft client (Bedrock or Java) to the latest supported release (**1.21+**).\n2. Verify you are entering the exact address — **Java:** \`basic.vitalcloud.in:19126\` | **Bedrock:** \`basic.vitalcloud.in\` (Port: \`19149\`).\n3. Restart Minecraft completely and try joining again.\n\nIf the issue is still not solved, please open a **Support Ticket** on our official Discord server (**https://discord.gg/Vp9Ss592cq**).`;
      }
      return `**Step-by-Step Troubleshooting Guide:**\n1. **Verify IP & Port:** For Java Edition use \`basic.vitalcloud.in:19126\`. For Bedrock/Pocket Edition use IP \`basic.vitalcloud.in\` and Port \`19149\` with no extra spaces.\n2. **Check Network & VPN:** Turn off any active VPN/proxy and toggle Airplane mode or restart your router.\n3. **Restart Minecraft:** Fully close Minecraft and relaunch it to refresh your session token.\n\nIf your issue is still not resolved after trying these steps, please open a **Support Ticket** on our official Discord server (**https://discord.gg/Vp9Ss592cq**) so our staff team can assist you directly!`;
    }

    async function queryGeminiSupportAI(userPrompt) {
      const apiKey = "";
      const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-3-flash-preview:generateContent?key=${apiKey}`;

      const languageInstruction =
        selectedAiLanguage === 'Hindi'
          ? 'You MUST reply strictly in clear Hindi (Devanagari script), keeping technical Minecraft terms, IPs, ports, and URLs in English.'
          : selectedAiLanguage === 'Hinglish'
          ? 'You MUST reply strictly in natural Hinglish (Hindi written in Roman English alphabet, friendly Indian gaming tone).'
          : 'You MUST reply strictly in clear, professional English.';

      const systemPrompt = `You are PineappleBot AI, the official 24/7 technical support and gameplay assistant for the PineappleSMP Minecraft Lifesteal server.
Official Server Facts:
- Server Name: PineappleSMP (Season 1 Launched)
- Game Mode: Lifesteal SMP (Kill = +1 Heart, Death = -1 Heart, Revive Beacons, Crossplay)
- Java Edition IP & Port: basic.vitalcloud.in:19126
- Bedrock / Pocket Edition IP: basic.vitalcloud.in | Port: 19149
- Official Discord Server: https://discord.gg/Vp9Ss592cq

Rules:
1. ${languageInstruction}
2. Whenever a user mentions ANY error, bug, lag, or connection problem, provide clear numbered step-by-step troubleshooting instructions to solve it.
3. Always clearly state at the end that if the issue is still not solved after trying the steps, they should open a support ticket on our official Discord server (https://discord.gg/Vp9Ss592cq).
4. Keep answers concise, structured with bullet/numbered steps, and helpful.`;

      aiConversationHistory.push({ role: 'user', parts: [{ text: userPrompt }] });
      const recentContents = aiConversationHistory.slice(-6);

      const payload = {
        contents: recentContents,
        systemInstruction: {
          parts: [{ text: systemPrompt }]
        }
      };

      const delays = [1000, 2000, 4000];
      for (let attempt = 0; attempt <= delays.length; attempt++) {
        try {
          const response = await fetch(apiUrl, {
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify(payload)
          });

          if (!response.ok) {
            if (attempt < delays.length && (response.status === 429 || response.status >= 500)) {
              await new Promise(res => setTimeout(res, delays[attempt]));
              continue;
            }
            throw new Error(`API status ${response.status}`);
          }

          const result = await response.json();
          const replyText = result?.candidates?.[0]?.content?.parts?.[0]?.text;
          if (replyText) {
            aiConversationHistory.push({ role: 'model', parts: [{ text: replyText }] });
            return replyText;
          }
          throw new Error('Empty AI candidate');
        } catch (err) {
          if (attempt < delays.length) {
            await new Promise(res => setTimeout(res, delays[attempt]));
            continue;
          }
          const fallback = buildLocalFallbackResponse(userPrompt, selectedAiLanguage);
          aiConversationHistory.push({ role: 'model', parts: [{ text: fallback }] });
          return fallback;
        }
      }
    }

    async function handleAiChatSubmit(e) {
      e.preventDefault();
      const inputEl = document.getElementById('ai-user-input');
      const sendBtn = document.getElementById('ai-send-btn');
      const chatFeed = document.getElementById('ai-chat-messages');
      if (!inputEl || !sendBtn) return;

      const userText = inputEl.value.trim();
      if (!userText) return;

      inputEl.value = '';
      inputEl.disabled = true;
      sendBtn.disabled = true;

      appendChatMessage('user', userText, false);

      // Typing indicator
      const typingId = 'ai-typing-' + Date.now();
      const typingDiv = document.createElement('div');
      typingDiv.id = typingId;
      typingDiv.className = 'flex items-center gap-3';
      typingDiv.innerHTML = `
        <div class="w-9 h-9 rounded-xl bg-gradient-to-br from-pineapple-500 to-emerald-600 text-slate-950 font-black flex items-center justify-center shrink-0">
          <i class="fa-solid fa-robot"></i>
        </div>
        <div class="bg-slate-900/95 border border-pineapple-500/35 rounded-2xl rounded-tl-none px-4 py-3 text-xs text-pineapple-300 flex items-center gap-2">
          <i class="fa-solid fa-spinner fa-spin"></i>
          <span>Analyzing &amp; preparing solution in ${selectedAiLanguage}...</span>
        </div>
      `;
      if (chatFeed) {
        chatFeed.appendChild(typingDiv);
        chatFeed.scrollTop = chatFeed.scrollHeight;
      }

      const reply = await queryGeminiSupportAI(userText);
      const existingTyping = document.getElementById(typingId);
      if (existingTyping) existingTyping.remove();

      appendChatMessage('ai', reply, true);

      inputEl.disabled = false;
      sendBtn.disabled = false;
      inputEl.focus();
    }

    function sendQuickAiPrompt(promptText) {
      const inputEl = document.getElementById('ai-user-input');
      const formEl = document.getElementById('ai-chat-form');
      if (!inputEl || !formEl) return;
      inputEl.value = promptText;
      formEl.dispatchEvent(new Event('submit', { cancelable: true, bubbles: true }));
    }

    window.setAiLanguage = setAiLanguage;
    window.handleAiChatSubmit = handleAiChatSubmit;
    window.sendQuickAiPrompt = sendQuickAiPrompt;
