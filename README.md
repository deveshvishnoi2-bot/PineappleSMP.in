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
          <span class="w-2 h-2 rounded-full bg-amber-400 animate-ping"></span>
          🍍 PINEAPPLE SMP — LAUNCHING SOON....
        </span>
        <span class="text-slate-600">|</span>
        <span class="flex items-center gap-2 text-amber-200">
          🚀 PREPARE YOUR GEAR!
        </span>
        <span class="text-slate-600">|</span>
        <span class="flex items-center gap-2 text-emerald-300">
          <i class="fa-solid fa-server text-pineapple-400"></i>
          🌐 IP &amp; PORT: <strong class="font-mono text-white">SOON</strong> (BEDROCK &amp; JAVA CROSSPLAY)
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
          <span class="w-2 h-2 rounded-full bg-amber-400 animate-ping"></span>
          🍍 PINEAPPLE SMP — LAUNCHING SOON....
        </span>
        <span class="text-slate-600">|</span>
        <span class="flex items-center gap-2 text-amber-200">
          🚀 PREPARE YOUR GEAR!
        </span>
        <span class="text-slate-600">|</span>
        <span class="flex items-center gap-2 text-emerald-300">
          <i class="fa-solid fa-server text-pineapple-400"></i>
          🌐 IP &amp; PORT: <strong class="font-mono text-white">SOON</strong> (BEDROCK &amp; JAVA CROSSPLAY)
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
      <!-- Far Right: Quick Status Pill, Discord & Circular Login / Profile Avatar Button -->
      <div class="ml-auto flex items-center justify-end gap-2.5 sm:gap-3">
        <button onclick="showToast('Server IP & Port dropping SOON on Discord!')" class="hidden md:flex items-center gap-2 bg-smpCard hover:bg-slate-800 text-slate-200 px-3.5 py-2 rounded-lg border border-pineapple-600/60 text-xs font-semibold tracking-wider transition-all hover:border-pineapple-400/80">
          <span id="nav-status-dot" class="w-2 h-2 rounded-full bg-amber-400 animate-pulse"></span>
          <span>IP &amp; PORT: <strong class="text-pineapple-300 font-mono">SOON</strong></span>
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
   