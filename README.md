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
      <i class="fa-solid fa-clock"></i> LAUNCHING SOON....
    </div>
    
    <div class="overflow-hidden whitespace-nowrap ml-3 flex-1 mask-linear">
      <div class="ticker-wrapper flex items-center gap-10 font-semibold text-slate-200">
        <div class="flex items-center gap-8">
          <span class="text-pineapple-300 font-extrabold flex items-center gap-1.5"><i class="fa-solid fa-sun text-yellow-400"></i> 🍍 PINEAPPLE SMP — LAUNCHING SOON....</span>
          <span class="text-slate-500">•</span>
          <span class="text-emerald-400 font-bold flex items-center gap-1.5"><i class="fa-solid fa-network-wired"></i> 🌐 IP: basic.vitalcloud.in</span>
          <span class="text-slate-500">•</span>
          <span class="text-amber-400 font-bold flex items-center gap-1.5"><i class="fa-solid fa-plug"></i> 🔌 PORT: 19174</span>
          <span class="text-slate-500">•</span>
          <span class="text-indigo-300 font-bold flex items-center gap-1.5"><i class="fa-brands fa-discord text-indigo-400"></i> 💬 JOIN DISCORD: discord.gg/Vp9Ss592cq</span>
          <span class="text-slate-500">•</span>
          <span class="text-red-400 font-bold flex items-center gap-1.5"><i class="fa-solid fa-heart-pulse"></i> ⚔️ CUSTOM LIFESTEAL & COMMUNITY SURVIVAL</span>
        </div>
        
        <!-- Loop for continuous ticker -->
        <div class="flex items-center gap-8">
          <span class="text-pineapple-300 font-extrabold flex items-center gap-1.5"><i class="fa-solid fa-sun text-yellow-400"></i> 🍍 PINEAPPLE SMP — LAUNCHING SOON....</span>
          <span class="text-slate-500">•</span>
          <span class="text-emerald-400 font-bold flex items-center gap-1.5"><i class="fa-solid fa-network-wired"></i> 🌐 IP: basic.vitalcloud.in</span>
          <span class="text-slate-500">•</span>
          <span class="text-amber-400 font-bold flex items-center gap-1.5"><i class="fa-solid fa-plug"></i> 🔌 PORT: 19174</span>
          <span class="text-slate-500">•</span>
          <span class="text-indigo-300 font-bold flex items-center gap-1.5"><i class="fa-brands fa-discord text-indigo-400"></i> 💬 JOIN DISCORD: discord.gg/Vp9Ss592cq</span>
          <span class="text-slate-500">•</span>
          <span class="text-red-400 font-bold flex items-center gap-1.5"><i class="fa-solid fa-heart-pulse"></i> ⚔️ CUSTOM LIFESTEAL & COMMUNITY SURVIVAL</span>
        </div>
      </div>
    </div>
  </div>

  <!-- Notification Toast Container -->
  <div id="toast" class="fixed bottom-6 right-6 z-50 transform translate-y-24 opacity-0 transition-all duration-300 pointer-events-none flex items-center gap-3 bg-slate-900 border border-pineapple-500/50 text-white px-5 py-3.5 rounded-xl shadow-2xl">
    <i class="fa-solid fa-circle-check text-pineapple-400 text-lg"></i>
    <span id="toast-text" class="text-sm font-semibold tracking-wide">Copied to clipboard!</span>
  </div>

  <!-- Navbar -->
  <header class="sticky top-[39px] z-40 backdrop-blur-md bg-smpDark/95 border-b border-smpBorder/90">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
      
      <!-- Brand Logo -->
      <a href="#home" class="flex items-center gap-3.5 group">
        <div class="w-12 h-12 sm:w-14 sm:h-14 flex items-center justify-center relative rounded-2xl overflow-hidden shadow-lg shadow-amber-500/30 border-2 border-pineapple-500/70 bg-gradient-to-br from-amber-950/80 via-slate-900 to-emerald-950 p-1 transition-transform duration-300 group-hover:scale-105">
          <img src="38452.png" alt="PineappleSMP Logo" class="w-full h-full object-contain filter drop-shadow-[0_0_8px_rgba(250,204,21,0.8)]" onerror="renderSvgLogoFallback(this)">
        </div>
        <div class="flex flex-col">
          <span class="font-heading text-xl sm:text-2xl font-black text-transparent bg-clip-text bg-gradient-to-r from-pineapple-300 via-amber-300 to-emerald-400 tracking-wider">PINEAPPLE SMP</span>
          <span class="text-[10px] text-emerald-400 uppercase tracking-widest font-semibold flex items-center gap-1">
            <span class="w-1.5 h-1.5 rounded-full bg-emerald-400 animate-pulse"></span> Bedrock & Java Crossplay
          </span>
        </div>
      </a>

      <!-- Navigation Links -->
      <nav class="hidden md:flex items-center gap-7">
        <a href="#home" class="text-slate-300 hover:text-pineapple-300 transition-colors text-sm font-medium">Home</a>
        <a href="#status" class="text-slate-300 hover:text-pineapple-300 transition-colors text-sm font-medium">Status</a>
        <a href="#join-guide" class="text-slate-300 hover:text-pineapple-300 transition-colors text-sm font-medium flex items-center gap-1.5">
          <i class="fa-solid fa-gamepad text-xs text-pineapple-400"></i> Join Bedrock
        </a>
        <a href="#features" class="text-slate-300 hover:text-pineapple-300 transition-colors text-sm font-medium">Features</a>
        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="text-slate-300 hover:text-[#5865F2] transition-colors text-sm font-medium flex items-center gap-1.5">
          <i class="fa-brands fa-discord text-base"></i> Discord
        </a>
      </nav>

      <!-- Server Quick Action -->
      <div class="flex items-center gap-3">
        <button onclick="copyToClipboard('basic.vitalcloud.in', 'Server IP Copied: basic.vitalcloud.in')" class="hidden sm:flex items-center gap-2 bg-smpCard hover:bg-slate-800 text-slate-200 px-4 py-2 rounded-lg border border-pineapple-600/60 text-xs font-semibold tracking-wider transition-all hover:border-pineapple-400/80">
          <span id="nav-status-dot" class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
          <span>IP: <strong class="text-pineapple-300 font-mono">basic.vitalcloud.in</strong></span>
          <i class="fa-regular fa-copy text-pineapple-400 ml-1"></i>
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
      
      <!-- PineappleSMP Mascot Crest (with vector SVG fallback) -->
      <div class="relative flex justify-center mb-6">
        <div class="relative w-56 h-56 sm:w-64 sm:h-64 md:w-80 md:h-80 animate-float flex items-center justify-center">
          <div class="absolute inset-0 bg-pineapple-500/25 blur-3xl rounded-full scale-95 pointer-events-none"></div>
          
          <div id="hero-logo-box" class="relative w-full h-full rounded-3xl p-4 bg-gradient-to-br from-amber-950/60 via-slate-950/90 to-emerald-950/70 border-2 border-pineapple-400/60 shadow-[0_0_55px_rgba(250,204,21,0.45)] flex items-center justify-center overflow-hidden backdrop-blur-md">
            <img src="38452.png" alt="PineappleSMP Mascot Crest" class="w-full h-full object-contain filter drop-shadow-[0_12px_24px_rgba(250,204,21,0.6)]" onerror="renderSvgLogoFallback(this)">
          </div>
        </div>
      </div>

      <!-- Hero Headlines -->
      <div class="inline-flex items-center gap-2 bg-gradient-to-r from-amber-500/20 to-emerald-500/20 border border-pineapple-500/50 px-5 py-2 rounded-full text-pineapple-300 text-xs sm:text-sm font-black uppercase tracking-widest mb-5 shadow-[0_0_20px_rgba(250,204,21,0.3)]">
        <i class="fa-solid fa-cube text-emerald-400"></i> BEDROCK (POCKET / CONSOLE / WIN10) + JAVA CROSSPLAY
      </div>

      <h1 class="text-4xl sm:text-6xl md:text-7xl font-extrabold font-heading text-white tracking-tight uppercase pineapple-text-glow leading-none">
        PINEAPPLE SMP <br/>
        <span class="text-transparent bg-clip-text bg-gradient-to-r from-pineapple-300 via-amber-300 to-emerald-400">LAUNCHING SOON....</span>
      </h1>
      
      <p class="mt-5 text-slate-300 max-w-2xl mx-auto text-base sm:text-lg leading-relaxed font-normal">
        Get ready for the ultimate Minecraft Lifesteal SMP adventure. Connect with the community while the server is Launching Soon....!
      </p>

      <!-- Quick Join Buttons -->
      <div class="mt-8 flex flex-wrap justify-center gap-4">
        <button onclick="copyToClipboard('basic.vitalcloud.in', 'Server IP Copied: basic.vitalcloud.in')" class="shine-btn bg-gradient-to-r from-pineapple-500 via-amber-500 to-emerald-500 hover:from-pineapple-400 hover:to-emerald-400 text-slate-950 font-black px-6 py-3.5 rounded-xl text-sm transition-all shadow-lg shadow-amber-500/25 flex items-center gap-2">
          <i class="fa-regular fa-copy text-base"></i>
          <span>COPY SERVER IP</span>
        </button>
        <button onclick="copyToClipboard('19174', 'Bedrock Port Copied: 19174')" class="shine-btn bg-slate-800 hover:bg-slate-700 text-pineapple-300 border border-pineapple-500/60 font-bold px-6 py-3.5 rounded-xl text-sm transition-all shadow-md flex items-center gap-2">
          <i class="fa-solid fa-plug text-sm text-emerald-400"></i>
          <span>COPY PORT (19174)</span>
        </button>
        <a href="https://discord.gg/Vp9Ss592cq" target="_blank" rel="noopener noreferrer" class="shine-btn bg-[#5865F2] hover:bg-[#4752c4] text-white font-extrabold px-6 py-3.5 rounded-xl text-sm transition-all shadow-lg shadow-[#5865F2]/25 flex items-center gap-2">
          <i class="fa-brands fa-discord text-lg"></i>
          <span>Join Discord</span>
        </a>
      </div>

      <!-- Live Server Metrics Bar with Direct API Integration -->
      <div id="status" class="mt-12 max-w-4xl mx-auto">
        <div class="flex items-center justify-between px-2 mb-2.5">
          <div class="flex items-center gap-2 text-xs text-slate-400">
            <span id="telemetry-dot" class="inline-block w-2 h-2 rounded-full bg-amber-400 animate-pulse"></span>
            <span>Server Status</span>
            <span id="last-updated-text" class="text-[11px] text-slate-500 font-mono">(Preparing Launch...)</span>
          </div>
          <button id="refresh-status-btn" onclick="fetchLiveServerStatus()" class="flex items-center gap-1.5 bg-slate-800/90 hover:bg-slate-700 text-pineapple-300 hover:text-white text-xs font-semibold px-3 py-1.5 rounded-lg border border-pineapple-700/60 transition-all hover:border-pineapple-400/80 shadow-sm active:scale-95">
            <i id="refresh-icon" class="fa-solid fa-arrows-rotate text-[11px]"></i>
            <span>Check Status</span>
          </button>
        </div>

        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-4 text-left">
          
          <!-- Server Status Card -->
          <div class="bg-smpCard/90 border border-smpBorder p-4 rounded-xl shadow-lg relative overflow-hidden group">
            <div class="text-xs text-slate-400 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Server Status</span>
              <span id="ping-latency-badge" class="text-[10px] bg-slate-800 px-2 py-0.5 rounded text-amber-300 font-mono">Upcoming</span>
            </div>
            <div id="server-status-badge" class="font-bold flex items-center gap-2 text-base mt-1.5 text-amber-400">
              <span id="server-status-dot" class="w-2.5 h-2.5 rounded-full bg-amber-400 shadow-[0_0_10px_#f59e0b] animate-pulse"></span>
              <span id="server-status-text">Launching Soon....</span>
            </div>
            <div id="server-version-text" class="text-[10px] text-slate-400 mt-1 font-mono truncate">Bedrock 1.20 - 1.21+ / Java</div>

            <!-- Stylized Callout Badge -->
            <div class="mt-3 pt-2.5 border-t border-slate-800/80 text-center">
              <div class="inline-block py-1 px-3 rounded-lg bg-gradient-to-r from-amber-600/30 via-pineapple-500/30 to-emerald-600/30 border border-pineapple-400/50 shadow-inner">
                <span class="font-heading font-black text-xs sm:text-sm tracking-widest text-transparent bg-clip-text bg-gradient-to-r from-pineapple-200 via-amber-300 to-emerald-200 animate-pulse drop-shadow-[0_0_8px_rgba(250,204,21,0.8)]">
                  LAUNCHING SOON....
                </span>
              </div>
              <div class="text-[10px] font-bold text-amber-400 mt-1 uppercase tracking-wider flex items-center justify-center gap-1">
                <span>⚔️ Prepare For Battle ⚔️</span>
              </div>
            </div>
          </div>

          <!-- Real Players Online Tracker -->
          <div class="bg-smpCard/90 border border-smpBorder hover:border-pineapple-500/60 transition-all p-4 rounded-xl shadow-lg relative overflow-hidden group">
            <div class="text-xs text-slate-400 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Players Waiting</span>
              <i class="fa-solid fa-users text-pineapple-400 text-xs"></i>
            </div>
            <div class="flex items-baseline gap-1.5 mt-1">
              <span id="server-players-online" class="text-2xl font-black font-mono text-white tracking-tight">0</span>
              <span id="server-players-max" class="text-xs text-slate-500 font-mono">/ 50</span>
            </div>
            <div class="text-[10px] text-amber-300 font-medium mt-0.5 flex items-center gap-1">
              <span id="players-pulse-dot" class="w-1.5 h-1.5 rounded-full bg-amber-400 animate-pulse"></span>
              <span id="server-players-status">Launching Soon....</span>
            </div>

            <!-- In-Card Username Roster -->
            <div class="mt-2.5 pt-2.5 border-t border-slate-800/80">
              <div class="text-[10px] uppercase font-bold text-slate-400 flex items-center justify-between mb-1.5">
                <span>Roster:</span>
                <span id="roster-count-tag" class="font-mono text-pineapple-300 text-[9px] bg-slate-900 px-1.5 py-0.5 rounded">WAITLIST</span>
              </div>
              <div id="card-players-list" class="flex flex-wrap gap-1.5 max-h-24 overflow-y-auto pr-1">
                <span class="text-[11px] text-slate-400 italic">Server is Launching Soon.... Join Discord!</span>
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
            <div class="text-[10px] text-slate-400 mt-1">Kill = +1 Heart | Death = -1 Heart</div>
          </div>

          <!-- Crossplay Info Card -->
          <div class="bg-smpCard/90 border border-smpBorder p-4 rounded-xl shadow-lg relative overflow-hidden">
            <div class="text-xs text-slate-400 uppercase tracking-wider font-semibold flex items-center justify-between">
              <span>Port Details</span>
              <i class="fa-solid fa-plug text-emerald-400 text-xs"></i>
            </div>
            <div class="text-pineapple-300 font-mono font-bold text-base mt-1.5">19174</div>
            <div class="text-[10px] text-emerald-400 mt-1">Bedrock Dedicated Po
