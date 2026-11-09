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
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@700;900&family=Inter:wght@400;500;600;700;800&family=Outfit:wght@600;800;900&display=swap" rel="stylesheet">
  
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
            smpDark: '#0B110D',
            smpCard: '#131D16',
            smpBorder: '#233829'
          },
          fontFamily: {
            heading: ['Outfit', 'sans-serif'],
            cinzel: ['Cinzel', 'serif'],
            sans: ['Inter', 'sans-serif']
          }
        }
      }
    }
  </script>
  <style>
    body {
      background-color: #070B08;
      color: #E2E8F0;
      overflow-x: hidden;
      font-family: 'Inter', sans-serif;
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
      animation: tickerSlide 26s linear infinite;
    }
    .ticker-wrapper:hover {
      animation-play-state: paused;
    }
  </style>
</head>
<body class="bg-smpDark text-slate-100 min-h-screen relative selection:bg-pineapple-500 selection:text-slate-900">

  <!-- Ambient Ambience Background -->
  <div class="fixed inset-0 bg-grid-pattern pointer-events-none opacity-50 z-0"></div>
  <div class="fixed top-0 left-1/2 -translate-x-1/2 w-[750px] h-[380px] bg-pineapple-500/15 blur-[150px] rounded-full pointer-events-none z-0"></div>
  <div class="fixed top-96 right-10 w-[450px] h-[450px] bg-jungle-500/10 blur-[130px] rounded-full pointer-events-none z-0"></div>

  <!-- TOP RUNNING NEWS TICKER -->
  <div class="sticky top-0 z-50 bg-gradient-to-r from-amber-950 via-slate-950 to-emerald-950 border-b border-pineapple-500/40 text-xs py-2 px-3 flex items-center overflow-hidden shadow-lg backdrop-blur-md">
    <div class="flex items-center gap-2 bg-gradient-to-r from-amber-500 to-emerald-500 text-slate-950 font-black uppercase px-3 py-1 rounded-md shrink-0 shadow-md z-10 text-[11px] tracking-wider animate-pulse">
      <i class="fa-solid fa-clock"></i> LAUNCHING SOON...
    </div>
    
    <div class="overflow-hidden whitespace-nowrap ml-3 flex-1 mask-linear">
      <div class="ticker-wrapper flex items-center gap-10 font-semibold text-slate-200">
        <div class="flex items-center gap-8">
          <span class="text-pineapple-300 font-extrabold flex items-center gap-1.5"><i class="fa-solid fa-sun text-yellow-400"></i> 🍍 PINEAPPLE SMP — LAUNCHING SOON...</span>
          <span class="text-slate-500">•</span>
          <span class="text-emerald-400 font-bold flex items-center gap-1.5"><i class="fa-solid fa-rocket text-emerald-400"></i> 🚀 PREPARE YOUR GEAR!</span>
          <span class="text-slate-500">•</span>
          <span class="text-indigo-300 font-bold flex items-center gap-1.5"><i class="fa-brands fa-discord text-indigo-400"></i> 💬 JOIN DISCORD FOR WHITELIST & IP DROP: discord.gg/Vp9Ss592cq</span>
          <span class="text-slate-500">•</span>
          <span class="text-amber-400 font-bold flex items-center gap-1.5"><i class="fa-solid fa-heart-pulse text-red-500 animate-pulse"></i> ⚔️ CUSTOM LIFESTEAL MECHANICS COMING SOON...</span>
          <span class="text-slate-500">•</span>
          <span class="text-pineapple-300 font-bold">🍍 STAY TUNED!</span>
        </div>
        
        <!-- Loop for continuous ticker -->
        <div class="flex items-center gap-8">
          <span class="text-pineapple-300 font-extrabold flex items-center gap-1.5"><i class="fa-solid fa-sun text-yellow-400"></i> 🍍 PINEAPPLE SMP — LAUNCHING SOON...</span>
          <span class="text-slate-500">•</span>
          <span class="text-emerald-400 font-bold flex items-center gap-1.5"><i class="fa-solid fa-rocket text-emerald-400"></i> 🚀 PREPARE YOUR GEAR!</span>
          <span class="text-slate-500">•</span>
          <span class="text-indigo-300 font-bold flex items-center gap-1.5"><i class="fa-brands fa-discord text-indigo-400"></i> 💬 JOIN DISCORD FOR WHITELIST & IP DROP: discord.gg/Vp9Ss592cq</span>
          <span class="text-slate-500">•</span>
          <span class="text-amber-400 font-bold flex items-center gap-1.5"><i class="fa-solid fa-heart-pulse text-red-500 animate-pulse"></i> ⚔️ CUSTOM LIFESTEAL MECHANICS COMING SOON...</span>
          <span class="text-slate-500">•</span>
          <span class="text-pineapple-300 font-bold">🍍 STAY TUNED!</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Notification Toast Container -->
  <div id="toast" class="fixed bottom-6 right-6 z-50 transform translate-y-24 opacity-0 transition-all duration-300 pointer-events-none flex items-center gap-3 bg-slate-900 border border-pineapple-500/50 text-white px-5 py-3.5 rounded-xl shadow-2xl">
    <i class="fa-solid fa-circle-check text-pineapple-400 text-lg"></i>
    <span id="toast-text" class="text-sm font-semibold tracking-wide">Server Launching Soon... Stay tuned on Discord!</span>
  </div>

  <!-- Navbar -->
  <header class="sticky top-[39px] z-40 backdrop-blur-md bg-smpDark/95 border-b border-smpBorder/90">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
      
      <!-- Brand Logo -->
      <a href="#home" class="flex items-center gap-3.5 group">
        <div class="w-12 h-12 sm:w-14 sm:h-14 flex items-center justify-center relative rounded-2xl overflow-hidden shadow-lg shadow-amber-500/30 border-2 border-pineapple-500/70 bg-gradient-to-br from-amber-950/80 via-slate-900 to-emerald-950 p-1 transition-transform duration-300 group-hover:scale-105">
          <img src="38470.png" alt="PineappleSMP Logo" class="w-full h-full object-contain filter drop-shadow-[0_0_8px_rgba(250,204,21,0.8)]" onerror="this.onerror=null; this.src='https://placehold.co/120x120/131D16/FACC15?text=🍍';">
        </div>
        <div class="flex flex-col">
          <span class="font-heading text-xl sm:text-2xl font-black text-transparent bg-clip-text bg-gradient-to-r from-pineapple-300 via-amber-300 to-emerald-400 tracking-wider">PINEAPPLE SMP</span>
          <span class="text-[10px] text-emerald-400 uppercase tracking-widest font-semibold flex items-center gap-1">
            <i class="fa-solid fa-clock text-amber-400 text-[9px]"></i> Launching Soon...
          </span>
        </div>
      </a>

      <!-- Navigation Links -->
      <nav class="hidden md:flex items-center gap-7">
        <a href="#home" class="text-slate-300 hover:text-pineapple-300 transition-colors text-sm font-medium">Home</a>
        <a href="#features" class="text-slate-300 hover:text-pineapple-300 transition-colors text-sm font-medium flex items-center gap-1.5">
          <i class="fa-solid fa-star text-xs text-pineapple-400"></i> Features
        </a>
        <a href="#info" class="text-slate-300 hover:text-pineapple-300 transition-colors text-sm font-medium">Server IP</a>
        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="text-slate-300 hover:text-[#5865F2] transition-colors text-sm font-medium flex items-center gap-1.5">
          <i class="fa-brands fa-discord text-base"></i> Discord
        </a>
      </nav>

      <!-- Server Quick Action -->
      <div class="flex items-center gap-3">
        <button onclick="showToast('Server Launching Soon... Join Discord for whitelist & IP drop!')" class="hidden sm:flex items-center gap-2 bg-smpCard hover:bg-slate-800 text-slate-200 px-4 py-2 rounded-lg border border-pineapple-600/60 text-xs font-semibold tracking-wider transition-all hover:border-pineapple-400/80">
          <span class="w-2 h-2 rounded-full bg-amber-400 animate-pulse"></span>
          <span>Status: <strong class="text-pineapple-300">Launching Soon...</strong></span>
          <i class="fa-solid fa-hourglass-half text-amber-400 ml-1"></i>
        </button>

        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="shine-btn bg-gradient-to-r from-[#5865F2] to-indigo-600 hover:from-[#4752c4] hover:to-indigo-500 text-white font-bold px-4 py-2 sm:px-5 sm:py-2.5 rounded-lg text-xs sm:text-sm shadow-md shadow-[#5865F2]/30 transition-all flex items-center gap-2">
          <i class="fa-brands fa-discord text-sm"></i>
          <span>Join Discord</span>
        </a>
      </div>
    </div>
  </header>

  <main class="relative z-10">

    <!-- Hero Section -->
    <section id="home" class="pt-8 pb-12 md:pt-14 md:pb-20 max-w-6xl mx-auto px-4 text-center">
      
      <!-- PineappleSMP Showcase Logo -->
      <div class="relative flex justify-center mb-6">
        <div class="relative w-56 h-56 sm:w-64 sm:h-64 md:w-80 md:h-80 animate-float flex items-center justify-center">
          <div class="absolute inset-0 bg-pineapple-500/25 blur-3xl rounded-full scale-95 pointer-events-none"></div>
          
          <div class="relative w-full h-full rounded-3xl p-4 bg-gradient-to-br from-amber-950/60 via-slate-950/90 to-emerald-950/70 border-2 border-pineapple-400/60 shadow-[0_0_55px_rgba(250,204,21,0.45)] flex items-center justify-center overflow-hidden backdrop-blur-md">
            <img src="38470.png" alt="PineappleSMP Mascot Logo" class="w-full h-full object-contain filter drop-shadow-[0_12px_24px_rgba(250,204,21,0.6)]" onerror="this.onerror=null; this.src='https://placehold.co/300x300/131D16/FACC15?text=PineappleSMP';">
          </div>
        </div>
      </div>

      <!-- Hero Headlines -->
      <div class="inline-flex items-center gap-2 bg-gradient-to-r from-amber-500/20 to-emerald-500/20 border border-pineapple-500/50 px-5 py-2 rounded-full text-pineapple-300 text-xs sm:text-sm font-black uppercase tracking-widest mb-5 shadow-[0_0_20px_rgba(250,204,21,0.3)] animate-pulse">
        <i class="fa-solid fa-hourglass-start text-amber-400"></i> LAUNCHING SOON... • SEASON 1 PREPARATIONS
      </div>

      <h1 class="text-4xl sm:text-6xl md:text-7xl font-extrabold font-heading text-white tracking-tight uppercase pineapple-text-glow leading-none">
        PINEAPPLE SMP <br/>
        <span class="text-transparent bg-clip-text bg-gradient-to-r from-pineapple-300 via-amber-300 to-emerald-400">LAUNCHING SOON...</span>
      </h1>
      
      <p class="mt-5 text-slate-300 max-w-2xl mx-auto text-base sm:text-lg leading-relaxed font-normal">
        Prepare your gear and gather your clan! The ultimate Lifesteal & Survival SMP experience is gearing up for its official release.
      </p>

      <!-- Quick Action Buttons -->
      <div class="mt-8 flex flex-wrap justify-center gap-4">
        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="shine-btn bg-gradient-to-r from-pineapple-500 via-amber-500 to-emerald-500 hover:from-pineapple-400 hover:to-emerald-400 text-slate-950 font-black px-6 py-3.5 rounded-xl text-sm transition-all shadow-lg shadow-amber-500/25 flex items-center gap-2">
          <i class="fa-solid fa-bell text-base"></i>
          <span>GET IP ON DISCORD (LAUNCHING SOON...)</span>
        </a>
        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="shine-btn bg-[#5865F2] hover:bg-[#4752c4] text-white font-extrabold px-6 py-3.5 rounded-xl text-sm transition-all shadow-lg shadow-[#5865F2]/25 flex items-center gap-2">
          <i class="fa-brands fa-discord text-lg"></i>
          <span>Join Community Discord</span>
        </a>
      </div>

      <!-- Live Server Metrics Bar with Dynamic Refresh -->
      <div class="mt-12 max-w-4xl mx-auto">
        <div class="flex items-center justify-between px-2 mb-2.5">
          <div class="flex items-center gap-2 text-xs text-slate-400">
            <span id="telemetry-dot" class="inline-block w-2 h-2 rounded-full bg-amber-400 animate-pulse"></span>
            <span>Server Status</span>
            <span id="last-updated-text" class="text-[11px] text-slate-500">(Launching Soon... on Discord)</span>
          </div>
          <button id="refresh-status-btn" onclick="fetchLiveServerStatus()" class="flex items-center gap-1.5 bg-slate-800/90 hover:bg-slate-700 text-pineapple-300 hover:text-white text-xs font-semibold px-3 py-1.5 rounded-lg border border-pineapple-700/60 transition-all hover:border-pineapple-400/80 shadow-sm active:scale-95">
            <i id="refresh-icon" class="fa-solid fa-arrows-rotate text-[11px]"></i>
            <span>Refresh Status</span>
          </button>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4 text-left">
          <!-- Server Status Card with Launching Soon Banner -->
          <div class="bg-smpCard/90 border border-smpBorder p-4 rounded-xl shadow-lg relative overflow-hidden group">
            <div class="text-xs text-slate-400 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Server Status</span>
              <i class="fa-solid fa-hourglass-half text-amber-400 text-xs animate-spin" style="animation-duration: 8s;"></i>
            </div>
            <div id="server-status-badge" class="font-bold flex items-center gap-2 text-base mt-1.5 text-amber-400">
              <span id="server-status-dot" class="w-2.5 h-2.5 rounded-full bg-amber-400 shadow-[0_0_10px_#f59e0b] animate-ping"></span>
              <span id="server-status-text">Launching Soon...</span>
            </div>
            <div id="server-version-text" class="text-[10px] text-slate-500 mt-1 font-mono truncate">IP & Port dropping in Discord</div>

            <!-- Stylized Callout Badge -->
            <div class="mt-3 pt-2.5 border-t border-slate-800/80 text-center">
              <div class="inline-block py-1 px-3 rounded-lg bg-gradient-to-r from-amber-600/30 via-pineapple-500/30 to-emerald-600/30 border border-pineapple-400/50 shadow-inner">
                <span class="font-heading font-black text-xs sm:text-sm tracking-widest text-transparent bg-clip-text bg-gradient-to-r from-pineapple-200 via-amber-300 to-emerald-200 animate-pulse drop-shadow-[0_0_8px_rgba(250,204,21,0.8)]">
                  LAUNCHING SOON...
                </span>
              </div>
              <div class="text-[10px] font-bold text-pineapple-300 mt-1 uppercase tracking-wider flex items-center justify-center gap-1">
                <span>Stay tuned in Discord for launch time!</span>
              </div>
            </div>
          </div>

          <!-- Real Players Online Tracker -->
          <div class="bg-smpCard/90 border border-smpBorder hover:border-pineapple-500/60 transition-all p-4 rounded-xl shadow-lg relative overflow-hidden group">
            <div class="text-xs text-slate-400 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Players Online</span>
              <i class="fa-solid fa-users text-pineapple-400 text-xs"></i>
            </div>
            <div class="flex items-baseline gap-1.5 mt-1">
              <span id="server-players-online" class="text-2xl font-black font-mono text-white tracking-tight">0</span>
              <span id="server-players-max" class="text-xs text-slate-500 font-mono">/ TBA</span>
            </div>
            <div class="text-[10px] text-amber-300 font-medium mt-0.5 flex items-center gap-1">
              <span id="players-pulse-dot" class="w-1.5 h-1.5 rounded-full bg-amber-400 animate-pulse"></span>
              <span id="server-players-status">Server Launching Soon...</span>
            </div>

            <!-- In-Card Username Roster -->
            <div class="mt-2.5 pt-2.5 border-t border-slate-800/80">
              <div class="text-[10px] uppercase font-bold text-slate-400 flex items-center justify-between mb-1.5">
                <span>Roster Status:</span>
                <span id="roster-count-tag" class="font-mono text-pineapple-300 text-[9px] bg-slate-900 px-1.5 py-0.5 rounded">SOON</span>
              </div>
              <div id="card-players-list" class="flex flex-wrap gap-1.5 max-h-24 overflow-y-auto pr-1">
                <span class="text-[11px] text-slate-400 italic">Join Discord to get notified when server goes live!</span>
              </div>
            </div>
          </div>

          <!-- SMP Mode Card -->
          <div class="bg-smpCard/90 border border-smpBorder p-4 rounded-xl shadow-lg relative overflow-hidden">
            <div class="text-xs text-slate-400 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Game Mode</span>
              <i class="fa-solid fa-heart text-red-500 text-xs"></i>
            </div>
            <div class="text-white font-bold text-base mt-1.5 flex items-center gap-1.5">
              <span class="text-red-500">❤️</span> Lifesteal SMP
            </div>
            <div class="text-[10px] text-slate-400 mt-1">Kill to steal hearts, die to lose</div>
          </div>

          <!-- Crossplay Info Card -->
          <div class="bg-smpCard/90 border border-smpBorder p-4 rounded-xl shadow-lg relative overflow-hidden">
            <div class="text-xs text-slate-400 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Platform</span>
              <i class="fa-solid fa-cubes text-emerald-400 text-xs"></i>
            </div>
            <div class="text-pineapple-300 font-bold text-base mt-1.5">Java & Bedrock</div>
            <div class="text-[10px] text-slate-400 mt-1">Crossplay Ready at Launch</div>
          </div>
        </div>
      </div>
    </section>

    <!-- SERVER FEATURES SECTION -->
    <section id="features" class="py-14 bg-smpDark relative">
      <div class="max-w-6xl mx-auto px-4 sm:px-6">
        
        <div class="text-center mb-12">
          <div class="inline-flex items-center gap-2 px-3.5 py-1 rounded-full bg-pineapple-500/10 border border-pineapple-500/30 text-pineapple-300 text-xs font-bold uppercase tracking-widest mb-3">
            <i class="fa-solid fa-star text-pineapple-400"></i> Why Choose PineappleSMP
          </div>
          <h2 class="text-3xl sm:text-5xl font-heading font-black text-white tracking-wide">
            SERVER FEATURES & PERKS
          </h2>
          <p class="text-slate-400 text-sm sm:text-base mt-3 max-w-xl mx-auto">
            Experience an optimized, fair, lag-free SMP environment crafted for intense PvP, friendly alliances, and endless adventure.
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          
          <!-- Feature 1 -->
          <div class="bg-smpCard border border-smpBorder hover:border-pineapple-500/60 rounded-2xl p-6 transition-all duration-300 hover:-translate-y-1 shadow-lg group">
            <div class="w-12 h-12 rounded-xl bg-amber-500/10 border border-amber-500/30 text-pineapple-400 flex items-center justify-center text-xl mb-4 group-hover:scale-110 transition-transform">
              <i class="fa-solid fa-heart-crack text-red-400"></i>
            </div>
            <h3 class="text-xl font-heading font-bold text-white mb-2">Custom Lifesteal</h3>
            <p class="text-xs sm:text-sm text-slate-300 leading-relaxed">
              Eliminate enemy players to steal their maximum health hearts. Revive fallen teammates with custom crafted revive beacons!
            </p>
          </div>

          <!-- Feature 2 -->
          <div class="bg-smpCard border border-smpBorder hover:border-emerald-500/60 rounded-2xl p-6 transition-all duration-300 hover:-translate-y-1 shadow-lg group">
            <div class="w-12 h-12 rounded-xl bg-emerald-500/10 border border-emerald-500/30 text-emerald-400 flex items-center justify-center text-xl mb-4 group-hover:scale-110 transition-transform">
              <i class="fa-solid fa-mobile-screen"></i>
            </div>
            <h3 class="text-xl font-heading font-bold text-white mb-2">Full Crossplay</h3>
            <p class="text-xs sm:text-sm text-slate-300 leading-relaxed">
              Join seamlessly from PC (Java Edition) or Mobile/Console (Bedrock Edition) with synchronized inventories and optimized combat.
            </p>
          </div>

          <!-- Feature 3 -->
          <div class="bg-smpCard border border-smpBorder hover:border-pineapple-500/60 rounded-2xl p-6 transition-all duration-300 hover:-translate-y-1 shadow-lg group">
            <div class="w-12 h-12 rounded-xl bg-pineapple-500/10 border border-pineapple-500/30 text-pineapple-400 flex items-center justify-center text-xl mb-4 group-hover:scale-110 transition-transform">
              <i class="fa-solid fa-shield-halved text-emerald-400"></i>
            </div>
            <h3 class="text-xl font-heading font-bold text-white mb-2">Anti-Cheat & 24/7 Uptime</h3>
            <p class="text-xs sm:text-sm text-slate-300 leading-relaxed">
              High performance server with low latency, strict fair-play anti-cheat, automatic backups, and 24/7 dedicated hosting.
            </p>
          </div>

        </div>

      </div>
    </section>

    <!-- SERVER DETAILS SECTION -->
    <section id="info" class="py-14 max-w-4xl mx-auto px-4 sm:px-6">
      <div class="text-center mb-10">
        <h3 class="text-2xl sm:text-3xl font-heading font-black text-white">HOW TO JOIN PINEAPPLE SMP</h3>
        <p class="text-amber-300 font-semibold text-sm mt-1">Server Launching Soon... IP & Port will be dropped in Discord first.</p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
        
        <!-- Java Card -->
        <div class="bg-smpCard border border-smpBorder p-6 rounded-2xl relative overflow-hidden">
          <div class="flex items-center justify-between mb-4">
            <span class="text-xs uppercase font-extrabold px-3 py-1 bg-pineapple-500/20 text-pineapple-300 border border-pineapple-500/40 rounded-lg">Java Edition</span>
            <span class="text-xs text-slate-400">1.19 - 1.21+</span>
          </div>
          <div class="text-xs text-slate-400 uppercase font-semibold">Server Address</div>
          <div class="mt-1 flex items-center justify-between bg-slate-900 p-3 rounded-xl border border-slate-800">
            <span class="font-mono font-bold text-amber-300 tracking-wide">Server Launching Soon...</span>
            <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="text-pineapple-400 hover:text-white transition-colors" title="Check Discord">
              <i class="fa-brands fa-discord"></i>
            </a>
          </div>
          <p class="text-xs text-slate-400 mt-3">Server Launching Soon... IP & Port will be dropped in Discord first.</p>
        </div>

        <!-- Bedrock / Pocket Edition Card -->
        <div class="bg-smpCard border border-smpBorder p-6 rounded-2xl relative overflow-hidden">
          <div class="flex items-center justify-between mb-4">
            <span class="text-xs uppercase font-extrabold px-3 py-1 bg-emerald-500/10 text-emerald-400 border border-emerald-500/30 rounded-lg">Bedrock / Mobile</span>
            <span class="text-xs text-slate-400">Latest Versions</span>
          </div>
          <div class="grid grid-cols-3 gap-2">
            <div class="col-span-2">
              <div class="text-xs text-slate-400 uppercase font-semibold">Server IP</div>
              <div class="mt-1 flex items-center justify-between bg-slate-900 p-3 rounded-xl border border-slate-800">
                <span class="font-mono font-bold text-amber-300 truncate text-xs sm:text-sm">Launching Soon...</span>
                <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="text-pineapple-400 hover:text-white" title="Check Discord">
                  <i class="fa-brands fa-discord"></i>
                </a>
              </div>
            </div>
            <div>
              <div class="text-xs text-slate-400 uppercase font-semibold">Port</div>
              <div class="mt-1 flex items-center justify-between bg-slate-900 p-3 rounded-xl border border-slate-800">
                <span class="font-mono font-bold text-pineapple-300 text-xs sm:text-sm">TBA</span>
                <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="text-pineapple-400 hover:text-white" title="Check Discord">
                  <i class="fa-brands fa-discord"></i>
                </a>
              </div>
            </div>
          </div>
          <p class="text-xs text-slate-400 mt-3">Server Launching Soon... IP & Port will be dropped in Discord first.</p>
        </div>

      </div>
    </section>

    <!-- COMMUNITY DISCORD CTA -->
    <section class="py-12 max-w-4xl mx-auto px-4 sm:px-6">
      <div class="bg-gradient-to-r from-amber-950/60 via-slate-900 to-emerald-950/70 border-2 border-pineapple-500/40 rounded-3xl p-8 sm:p-10 shadow-2xl text-center relative overflow-hidden">
        <div class="inline-flex p-3 rounded-2xl bg-indigo-500/20 text-[#5865F2] mb-3 text-3xl">
          <i class="fa-brands fa-discord"></i>
        </div>
        <h3 class="text-2xl sm:text-4xl font-heading font-black text-white">JOIN OUR OFFICIAL DISCORD</h3>
        <p class="text-slate-300 text-sm sm:text-base mt-2 max-w-xl mx-auto">
          Participate in community events, report issues, talk with fellow players, and stay updated on announcements!
        </p>
        <div class="mt-6">
          <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="shine-btn inline-flex items-center gap-2.5 bg-[#5865F2] hover:bg-[#4752c4] text-white font-extrabold px-8 py-4 rounded-xl text-sm sm:text-base transition-all shadow-xl shadow-[#5865F2]/30">
            <i class="fa-brands fa-discord text-xl"></i>
            <span>Join PineappleSMP Discord (discord.gg/Vp9Ss592cq) &rarr;</span>
          </a>
        </div>
      </div>
    </section>

  </main>

  <!-- Footer -->
  <footer class="border-t border-smpBorder/60 bg-slate-950 py-10 text-slate-500 text-xs">
    <div class="max-w-7xl mx-auto px-4 flex flex-col md:flex-row items-center justify-between gap-4">
      <div class="flex items-center gap-3">
        <div class="w-10 h-10 rounded-xl border border-pineapple-500/50 bg-gradient-to-br from-amber-950 to-slate-950 flex items-center justify-center p-1 shadow-md shadow-amber-500/20">
          <img src="38470.png" alt="PineappleSMP Footer Logo" class="w-full h-full object-contain" onerror="this.onerror=null; this.src='https://placehold.co/100x100/131D16/FACC15?text=🍍';">
        </div>
        <span class="font-heading font-bold text-slate-300 text-sm tracking-wider">PINEAPPLE SMP</span>
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

  <script>
    // Server connection is currently set to TBA pending new IP release
    const SERVER_HOST = null;
    const SERVER_PORT = null;

    function renderRealPlayers(onlineCount, maxCount, playerList) {
      const cardPlayersList = document.getElementById('card-players-list');
      const rosterCountTag = document.getElementById('roster-count-tag');
      const playersOnlineElem = document.getElementById('server-players-online');
      const playersMaxElem = document.getElementById('server-players-max');
      const playersStatusElem = document.getElementById('server-players-status');
      const playersPulseDot = document.getElementById('players-pulse-dot');

      if (playersOnlineElem) playersOnlineElem.textContent = '0';
      if (playersMaxElem) playersMaxElem.textContent = '/ TBA';
      if (rosterCountTag) rosterCountTag.textContent = 'SOON';

      if (playersStatusElem) playersStatusElem.textContent = 'Server Launching Soon...';
      if (playersPulseDot) {
        playersPulseDot.className = 'w-1.5 h-1.5 rounded-full bg-amber-400 animate-pulse';
      }

      if (cardPlayersList) {
        cardPlayersList.innerHTML = `<span class="text-[11px] text-slate-400 italic">Join Discord to get notified when server goes live! <a href="https://discord.gg/Vp9Ss592cq" target="_blank" class="text-pineapple-400 underline font-semibold">discord.gg/Vp9Ss592cq</a></span>`;
      }
    }

    async function fetchLiveServerStatus() {
      const refreshIcon = document.getElementById('refresh-icon');
      const statusText = document.getElementById('server-status-text');
      const statusBadge = document.getElementById('server-status-badge');
      const statusDot = document.getElementById('server-status-dot');
      const telemetryDot = document.getElementById('telemetry-dot');
      const lastUpdatedElem = document.getElementById('last-updated-text');
      const serverVersionText = document.getElementById('server-version-text');

      if (refreshIcon) refreshIcon.classList.add('fa-spin');

      setTimeout(() => {
        if (statusText) statusText.textContent = 'Launching Soon...';
        if (statusBadge) statusBadge.className = 'font-bold flex items-center gap-2 text-base mt-1.5 text-amber-400';
        if (statusDot) statusDot.className = 'w-2.5 h-2.5 rounded-full bg-amber-400 shadow-[0_0_10px_#f59e0b] animate-ping';
        if (telemetryDot) telemetryDot.className = 'inline-block w-2 h-2 rounded-full bg-amber-400 animate-pulse';
        if (serverVersionText) serverVersionText.textContent = 'IP & Port dropping in Discord';

        renderRealPlayers(0, null, []);

        if (refreshIcon) refreshIcon.classList.remove('fa-spin');
        const now = new Date();
        const timeStr = now.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit', second: '2-digit' });
        if (lastUpdatedElem) lastUpdatedElem.textContent = `(Checked: ${timeStr})`;
      }, 500);
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

    window.addEventListener('DOMContentLoaded', () => {
      fetchLiveServerStatus();
    });
  </script>
</body>
</html>
