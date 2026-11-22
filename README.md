<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PineappleSMP | Lifesteal Minecraft Server & Store</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&family=Press+Start+2P&family=Space+Grotesk:wght@600;700&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        display: ['"Space Grotesk"', 'sans-serif'],
                        pixel: ['"Press Start 2P"', 'cursive'],
                    },
                    colors: {
                        pineapple: {
                            400: '#fde047',
                            500: '#facc15',
                            600: '#eab308',
                            700: '#ca8a04',
                        },
                        obsidian: {
                            950: '#09090b',
                            900: '#101014',
                            850: '#16161d',
                            800: '#1e1e26',
                            700: '#2a2a36',
                        }
                    },
                    animation: {
                        'marquee': 'marquee 15s linear infinite',
                        'float': 'float 4s ease-in-out infinite',
                        'pulse-slow': 'pulse 3s cubic-bezier(0.4, 0, 0.6, 1) infinite',
                    },
                    keyframes: {
                        marquee: {
                            '0%': { transform: 'translateX(0%)' },
                            '100%': { transform: 'translateX(-50%)' },
                        },
                        float: {
                            '0%, 100%': { transform: 'translateY(0px)' },
                            '50%': { transform: 'translateY(-10px)' },
                        }
                    }
                }
            }
        }
    </script>
    <style>
        /* Custom utilities for pixel-inspired beveled buttons and subtle grid background */
        body {
            background-color: #09090b;
            color: #f4f4f5;
            background-image: 
                radial-gradient(circle at 50% 0%, rgba(250, 204, 21, 0.08) 0%, transparent 55%),
                linear-gradient(to right, rgba(255, 255, 255, 0.025) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(255, 255, 255, 0.025) 1px, transparent 1px);
            background-size: 100% 100%, 36px 36px, 36px 36px;
        }

        .mc-btn {
            box-shadow: inset 0 2px 0 rgba(255,255,255,0.35), inset 0 -4px 0 rgba(0,0,0,0.4), 0 4px 12px rgba(250, 204, 21, 0.2);
            transition: transform 0.12s ease, box-shadow 0.12s ease, filter 0.12s ease;
        }
        .mc-btn:hover {
            filter: brightness(1.06);
            transform: translateY(-1px);
        }
        .mc-btn:active {
            transform: translateY(2px);
            box-shadow: inset 0 2px 0 rgba(0,0,0,0.2), inset 0 -1px 0 rgba(0,0,0,0.4);
        }

        .mc-btn-dark {
            box-shadow: inset 0 2px 0 rgba(255,255,255,0.08), inset 0 -4px 0 rgba(0,0,0,0.6);
            transition: transform 0.12s ease, background-color 0.15s ease;
        }
        .mc-btn-dark:active {
            transform: translateY(2px);
        }

        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #101014;
        }
        ::-webkit-scrollbar-thumb {
            background: #2a2a36;
            border-radius: 9999px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #facc15;
        }
    </style>
</head>
<body class="antialiased selection:bg-pineapple-500 selection:text-obsidian-950 overflow-x-hidden">

    <!-- Toast Notification Container (Replaces alert) -->
    <div id="toast-container" class="fixed top-14 right-4 z-50 flex flex-col gap-2 pointer-events-none"></div>

    <!-- 1. Top Scrolling News Ticker -->
    <div class="bg-pineapple-500 text-obsidian-950 font-bold text-xs sm:text-sm py-2 overflow-hidden border-b-2 border-pineapple-700 relative z-40">
        <div class="flex whitespace-nowrap animate-marquee hover:[animation-play-state:paused]">
            <div class="flex items-center space-x-8 px-4">
                <span class="inline-flex items-center gap-2">
                    <span class="px-2 py-0.5 bg-obsidian-950 text-pineapple-400 rounded text-[10px] font-pixel uppercase">EVENT</span>
                    MEGA PVP TOURNAMENT ON NOVEMBER 29, 2026 — WIN ENDER KITS & EXCLUSIVE RANKS!
                </span>
                <span>🍍</span>
                <span class="inline-flex items-center gap-2">
                    <span class="px-2 py-0.5 bg-emerald-950 text-emerald-300 rounded text-[10px] font-pixel uppercase">LIVE</span>
                    PINEAPPLESMP SEASON 1 IS OFFICIALLY LIVE — STEAL HEARTS, DOMINATE THE END!
                </span>
                <span>⚔️</span>
                <span class="inline-flex items-center gap-2">
                    <span class="px-2 py-0.5 bg-obsidian-950 text-pineapple-400 rounded text-[10px] font-pixel uppercase">CROSSPLAY</span>
                    JAVA & BEDROCK SUPPORTED (1.20 - 1.21+) • LOW PING INDIAN HOSTING!
                </span>
                <span>🍍</span>
            </div>
            <!-- Duplicated content for seamless infinite loop -->
            <div class="flex items-center space-x-8 px-4">
                <span class="inline-flex items-center gap-2">
                    <span class="px-2 py-0.5 bg-obsidian-950 text-pineapple-400 rounded text-[10px] font-pixel uppercase">EVENT</span>
                    MEGA PVP TOURNAMENT ON NOVEMBER 29, 2026 — WIN ENDER KITS & EXCLUSIVE RANKS!
                </span>
                <span>🍍</span>
                <span class="inline-flex items-center gap-2">
                    <span class="px-2 py-0.5 bg-emerald-950 text-emerald-300 rounded text-[10px] font-pixel uppercase">LIVE</span>
                    PINEAPPLESMP SEASON 1 IS OFFICIALLY LIVE — STEAL HEARTS, DOMINATE THE END!
                </span>
                <span>⚔️</span>
                <span class="inline-flex items-center gap-2">
                    <span class="px-2 py-0.5 bg-obsidian-950 text-pineapple-400 rounded text-[10px] font-pixel uppercase">CROSSPLAY</span>
                    JAVA & BEDROCK SUPPORTED (1.20 - 1.21+) • LOW PING INDIAN HOSTING!
                </span>
                <span>🍍</span>
            </div>
        </div>
    </div>

    <!-- Navigation Bar -->
    <header class="sticky top-0 z-30 bg-obsidian-950/85 backdrop-blur-md border-b border-zinc-800/80">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
            <a href="#" class="flex items-center gap-3 group">
                <!-- Blocky Minecraft Pineapple with Z-Black Sunglasses Navbar Icon -->
                <div class="w-11 h-11 rounded-xl bg-gradient-to-br from-obsidian-800 to-obsidian-950 border border-pineapple-500/50 flex items-center justify-center group-hover:border-pineapple-400 group-hover:shadow-[0_0_15px_rgba(250,204,21,0.35)] transition p-1">
                    <svg class="w-full h-full" viewBox="0 0 32 32" fill="none" shape-rendering="crispEdges">
                        <!-- Spiky Green Crown Leaves -->
                        <polygon points="16,1 13,9 19,9" fill="#22c55e" stroke="#052e16" stroke-width="1"/>
                        <polygon points="10,4 11,10 15,9" fill="#16a34a" stroke="#052e16" stroke-width="1"/>
                        <polygon points="22,4 21,10 17,9" fill="#16a34a" stroke="#052e16" stroke-width="1"/>
                        <!-- Blocky Yellow Pineapple Cube -->
                        <rect x="7" y="9" width="14" height="17" rx="1.5" fill="#facc15" stroke="#422006" stroke-width="1.5"/>
                        <!-- 3D Side Shading -->
                        <polygon points="21,9 25,11 25,27 21,26" fill="#ca8a04" stroke="#422006" stroke-width="1.2"/>
                        <!-- Cross-Hatch Pineapple Grid -->
                        <path d="M9 12L14 16L19 12M9 19L14 23L19 19" stroke="#d97706" stroke-width="1.1"/>
                        <!-- Z-Black Pixel Sunglasses -->
                        <rect x="7" y="13.5" width="14" height="1.5" fill="#09090b"/>
                        <rect x="8.5" y="13" width="5" height="3.5" fill="#050507" stroke="#000000" stroke-width="0.6"/>
                        <rect x="14.5" y="13" width="5" height="3.5" fill="#050507" stroke="#000000" stroke-width="0.6"/>
                        <!-- Sleek Z-Black Glint -->
                        <rect x="9.5" y="13.8" width="1.2" height="1" fill="#52525b"/>
                        <rect x="15.5" y="13.8" width="1.2" height="1" fill="#52525b"/>
                        <!-- Cute Happy Mouth -->
                        <rect x="12" y="19" width="4" height="2" fill="#271204"/>
                        <rect x="13" y="20" width="2" height="1" fill="#f87171"/>
                    </svg>
                </div>
                <span class="font-display font-extrabold text-xl tracking-tight text-white">
                    Pineapple<span class="text-pineapple-400">SMP</span>
                </span>
            </a>

            <nav class="hidden md:flex items-center gap-8 text-sm font-semibold text-zinc-400">
                <a href="#status" class="hover:text-pineapple-400 transition">Live Status</a>
                <a href="#store" class="hover:text-pineapple-400 transition">Kit Store</a>
                <a href="#community" class="hover:text-pineapple-400 transition">Top Funders & Staff</a>
                <a href="#rules" class="hover:text-pineapple-400 transition">Lifesteal Info</a>
            </nav>

            <div class="flex items-center gap-3">
                <a href="#store" class="mc-btn bg-pineapple-500 text-obsidian-950 font-bold text-xs sm:text-sm px-4 py-2 rounded-xl">
                    Visit Store
                </a>
            </div>
        </div>
    </header>

    <!-- 2. Hero Section -->
    <section class="relative pt-12 pb-20 sm:pt-20 sm:pb-28 overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid lg:grid-cols-12 gap-12 items-center">
                <!-- Left Content -->
                <div class="lg:col-span-7 text-center lg:text-left space-y-6">
                    <div class="inline-flex items-center gap-2.5 px-3.5 py-1.5 rounded-full bg-pineapple-500/10 border border-pineapple-500/30 text-pineapple-400 text-xs font-bold tracking-wide uppercase">
                        <span class="w-2 h-2 rounded-full bg-emerald-400 animate-ping"></span>
                        <span>Season 1 Live • Lifesteal SMP</span>
                    </div>

                    <h1 class="font-display font-black text-4xl sm:text-6xl lg:text-7xl tracking-tight text-white leading-[1.08]">
                        STEAL HEARTS.<br>
                        RULE <span class="text-transparent bg-clip-text bg-gradient-to-r from-pineapple-400 via-yellow-300 to-amber-500">PINEAPPLESMP</span>.
                    </h1>

                    <p class="text-zinc-400 text-base sm:text-lg max-w-2xl mx-auto lg:mx-0 leading-relaxed">
                        Experience intense, lag-free <strong class="text-zinc-200">Minecraft Lifesteal PvP</strong> crafted for both Java & Bedrock warriors. Eliminate enemies to steal their permanent hearts, forge unstoppable teams, and prepare for the <span class="text-pineapple-400 font-semibold">November 29, 2026 Mega PvP Showdown</span>!
                    </p>

                    <!-- Quick-Copy Server IP Buttons -->
                    <div class="grid sm:grid-cols-2 gap-4 pt-2 max-w-2xl mx-auto lg:mx-0">
                        <!-- Java IP Button -->
                        <button onclick="copyIP('basic.vitalcloud.in:19126', 'Java Edition IP')" class="mc-btn bg-pineapple-500 text-obsidian-950 rounded-2xl p-4 text-left flex items-center justify-between group cursor-pointer">
                            <div>
                                <div class="text-[11px] font-extrabold uppercase tracking-wider opacity-80 flex items-center gap-1.5">
                                    <span>☕ Java Edition</span>
                                    <span class="px-1.5 py-0.2 bg-obsidian-950/15 rounded text-[10px]">1.20 - 1.21+</span>
                                </div>
                                <div class="font-mono font-extrabold text-sm sm:text-base mt-0.5 tracking-tight">basic.vitalcloud.in:19126</div>
                            </div>
                            <span class="p-2 rounded-xl bg-obsidian-950/15 group-hover:bg-obsidian-950/25 transition" title="Copy IP">
                                <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.2" d="M8 16H6a2 2 0 01-2-2V6a2 2 0 012-2h8a2 2 0 012 2v2m-6 12h8a2 2 0 002-2v-8a2 2 0 00-2-2h-8a2 2 0 00-2 2v8a2 2 0 002 2z"></path>
                                </svg>
                            </span>
                        </button>

                        <!-- Bedrock IP & Port Button -->
                        <button onclick="copyIP('basic.vitalcloud.in:19149', 'Bedrock IP & Port')" class="mc-btn-dark bg-obsidian-850 hover:bg-obsidian-800 border-2 border-zinc-700/80 hover:border-pineapple-500/50 text-white rounded-2xl p-4 text-left flex items-center justify-between group cursor-pointer">
                            <div>
                                <div class="text-[11px] font-extrabold uppercase tracking-wider text-pineapple-400 flex items-center gap-1.5">
                                    <span>📱 Bedrock / PE</span>
                                    <span class="px-1.5 py-0.2 bg-pineapple-500/15 rounded text-[10px]">Port: 19149</span>
                                </div>
                                <div class="font-mono font-bold text-sm sm:text-base mt-0.5 text-zinc-100">basic.vitalcloud.in</div>
                            </div>
                            <span class="p-2 rounded-xl bg-zinc-800 group-hover:bg-pineapple-500 group-hover:text-obsidian-950 transition" title="Copy Bedrock IP">
                                <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.2" d="M8 16H6a2 2 0 01-2-2V6a2 2 0 012-2h8a2 2 0 012 2v2m-6 12h8a2 2 0 002-2v-8a2 2 0 00-2-2h-8a2 2 0 00-2 2v8a2 2 0 002 2z"></path>
                                </svg>
                            </span>
                        </button>
                    </div>
                </div>

                <!-- Right Custom Blocky Minecraft PineappleSMP Logo with Z-Black Sunglasses -->
                <div class="lg:col-span-5 flex justify-center">
                    <div class="relative animate-float w-full max-w-md">
                        <!-- Multi-layered Golden Aura -->
                        <div class="absolute -inset-6 bg-gradient-to-tr from-pineapple-500/25 via-amber-400/15 to-emerald-500/15 blur-3xl rounded-full"></div>
                        
                        <div class="relative bg-gradient-to-b from-obsidian-850/95 to-obsidian-950/95 border-2 border-pineapple-500/50 rounded-3xl p-5 sm:p-6 shadow-[0_20px_50px_rgba(0,0,0,0.75)] backdrop-blur-md">
                            <!-- Exact Blocky Minecraft PineappleSMP Logo SVG with Sleek Z-Black Sunglasses -->
                            <svg class="w-full h-auto max-h-80 mx-auto drop-shadow-[0_14px_26px_rgba(0,0,0,0.65)]" viewBox="0 0 420 350" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <defs>
                                    <!-- Pineapple Front & Side Gradients -->
                                    <linearGradient id="mcPineFront" x1="150" y1="95" x2="235" y2="195" gradientUnits="userSpaceOnUse">
                                        <stop offset="0%" stop-color="#fef08a"/>
                                        <stop offset="45%" stop-color="#facc15"/>
                                        <stop offset="100%" stop-color="#eab308"/>
                                    </linearGradient>
                                    <linearGradient id="mcPineSide" x1="235" y1="95" x2="275" y2="195" gradientUnits="userSpaceOnUse">
                                        <stop offset="0%" stop-color="#d97706"/>
                                        <stop offset="100%" stop-color="#92400e"/>
                                    </linearGradient>
                                    <!-- Leaf Gradients -->
                                    <linearGradient id="mcLeafLight" x1="210" y1="20" x2="210" y2="95" gradientUnits="userSpaceOnUse">
                                        <stop offset="0%" stop-color="#84cc16"/>
                                        <stop offset="55%" stop-color="#22c55e"/>
                                        <stop offset="100%" stop-color="#15803d"/>
                                    </linearGradient>
                                    <!-- 3D PINEAPPLE Text Gradient -->
                                    <linearGradient id="text3DFront" x1="210" y1="185" x2="210" y2="262" gradientUnits="userSpaceOnUse">
                                        <stop offset="0%" stop-color="#fef08a"/>
                                        <stop offset="48%" stop-color="#fde047"/>
                                        <stop offset="52%" stop-color="#facc15"/>
                                        <stop offset="100%" stop-color="#f59e0b"/>
                                    </linearGradient>
                                    <!-- Wooden SMP Plaque Gradient -->
                                    <linearGradient id="woodPlaque" x1="210" y1="268" x2="210" y2="322" gradientUnits="userSpaceOnUse">
                                        <stop offset="0%" stop-color="#78350f"/>
                                        <stop offset="50%" stop-color="#5c280b"/>
                                        <stop offset="100%" stop-color="#3f1a06"/>
                                    </linearGradient>
                                </defs>

                                <!-- Flying Golden Pineapple Chunks & Pixel Sparkles (Left Side) -->
                                <g>
                                    <!-- Speed Motion Trails -->
                                    <path d="M98 148L128 164L118 176L88 158Z" fill="#fef08a" fill-opacity="0.22"/>
                                    <path d="M124 114L142 128L134 136L116 122Z" fill="#fef08a" fill-opacity="0.2"/>
                                    <!-- Larger Left Flying Slice -->
                                    <polygon points="72,145 94,126 112,154 84,160" fill="#facc15" stroke="#451a03" stroke-width="3.5" stroke-linejoin="round"/>
                                    <polygon points="82,144 93,134 102,148 87,152" fill="#fef9c3"/>
                                    <!-- Smaller Left Flying Cube -->
                                    <polygon points="108,104 128,104 128,125 113,121" fill="#eab308" stroke="#451a03" stroke-width="3.5" stroke-linejoin="round"/>
                                    <rect x="114" y="109" width="8" height="8" fill="#fef08a"/>
                                </g>

                                <!-- Flying Golden Pineapple Chunks & Pixel Sparkles (Right Side) -->
                                <g>
                                    <!-- Speed Motion Trails -->
                                    <path d="M322 154L292 172L302 184L332 166Z" fill="#fef08a" fill-opacity="0.22"/>
                                    <path d="M304 114L286 128L294 136L312 122Z" fill="#fef08a" fill-opacity="0.2"/>
                                    <!-- Upper Right Flying Slice -->
                                    <polygon points="294,102 314,106 310,126 294,129" fill="#facc15" stroke="#451a03" stroke-width="3.5" stroke-linejoin="round"/>
                                    <polygon points="299,108 308,110 306,120 299,122" fill="#fef9c3"/>
                                    <!-- Lower Right Flying Chunk -->
                                    <polygon points="326,132 348,144 338,168 316,162" fill="#facc15" stroke="#451a03" stroke-width="3.5" stroke-linejoin="round"/>
                                    <polygon points="328,140 340,147 334,159 323,155" fill="#fef08a"/>
                                    <!-- Pixel 4-Point Yellow Sparkle -->
                                    <path d="M332 100L335 107L342 110L335 113L332 120L329 113L322 110L329 107L332 100Z" fill="#facc15"/>
                                </g>

                                <!-- Blocky Spiky Minecraft Pineapple Crown Leaves -->
                                <g stroke="#052e16" stroke-width="3.5" stroke-linejoin="round">
                                    <!-- Back Dark Leaves -->
                                    <polygon points="184,96 172,46 204,78" fill="#15803d"/>
                                    <polygon points="236,96 258,42 222,78" fill="#15803d"/>
                                    <polygon points="164,96 156,74 186,88" fill="#166534"/>
                                    <polygon points="250,98 276,84 248,104" fill="#166534"/>
                                    <!-- Front Bright Voxel Leaves -->
                                    <polygon points="196,96 218,22 224,96" fill="url(#mcLeafLight)"/>
                                    <polygon points="178,96 174,56 202,94" fill="#22c55e"/>
                                    <polygon points="222,96 254,54 240,98" fill="#22c55e"/>
                                    <polygon points="162,96 168,80 188,96" fill="#4ade80"/>
                                </g>

                                <!-- Blocky 3D Minecraft Pineapple Head -->
                                <g>
                                    <!-- 3D Right Extruded Side Face -->
                                    <polygon points="236,94 274,114 264,192 230,192" fill="url(#mcPineSide)" stroke="#451a03" stroke-width="4" stroke-linejoin="round"/>
                                    <!-- Side Diamond Grid -->
                                    <path d="M242 116L266 138M238 144L264 168M268 118L238 148M266 148L236 178" stroke="#78350f" stroke-width="2.5"/>

                                    <!-- Main Front Cube Face -->
                                    <polygon points="154,94 236,94 230,192 146,192" fill="url(#mcPineFront)" stroke="#451a03" stroke-width="4" stroke-linejoin="round"/>
                                    
                                    <!-- Front Cross-Hatch Pineapple Grid & Specular Highlights -->
                                    <path d="M162 98L230 156M152 128L226 190M224 98L150 162M232 132L166 190" stroke="#eab308" stroke-width="2.5"/>
                                    <!-- Pixel Highlights -->
                                    <polygon points="164,104 176,104 170,114 158,114" fill="#fef9c3"/>
                                    <polygon points="194,104 206,104 200,114 188,114" fill="#fef9c3"/>

                                    <!-- SLEEK JET-BLACK (Z-BLACK) PIXEL-ART SUNGLASSES -->
                                    <g>
                                        <!-- Temple Arm Extending to 3D Side -->
                                        <polygon points="232,126 271,134 270,141 232,134" fill="#050507" stroke="#000000" stroke-width="1.5"/>
                                        <!-- Top Sleek Brow Bar -->
                                        <polygon points="152,123 234,125 234,132 152,130" fill="#050507" stroke="#000000" stroke-width="1.5"/>
                                        <!-- Left Z-Black Lens -->
                                        <polygon points="158,126 189,127 187,149 160,148" fill="#030305" stroke="#000000" stroke-width="2.5" stroke-linejoin="round"/>
                                        <!-- Right Z-Black Lens -->
                                        <polygon points="197,127 228,128 226,150 199,149" fill="#030305" stroke="#000000" stroke-width="2.5" stroke-linejoin="round"/>
                                        <!-- Nose Bridge -->
                                        <rect x="188" y="129" width="10" height="5" fill="#050507"/>
                                        <!-- Subtle Glossy Z-Black Reflections -->
                                        <polygon points="163,130 171,130 166,144 161,144" fill="#27272a"/>
                                        <polygon points="174,130 178,130 173,144 170,144" fill="#18181b"/>
                                        <polygon points="202,131 210,131 205,145 200,145" fill="#27272a"/>
                                        <polygon points="213,131 217,131 212,145 209,145" fill="#18181b"/>
                                    </g>

                                    <!-- Cute Happy Blocky Smile -->
                                    <g>
                                        <path d="M174 156H180V162H200V156H206V166H201V174H179V166H174V156Z" fill="#291103"/>
                                        <!-- Pink Tongue -->
                                        <rect x="184" y="167" width="12" height="5" fill="#fb7185"/>
                                    </g>
                                </g>

                                <!-- BOLD 3D BLOCKY "PINEAPPLE" BANNER TEXT -->
                                <g transform="translate(0, 4)">
                                    <!-- Deep 3D Extruded Shadow Backing -->
                                    <text x="210" y="256" text-anchor="middle" font-family="'Press Start 2P', 'Space Grotesk', sans-serif" font-weight="900" font-size="37" letter-spacing="-1" fill="#451a03" stroke="#09090b" stroke-width="11" stroke-linejoin="round">
                                        PINEAPPLE
                                    </text>
                                    <text x="210" y="253" text-anchor="middle" font-family="'Press Start 2P', 'Space Grotesk', sans-serif" font-weight="900" font-size="37" letter-spacing="-1" fill="#78350f">
                                        PINEAPPLE
                                    </text>
                                    <!-- Bright Golden-Yellow 3D Front Face -->
                                    <text x="210" y="246" text-anchor="middle" font-family="'Press Start 2P', 'Space Grotesk', sans-serif" font-weight="900" font-size="37" letter-spacing="-1" fill="url(#text3DFront)" stroke="#18181b" stroke-width="3.5" paint-order="stroke">
                                        PINEAPPLE
                                    </text>
                                </g>

                                <!-- WOODEN HEXAGONAL "SMP" PLAQUE BADGE -->
                                <g transform="translate(0, 4)">
                                    <!-- 3D Bottom Wood Rim -->
                                    <polygon points="145,272 275,272 296,298 275,326 145,326 124,298" fill="#271003" stroke="#09090b" stroke-width="4" stroke-linejoin="round"/>
                                    <!-- Front Wood Grain Hex Plaque -->
                                    <polygon points="146,268 274,268 294,293 274,318 146,318 126,293" fill="url(#woodPlaque)" stroke="#1c0a00" stroke-width="3" stroke-linejoin="round"/>
                                    <!-- Subtle Wood Grain Lines -->
                                    <path d="M142 281H278M136 294H284M144 306H276" stroke="#92400e" stroke-opacity="0.35" stroke-width="2"/>
                                    <!-- Crisp White Blocky "SMP" Text -->
                                    <text x="210" y="304" text-anchor="middle" font-family="'Press Start 2P', sans-serif" font-weight="900" font-size="24" letter-spacing="2" fill="#271003">
                                        SMP
                                    </text>
                                    <text x="210" y="301" text-anchor="middle" font-family="'Press Start 2P', sans-serif" font-weight="900" font-size="24" letter-spacing="2" fill="#ffffff">
                                        SMP
                                    </text>
                                </g>
                            </svg>

                            <div class="mt-3 text-center">
                                <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-pineapple-500/15 border border-pineapple-500/40">
                                    <span class="font-pixel text-[10px] text-pineapple-400 tracking-wider">SEASON 1 • LIFESTEAL</span>
                                </div>
                                <div class="text-xs text-zinc-400 mt-2">Official Mascot • Powered by <span class="text-white font-semibold">Devesh</span></div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 3. Live Server Status Section -->
    <section id="status" class="py-12 border-y border-zinc-800/80 bg-obsidian-900/60">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 mb-8">
                <div>
                    <h2 class="font-display font-extrabold text-2xl sm:text-3xl text-white flex items-center gap-3">
                        <span class="w-3 h-3 rounded-full bg-emerald-400 shadow-[0_0_12px_#34d399]"></span>
                        Live Server Telemetry
                    </h2>
                    <p class="text-zinc-400 text-sm mt-1">Real-time node status for <code class="text-pineapple-400">basic.vitalcloud.in</code></p>
                </div>

                <!-- 5-Second Auto-Refresh Countdown Timer -->
                <div class="inline-flex items-center gap-3 bg-obsidian-850 border border-zinc-700/80 px-4 py-2 rounded-xl self-start sm:self-auto">
                    <svg class="w-4 h-4 text-pineapple-400 animate-spin" style="animation-duration: 5s;" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15"></path>
                    </svg>
                    <span class="text-xs font-medium text-zinc-300">
                        Auto-refresh in <span id="refresh-countdown" class="font-mono font-bold text-pineapple-400">5</span>s
                    </span>
                    <button onclick="manualRefreshStatus()" class="text-xs font-bold text-zinc-400 hover:text-white underline ml-1">Now</button>
                </div>
            </div>

            <!-- Telemetry Metrics Grid -->
            <div class="grid grid-cols-2 lg:grid-cols-4 gap-4 mb-6">
                <div class="bg-obsidian-850 border border-zinc-800 rounded-2xl p-5">
                    <div class="text-xs font-bold uppercase tracking-wider text-zinc-500">Server Status</div>
                    <div class="mt-2 flex items-center gap-2">
                        <span id="server-status-badge" class="px-2.5 py-1 rounded-lg bg-amber-500/15 text-amber-400 font-bold text-sm border border-amber-500/30">CHECKING...</span>
                        <span id="server-version-text" class="text-xs text-zinc-400 truncate">1.20 - 1.21+</span>
                    </div>
                </div>

                <div class="bg-obsidian-850 border border-zinc-800 rounded-2xl p-5">
                    <div class="text-xs font-bold uppercase tracking-wider text-zinc-500">Online Players</div>
                    <div class="mt-2 flex items-baseline gap-2">
                        <span id="online-count" class="font-display font-black text-3xl text-pineapple-400">--</span>
                        <span class="text-sm font-semibold text-zinc-500">/ <span id="max-slots">100</span> Slots</span>
                    </div>
                </div>

                <div class="bg-obsidian-850 border border-zinc-800 rounded-2xl p-5">
                    <div class="text-xs font-bold uppercase tracking-wider text-zinc-500">API Response</div>
                    <div class="mt-2 flex items-baseline gap-2">
                        <span id="server-ping" class="font-display font-black text-3xl text-emerald-400">--</span>
                        <span class="text-sm font-semibold text-zinc-500">ms (Live)</span>
                    </div>
                </div>

                <div class="bg-obsidian-850 border border-zinc-800 rounded-2xl p-5">
                    <div class="text-xs font-bold uppercase tracking-wider text-zinc-500">Next Big Event</div>
                    <div class="mt-2">
                        <div class="font-bold text-white text-sm sm:text-base">Nov 29, 2026</div>
                        <div class="text-xs text-pineapple-400 font-medium">Mega PvP Arena</div>
                    </div>
                </div>
            </div>

            <!-- Live Online Players List (Real API Data Only) -->
            <div class="bg-obsidian-850 border border-zinc-800 rounded-2xl p-5">
                <div class="flex items-center justify-between mb-4">
                    <h3 class="text-xs font-bold uppercase tracking-wider text-zinc-400 flex items-center gap-2">
                        <span>👥 Live Online Players (mcsrvstat.us Real-Time Feed)</span>
                    </h3>
                    <span id="last-updated-label" class="text-xs text-zinc-500">Syncing...</span>
                </div>
                <div id="online-players-grid" class="flex flex-wrap gap-2.5">
                    <span class="text-xs text-zinc-400">Fetching live player list from server...</span>
                </div>
            </div>
        </div>
    </section>

    <!-- 4. Kit & Rank Store Section -->
    <section id="store" class="py-20">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-12">
                <span class="px-3 py-1 rounded-full bg-pineapple-500/10 border border-pineapple-500/30 text-pineapple-400 text-xs font-bold uppercase tracking-wider">
                    Official Server Store
                </span>
                <h2 class="font-display font-black text-3xl sm:text-5xl text-white mt-3">
                    UNLOCK THE <span class="text-pineapple-400">LEGEND KIT</span>
                </h2>
                <p class="text-zinc-400 text-sm sm:text-base mt-3">
                    Instant delivery via UPI. Support PineappleSMP Season 1 and dominate the Lifesteal arena!
                </p>
            </div>

            <!-- Kit Insurance Add-On Banner / Toggle -->
            <div class="max-w-4xl mx-auto mb-12 bg-gradient-to-r from-obsidian-850 via-obsidian-900 to-obsidian-850 border-2 border-pineapple-500/40 rounded-3xl p-6 shadow-xl">
                <div class="flex flex-col md:flex-row items-start md:items-center justify-between gap-6">
                    <div class="space-y-2 flex-1">
                        <div class="flex items-center gap-2.5">
                            <span class="p-1.5 rounded-lg bg-pineapple-500/20 text-pineapple-400">
                                <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"></path>
                                </svg>
                            </span>
                            <h3 class="font-display font-bold text-lg sm:text-xl text-white">
                                PineappleShield™ Kit Insurance <span class="text-xs font-mono bg-pineapple-500 text-obsidian-950 px-2 py-0.5 rounded-md ml-1 font-extrabold">+10% + 5% GST</span>
                            </h3>
                        </div>
                        <p class="text-zinc-400 text-xs sm:text-sm leading-relaxed">
                            Protect your hard-earned loot! Includes a <strong class="text-zinc-200">3-Hour Full Refund Policy</strong> (if unsatisfied or accidental purchase) plus <strong class="text-pineapple-400">3-Day Damage & Glitch Coverage</strong> (free kit replacement if lost to server lag, bugs, or verified cheaters).
                        </p>
                    </div>

                    <!-- Global Toggle Switch -->
                    <div class="flex items-center gap-3 bg-obsidian-950 px-4 py-3 rounded-2xl border border-zinc-800 shrink-0 self-stretch md:self-auto justify-between">
                        <span class="text-xs font-bold text-zinc-300">Apply Insurance</span>
                        <label class="relative inline-flex items-center cursor-pointer">
                            <input type="checkbox" id="global-insurance-toggle" class="sr-only peer" onchange="syncInsuranceToggle(this.checked)">
                            <div class="w-12 h-6 bg-zinc-700 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-pineapple-500"></div>
                        </label>
                    </div>
                </div>
            </div>

            <!-- Centered Featured Legend Kit Card -->
            <div id="kits-grid" class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Populated dynamically via JS with all 6 kits -->
            </div>
        </div>
    </section>

    <!-- 6. Top Funders & Staff Section -->
    <section id="community" class="py-16 border-t border-zinc-800/80 bg-obsidian-900/50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-2xl mx-auto mb-12">
                <h2 class="font-display font-black text-3xl sm:text-4xl text-white">
                    TOP FUNDERS & <span class="text-pineapple-400">LEADERSHIP</span>
                </h2>
                <p class="text-zinc-400 text-sm mt-2">
                    Meet the legends keeping PineappleSMP online and thriving.
                </p>
            </div>

            <div class="grid md:grid-cols-2 gap-8 max-w-5xl mx-auto">
                <!-- Top Funder Highlight Card -->
                <div class="relative bg-gradient-to-br from-amber-500/15 via-obsidian-850 to-obsidian-900 border-2 border-pineapple-500/50 rounded-3xl p-6 sm:p-8 flex flex-col justify-between shadow-xl overflow-hidden">
                    <div class="absolute top-0 right-0 bg-pineapple-500 text-obsidian-950 font-pixel text-[10px] px-3 py-1.5 rounded-bl-xl font-bold">
                        👑 #1 TOP FUNDER
                    </div>

                    <div class="flex items-center gap-5 mt-2">
                        <!-- Minecraft Avatar SVG for flaxxy444 -->
                        <div class="w-20 h-20 rounded-2xl bg-obsidian-950 border-2 border-pineapple-400 p-1.5 shrink-0 shadow-lg">
                            <svg class="w-full h-full rounded-xl" viewBox="0 0 8 8" shape-rendering="crispEdges">
                                <rect width="8" height="8" fill="#facc15"/>
                                <rect x="0" y="0" width="8" height="2" fill="#422006"/>
                                <rect x="0" y="2" width="1" height="2" fill="#422006"/>
                                <rect x="7" y="2" width="1" height="2" fill="#422006"/>
                                <rect x="1" y="2" width="6" height="6" fill="#fed7aa"/>
                                <rect x="1" y="4" width="2" height="1" fill="#ffffff"/>
                                <rect x="2" y="4" width="1" height="1" fill="#2563eb"/>
                                <rect x="5" y="4" width="2" height="1" fill="#ffffff"/>
                                <rect x="5" y="4" width="1" height="1" fill="#2563eb"/>
                                <rect x="3" y="6" width="2" height="1" fill="#9a3412"/>
                            </svg>
                        </div>
                        <div>
                            <div class="inline-flex items-center gap-1.5 text-xs font-bold text-pineapple-400 uppercase tracking-wider">
                                <span>💎 Diamond Patron</span>
                            </div>
                            <h3 class="font-display font-black text-2xl sm:text-3xl text-white mt-0.5">flaxxy444</h3>
                            <p class="text-zinc-400 text-xs sm:text-sm mt-1">
                                Official Season 1 Founding Supporter & Community MVP.
                            </p>
                        </div>
                    </div>

                    <div class="mt-6 pt-5 border-t border-zinc-800/80 flex items-center justify-between text-xs">
                        <span class="text-zinc-400">Contribution Tier: <strong class="text-pineapple-400">LEGENDARY</strong></span>
                        <span class="px-2.5 py-1 rounded-lg bg-pineapple-500/15 text-pineapple-300 font-semibold">Hall of Fame</span>
                    </div>
                </div>

                <!-- Live-Style Discord Profile Widget for Owner devesh_37 -->
                <div class="bg-[#111214] border border-[#2b2d31] rounded-3xl overflow-hidden shadow-xl flex flex-col justify-between">
                    <!-- Discord Banner -->
                    <div>
                        <div class="h-20 bg-gradient-to-r from-pineapple-500 via-amber-500 to-yellow-600 relative">
                            <span class="absolute top-3 right-3 bg-black/60 backdrop-blur-md text-white text-[11px] font-bold px-2.5 py-1 rounded-full">
                                Discord Profile
                            </span>
                        </div>

                        <div class="px-6 pb-6 relative">
                            <!-- Avatar + Online Status Dot -->
                            <div class="relative -mt-10 mb-3 inline-block">
                                <div class="w-20 h-20 rounded-full bg-[#111214] p-1.5">
                                    <div class="w-full h-full rounded-full bg-obsidian-800 border border-pineapple-500/50 flex items-center justify-center overflow-hidden">
                                        <!-- Custom Owner Pixel Avatar -->
                                        <svg class="w-14 h-14" viewBox="0 0 8 8" shape-rendering="crispEdges">
                                            <rect width="8" height="8" fill="#18181b"/>
                                            <rect x="1" y="1" width="6" height="6" fill="#fde047"/>
                                            <rect x="1" y="1" width="6" height="2" fill="#09090b"/>
                                            <rect x="1" y="4" width="2" height="1" fill="#09090b"/>
                                            <rect x="5" y="4" width="2" height="1" fill="#09090b"/>
                                            <rect x="3" y="4" width="2" height="1" fill="#ca8a04"/>
                                            <rect x="2" y="6" width="4" height="1" fill="#09090b"/>
                                        </svg>
                                    </div>
                                </div>
                                <span class="absolute bottom-1.5 right-1.5 w-5 h-5 rounded-full bg-emerald-500 border-4 border-[#111214]" title="Online"></span>
                            </div>

                            <div class="flex flex-wrap items-center justify-between gap-2">
                                <div>
                                    <h3 class="font-bold text-xl text-white flex items-center gap-2">
                                        Devesh
                                        <span class="text-xs font-semibold px-2 py-0.5 rounded bg-[#5865F2]/20 text-[#8ea1e1] border border-[#5865F2]/40">OWNER</span>
                                    </h3>
                                    <div class="text-xs text-zinc-400 font-mono">@devesh_37</div>
                                </div>

                                <a href="https://discord.gg/McaguFJdQ" target="_blank" rel="noopener noreferrer" onclick="showToast('Opening PineappleSMP Discord Invite! Add @devesh_37 for support.', 'info')" class="mc-btn bg-[#5865F2] hover:bg-[#4752C4] text-white font-bold text-xs px-4 py-2.5 rounded-xl inline-flex items-center gap-2">
                                    <svg class="w-4 h-4 fill-current" viewBox="0 0 24 24">
                                        <path d="M20.317 4.37a19.791 19.791 0 0 0-4.885-1.515.074.074 0 0 0-.079.037c-.21.375-.444.864-.608 1.25a18.27 18.27 0 0 0-5.487 0 12.64 12.64 0 0 0-.617-1.25.077.077 0 0 0-.079-.037A19.736 19.736 0 0 0 3.677 4.37a.07.07 0 0 0-.032.027C.533 9.046-.32 13.58.099 18.057a.082.082 0 0 0 .031.057 19.9 19.9 0 0 0 5.993 3.03.078.078 0 0 0 .084-.028c.462-.63.874-1.295 1.226-1.994.021-.041.001-.09-.041-.106a13.107 13.107 0 0 1-1.872-.892.077.077 0 0 1-.008-.128 10.2 10.2 0 0 0 .372-.292.074.074 0 0 1 .077-.01c3.928 1.793 8.18 1.793 12.061 0a.074.074 0 0 1 .078.01c.12.098.246.198.373.292a.077.077 0 0 1-.006.127 12.299 12.299 0 0 1-1.873.892.077.077 0 0 0-.041.107c.36.698.772 1.362 1.225 1.993a.076.076 0 0 0 .084.028 19.839 19.839 0 0 0 6.002-3.03.077.077 0 0 0 .032-.054c.5-5.177-.838-9.674-3.549-13.66a.061.061 0 0 0-.031-.028z"/>
                                    </svg>
                                    Join Discord
                                </a>
                            </div>

                            <!-- Discord Activity Box -->
                            <div class="mt-4 bg-[#1e1f22] rounded-xl p-3 border border-zinc-800/80">
                                <div class="text-[10px] font-bold uppercase tracking-wider text-zinc-400 mb-1.5">Playing a Game</div>
                                <div class="flex items-center gap-3">
                                    <div class="w-10 h-10 rounded-lg bg-pineapple-500/20 border border-pineapple-500/40 flex items-center justify-center text-lg">
                                        🍍
                                    </div>
                                    <div>
                                        <div class="text-xs font-bold text-white">PineappleSMP Season 1</div>
                                        <div class="text-[11px] text-zinc-400">Managing PvP Event (Nov 29)</div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Lifesteal Rules & Features Strip -->
    <section id="rules" class="py-14 border-t border-zinc-800/80">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid sm:grid-cols-3 gap-6">
                <div class="bg-obsidian-850 border border-zinc-800 rounded-2xl p-6">
                    <div class="text-2xl mb-3">❤️</div>
                    <h3 class="font-display font-bold text-lg text-white">True Lifesteal Mechanics</h3>
                    <p class="text-zinc-400 text-sm mt-1.5 leading-relaxed">
                        Kill a player to permanently gain +1 Heart (up to 20 Hearts). Lose all your hearts and get temporarily death-banned until a teammate crafts a Revival Beacon!
                    </p>
                </div>
                <div class="bg-obsidian-850 border border-zinc-800 rounded-2xl p-6">
                    <div class="text-2xl mb-3">⚔️</div>
                    <h3 class="font-display font-bold text-lg text-white">Nov 29 Mega PvP Event</h3>
                    <p class="text-zinc-400 text-sm mt-1.5 leading-relaxed">
                        Join on November 29, 2026 for a server-wide Crystal & Sword PvP Tournament. Top 3 winners receive free Ender & Netherite Kits!
                    </p>
                </div>
                <div class="bg-obsidian-850 border border-zinc-800 rounded-2xl p-6">
                    <div class="text-2xl mb-3">⚡</div>
                    <h3 class="font-display font-bold text-lg text-white">Instant UPI Kit Delivery</h3>
                    <p class="text-zinc-400 text-sm mt-1.5 leading-relaxed">
                        Pay securely via any Indian UPI app (GPay, PhonePe, Paytm) to <code class="text-pineapple-400">ghostmc.fund@axl</code> and claim your kit in-game within minutes.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- 8. Footer -->
    <footer class="border-t border-zinc-800 bg-obsidian-950 py-10">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col sm:flex-row items-center justify-between gap-4 text-center sm:text-left">
            <div>
                <div class="font-display font-extrabold text-lg text-white">
                    Pineapple<span class="text-pineapple-400">SMP</span>
                </div>
                <p class="text-xs text-zinc-500 mt-1">
                    Not affiliated with Mojang AB or Microsoft. Minecraft is a trademark of Mojang Synergies AB.
                </p>
            </div>
            <div class="flex flex-col items-center sm:items-end gap-1">
                <span class="px-3.5 py-1.5 rounded-xl bg-obsidian-900 border border-pineapple-500/30 text-xs font-bold text-pineapple-400 tracking-wide">
                    ⚡ Powered by Devesh
                </span>
                <span class="text-[11px] text-zinc-600">© 2026 PineappleSMP Network. All rights reserved.</span>
            </div>
        </div>
    </footer>

    <!-- 5. Interactive UPI Checkout Modal -->
    <div id="checkout-modal" class="fixed inset-0 z-50 hidden items-center justify-center p-4 bg-black/80 backdrop-blur-sm overflow-y-auto">
        <div class="relative w-full max-w-lg bg-obsidian-900 border-2 border-pineapple-500/50 rounded-3xl shadow-2xl overflow-hidden my-auto">
            <!-- Modal Header -->
            <div class="bg-obsidian-850 px-6 py-4 border-b border-zinc-800 flex items-center justify-between">
                <div class="flex items-center gap-2.5">
                    <span class="text-xl">🍍</span>
                    <h3 class="font-display font-extrabold text-lg text-white">UPI Instant Checkout</h3>
                </div>
                <button onclick="closeCheckoutModal()" class="w-8 h-8 rounded-lg bg-obsidian-950 text-zinc-400 hover:text-white flex items-center justify-center transition">
                    ✕
                </button>
            </div>

            <!-- Modal Body -->
            <div id="checkout-form-view" class="p-6 space-y-5">
                <!-- Selected Kit Summary -->
                <div class="bg-obsidian-950 border border-zinc-800 rounded-2xl p-4 space-y-3">
                    <div class="flex items-center justify-between">
                        <div>
                            <div class="text-xs text-zinc-400 uppercase font-bold">Selected Package</div>
                            <div id="modal-kit-name" class="font-display font-extrabold text-xl text-pineapple-400">Diamond Kit</div>
                        </div>
                        <div class="text-right">
                            <div class="text-xs text-zinc-400">Base Price</div>
                            <div id="modal-base-price" class="font-mono font-bold text-white">₹100.00</div>
                        </div>
                    </div>

                    <!-- Modal Insurance Toggle -->
                    <div class="pt-3 border-t border-zinc-800/80 flex items-center justify-between">
                        <div>
                            <div class="text-xs font-bold text-zinc-200 flex items-center gap-1.5">
                                🛡️ Kit Insurance (+10% + 5% GST)
                            </div>
                            <div class="text-[11px] text-zinc-500">3-hr refund & 3-day damage coverage</div>
                        </div>
                        <label class="relative inline-flex items-center cursor-pointer">
                            <input type="checkbox" id="modal-insurance-checkbox" class="sr-only peer" onchange="updateModalPricing()">
                            <div class="w-11 h-6 bg-zinc-700 peer-focus:outline-none rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-pineapple-500"></div>
                        </label>
                    </div>

                    <!-- Breakdown rows -->
                    <div id="modal-breakdown" class="hidden pt-2 border-t border-zinc-800/60 text-xs space-y-1 text-zinc-400">
                        <div class="flex justify-between">
                            <span>Insurance Fee (10%):</span>
                            <span id="modal-ins-fee" class="font-mono text-zinc-300">₹10.00</span>
                        </div>
                        <div class="flex justify-between">
                            <span>GST on Insurance (5%):</span>
                            <span id="modal-gst-fee" class="font-mono text-zinc-300">₹0.50</span>
                        </div>
                    </div>

                    <!-- Final Payable -->
                    <div class="pt-3 border-t border-zinc-800 flex items-center justify-between">
                        <span class="font-bold text-sm text-white">Total Payable (INR)</span>
                        <span id="modal-total-price" class="font-display font-black text-2xl text-emerald-400">₹100.00</span>
                    </div>
                </div>

                <!-- Dynamic QR Code & UPI ID Box -->
                <div class="grid sm:grid-cols-12 gap-4 items-center bg-obsidian-850 border border-zinc-800 rounded-2xl p-4">
                    <div class="sm:col-span-5 flex flex-col items-center">
                        <!-- Dynamic SVG QR Code Container -->
                        <div id="dynamic-qr-container" class="bg-white p-2.5 rounded-xl shadow-md w-32 h-32 flex items-center justify-center">
                            <!-- Generated dynamically by JS -->
                        </div>
                        <span class="text-[10px] text-zinc-400 mt-1.5 font-medium">Scan with any UPI App</span>
                    </div>

                    <div class="sm:col-span-7 space-y-2.5 text-center sm:text-left">
                        <div class="text-xs font-bold text-zinc-400 uppercase tracking-wider">Official UPI ID</div>
                        <div class="flex items-center justify-between bg-obsidian-950 border border-zinc-700 rounded-xl px-3 py-2">
                            <code class="text-xs sm:text-sm font-bold text-pineapple-400 select-all">ghostmc.fund@axl</code>
                            <button type="button" onclick="copyIP('ghostmc.fund@axl', 'UPI ID')" class="text-xs bg-zinc-800 hover:bg-zinc-700 text-white px-2.5 py-1 rounded-lg font-semibold transition">
                                Copy
                            </button>
                        </div>
                        <p class="text-[11px] text-zinc-400 leading-relaxed">
                            Pay the exact amount shown above, then enter your Minecraft & Discord details below to verify your order.
                        </p>
                    </div>
                </div>

                <!-- Order Confirmation Form -->
                <form onsubmit="submitOrderConfirmation(event)" class="space-y-3.5">
                    <div>
                        <label class="block text-xs font-bold text-zinc-300 mb-1">Minecraft Username (Exact IGN) *</label>
                        <input type="text" id="order-mc-username" required placeholder="e.g., Steve_PvP (prefix . for Bedrock)" class="w-full bg-obsidian-950 border border-zinc-700 focus:border-pineapple-500 rounded-xl px-3.5 py-2.5 text-sm text-white outline-none transition">
                    </div>

                    <div class="grid sm:grid-cols-2 gap-3">
                        <div>
                            <label class="block text-xs font-bold text-zinc-300 mb-1">Discord Tag / Username *</label>
                            <input type="text" id="order-discord-tag" required placeholder="e.g., player#1234" class="w-full bg-obsidian-950 border border-zinc-700 focus:border-pineapple-500 rounded-xl px-3.5 py-2.5 text-sm text-white outline-none transition">
                        </div>
                        <div>
                            <label class="block text-xs font-bold text-zinc-300 mb-1">UPI Transaction / UTR Ref *</label>
                            <input type="text" id="order-utr" required placeholder="12-digit UTR number" class="w-full bg-obsidian-950 border border-zinc-700 focus:border-pineapple-500 rounded-xl px-3.5 py-2.5 text-sm text-white outline-none transition">
                        </div>
                    </div>

                    <button type="submit" class="mc-btn w-full bg-pineapple-500 text-obsidian-950 font-extrabold text-sm py-3.5 rounded-xl mt-2">
                        Confirm Payment & Claim Kit ⚔️
                    </button>
                </form>
            </div>

            <!-- Order Success Receipt View -->
            <div id="checkout-success-view" class="hidden p-8 text-center space-y-4">
                <div class="w-16 h-16 rounded-full bg-emerald-500/20 border-2 border-emerald-500 text-emerald-400 flex items-center justify-center text-3xl mx-auto">
                    ✓
                </div>
                <h4 class="font-display font-black text-2xl text-white">Order Submitted!</h4>
                <p class="text-sm text-zinc-400 max-w-sm mx-auto">
                    Thank you, <span id="receipt-ign" class="text-pineapple-400 font-bold">Player</span>! Your payment verification for <span id="receipt-kit" class="text-white font-bold">Kit</span> (<span id="receipt-amount" class="text-emerald-400 font-bold">₹0</span>) has been logged.
                </p>
                <div class="bg-obsidian-950 border border-zinc-800 rounded-2xl p-4 text-xs text-zinc-400 space-y-1 text-left">
                    <div><strong class="text-zinc-200">Order ID:</strong> <span id="receipt-order-id" class="font-mono text-pineapple-400">#PSMP-8821</span></div>
                    <div><strong class="text-zinc-200">Discord Contact:</strong> <span id="receipt-discord">user</span></div>
                    <div><strong class="text-zinc-200">Delivery ETA:</strong> 2–10 mins (or ping <span class="text-pineapple-400">@devesh_37</span> on Discord)</div>
                </div>
                <button onclick="closeCheckoutModal()" class="mc-btn-dark w-full bg-obsidian-800 hover:bg-obsidian-700 text-white font-bold text-sm py-3 rounded-xl">
                    Back to PineappleSMP
                </button>
            </div>
        </div>
    </div>

    <!-- 7. Floating Multilingual AI Assistant & Mini Community Live Chat Widget -->
    <div class="fixed bottom-5 right-5 z-40 flex flex-col items-end">
        <!-- Expandable Widget Window -->
        <div id="assistant-window" class="hidden mb-3 w-[340px] sm:w-[380px] bg-obsidian-900 border-2 border-pineapple-500/50 rounded-3xl shadow-2xl overflow-hidden flex flex-col max-h-[520px]">
            <!-- Top Header & Tab Switcher -->
            <div class="bg-obsidian-850 p-3.5 border-b border-zinc-800">
                <div class="flex items-center justify-between mb-3">
                    <div class="flex items-center gap-2">
                        <span class="text-lg">🍍</span>
                        <div>
                            <div class="font-display font-bold text-sm text-white leading-none">PineappleSMP Hub</div>
                            <div class="text-[10px] text-emerald-400 font-semibold mt-0.5">● AI Helper & Live Lobby Chat</div>
                        </div>
                    </div>
                    <button onclick="toggleAssistant()" class="text-zinc-400 hover:text-white p-1">✕</button>
                </div>

                    <!-- Mode Tabs -->
                <div class="grid grid-cols-2 gap-1.5 bg-obsidian-950 p-1 rounded-xl border border-zinc-800">
                    <button id="tab-ai" onclick="switchHubTab('ai')" class="py-1.5 text-xs font-bold rounded-lg bg-pineapple-500 text-obsidian-950 transition">
                        🤖 AI Assistant
                    </button>
                    <button id="tab-chat" onclick="switchHubTab('chat')" class="py-1.5 text-xs font-bold rounded-lg text-zinc-400 hover:text-white transition">
                        💬 Live Chat (<span id="chat-online-badge">0</span>)
                    </button>
                </div>
            </div>

            <!-- TAB 1: Multilingual AI Assistant -->
            <div id="panel-ai" class="flex flex-col flex-1 overflow-hidden">
                <!-- Language Selector Bar -->
                <div class="bg-obsidian-950/80 px-3.5 py-2 border-b border-zinc-800/80 flex items-center justify-between text-xs">
                    <span class="text-zinc-400 font-medium">Language:</span>
                    <div class="flex gap-1">
                        <button onclick="setAiLang('en')" id="lang-en" class="px-2 py-0.5 rounded bg-pineapple-500 text-obsidian-950 font-bold text-[11px]">English</button>
                        <button onclick="setAiLang('hi')" id="lang-hi" class="px-2 py-0.5 rounded bg-obsidian-800 text-zinc-300 font-bold text-[11px]">हिंदी</button>
                        <button onclick="setAiLang('hinglish')" id="lang-hinglish" class="px-2 py-0.5 rounded bg-obsidian-800 text-zinc-300 font-bold text-[11px]">Hinglish</button>
                    </div>
                </div>

                <!-- AI Messages Feed -->
                <div id="ai-messages" class="p-3.5 space-y-3 overflow-y-auto h-64 text-xs">
                    <!-- Populated by JS -->
                </div>

                <!-- Quick Question Chips -->
                <div class="px-3.5 py-2 bg-obsidian-950/60 border-t border-zinc-800/60 flex gap-1.5 overflow-x-auto no-scrollbar">
                    <button onclick="askQuickQuestion('ip')" class="shrink-0 px-2.5 py-1 rounded-lg bg-obsidian-800 hover:bg-zinc-700 text-pineapple-400 font-semibold text-[11px] border border-zinc-700">Server IPs?</button>
                    <button onclick="askQuickQuestion('kits')" class="shrink-0 px-2.5 py-1 rounded-lg bg-obsidian-800 hover:bg-zinc-700 text-pineapple-400 font-semibold text-[11px] border border-zinc-700">Kit Prices?</button>
                    <button onclick="askQuickQuestion('insurance')" class="shrink-0 px-2.5 py-1 rounded-lg bg-obsidian-800 hover:bg-zinc-700 text-pineapple-400 font-semibold text-[11px] border border-zinc-700">Insurance?</button>
                    <button onclick="askQuickQuestion('event')" class="shrink-0 px-2.5 py-1 rounded-lg bg-obsidian-800 hover:bg-zinc-700 text-pineapple-400 font-semibold text-[11px] border border-zinc-700">Nov 29 Event?</button>
                </div>

                <!-- AI Input Form -->
                <form onsubmit="handleAiSubmit(event)" class="p-3 bg-obsidian-850 border-t border-zinc-800 flex gap-2">
                    <input type="text" id="ai-input" placeholder="Ask about IPs, kits, UPI, event..." class="flex-1 bg-obsidian-950 border border-zinc-700 focus:border-pineapple-500 rounded-xl px-3 py-2 text-xs text-white outline-none">
                    <button type="submit" class="bg-pineapple-500 hover:bg-pineapple-400 text-obsidian-950 font-bold px-3.5 py-2 rounded-xl text-xs transition">
                        Send
                    </button>
                </form>
            </div>

            <!-- TAB 2: Mini Community Live Chat Box -->
            <div id="panel-chat" class="hidden flex-col flex-1 overflow-hidden">
                <div id="community-chat-feed" class="p-3.5 space-y-2.5 overflow-y-auto h-72 text-xs">
                    <!-- Populated with lively server chat messages -->
                </div>
                <form onsubmit="handleCommunityChatSubmit(event)" class="p-3 bg-obsidian-850 border-t border-zinc-800 flex gap-2">
                    <input type="text" id="community-chat-input" placeholder="Chat with online players..." class="flex-1 bg-obsidian-950 border border-zinc-700 focus:border-pineapple-500 rounded-xl px-3 py-2 text-xs text-white outline-none">
                    <button type="submit" class="bg-emerald-500 hover:bg-emerald-400 text-obsidian-950 font-bold px-3.5 py-2 rounded-xl text-xs transition">
                        Say
                    </button>
                </form>
            </div>
        </div>

        <!-- Floating Launcher Button -->
        <button onclick="toggleAssistant()" class="mc-btn group bg-pineapple-500 text-obsidian-950 font-extrabold px-4 py-3.5 rounded-2xl flex items-center gap-2.5 shadow-2xl">
            <span class="text-xl group-hover:rotate-12 transition-transform">🍍</span>
            <span class="text-xs sm:text-sm">AI Help & Live Chat</span>
            <span class="w-2.5 h-2.5 rounded-full bg-emerald-600 animate-pulse"></span>
        </button>
    </div>

    <!-- JavaScript Logic -->
    <script>
        // ==========================================
        // 1. DATA & STATE INITIALIZATION
        // ==========================================
        const KITS_DATA = [
            {
                id: 'stone',
                name: 'STONE KIT',
                price: 30,
                badge: 'STARTER PACK',
                accent: 'border-zinc-700/90',
                badgeBg: 'bg-zinc-700 text-zinc-100',
                icon: '🪨',
                featured: false,
                perks: []
            },
            {
                id: 'legend',
                name: 'LEGEND KIT',
                price: 40,
                badge: 'MOST POPULAR',
                accent: 'border-pineapple-400',
                badgeBg: 'bg-pineapple-400 text-obsidian-950',
                icon: '👑',
                featured: true,
                perks: [
                    'Prot 3 Diamond Armour',
                    'Sharpness 3 Sword',
                    '2 Totem',
                    '2 Enchanted Apples',
                    '16 Golden Apples',
                    '16 Ender Pearls',
                    'AND MORE'
                ]
            },
            {
                id: 'iron',
                name: 'IRON KIT',
                price: 50,
                badge: 'COMBAT PACK',
                accent: 'border-slate-500/70',
                badgeBg: 'bg-slate-300 text-obsidian-950',
                icon: '⚔️',
                featured: false,
                perks: []
            },
            {
                id: 'diamond',
                name: 'DIAMOND KIT',
                price: 100,
                badge: 'PRO TIER',
                accent: 'border-cyan-500/70',
                badgeBg: 'bg-cyan-400 text-obsidian-950',
                icon: '💎',
                featured: false,
                perks: []
            },
            {
                id: 'netherite',
                name: 'NETHERITE KIT',
                price: 125,
                badge: 'ELITE TIER',
                accent: 'border-rose-500/70',
                badgeBg: 'bg-rose-500 text-white',
                icon: '🔥',
                featured: false,
                perks: []
            },
            {
                id: 'ender',
                name: 'ENDER KIT',
                price: 150,
                badge: 'MYTHIC TIER',
                accent: 'border-purple-500/70',
                badgeBg: 'bg-purple-500 text-white',
                icon: '🔮',
                featured: false,
                perks: []
            }
        ];

        let globalInsuranceEnabled = false;
        let selectedKit = KITS_DATA[1];
        let countdownSeconds = 5;
        let currentAiLang = 'en';
        let refreshIntervalId = null;

        // ==========================================
        // 2. TOAST & CLIPBOARD HELPERS
        // ==========================================
        function showToast(message, type = 'success') {
            const container = document.getElementById('toast-container');
            if (!container) return;

            const toast = document.createElement('div');
            const bgClass = type === 'error'
                ? 'bg-rose-950/95 border-rose-500 text-rose-100'
                : type === 'info'
                ? 'bg-obsidian-850/95 border-pineapple-500 text-pineapple-300'
                : 'bg-emerald-950/95 border-emerald-500 text-emerald-100';

            toast.className = `pointer-events-auto px-4 py-3 rounded-xl border ${bgClass} shadow-2xl text-xs sm:text-sm font-bold flex items-center gap-2.5 transform transition-all duration-300 translate-x-4 opacity-0`;
            toast.innerHTML = `<span>${type === 'error' ? '⚠️' : type === 'info' ? '🍍' : '✅'}</span><span>${message}</span>`;

            container.appendChild(toast);
            requestAnimationFrame(() => {
                toast.classList.remove('translate-x-4', 'opacity-0');
            });

            setTimeout(() => {
                toast.classList.add('translate-x-4', 'opacity-0');
                setTimeout(() => toast.remove(), 300);
            }, 3200);
        }

        function copyIP(text, label = 'Text') {
            const tempInput = document.createElement('textarea');
            tempInput.value = text;
            tempInput.style.position = 'fixed';
            tempInput.style.opacity = '0';
            document.body.appendChild(tempInput);
            tempInput.select();
            try {
                document.execCommand('copy');
                showToast(`${label} copied: ${text}`, 'success');
            } catch (err) {
                showToast(`Copy failed — please copy manually: ${text}`, 'error');
            }
            document.body.removeChild(tempInput);
        }

        // ==========================================
        // 3. STORE PRICING & RENDERING
        // ==========================================
        function calculateTotalWithInsurance(basePrice, includeInsurance) {
            if (!includeInsurance) {
                return {
                    base: basePrice.toFixed(2),
                    insFee: '0.00',
                    gstFee: '0.00',
                    total: basePrice.toFixed(2)
                };
            }
            const insFee = basePrice * 0.10;
            const gstFee = insFee * 0.05;
            const total = basePrice + insFee + gstFee;
            return {
                base: basePrice.toFixed(2),
                insFee: insFee.toFixed(2),
                gstFee: gstFee.toFixed(2),
                total: total.toFixed(2)
            };
        }

        function syncInsuranceToggle(checked) {
            globalInsuranceEnabled = checked;
            renderKitStore();
            showToast(
                checked
                    ? 'PineappleShield™ Insurance enabled across all kits (+10% + 5% GST)'
                    : 'PineappleShield™ Insurance turned off',
                'info'
            );
        }

        function renderKitStore() {
            const grid = document.getElementById('kits-grid');
            if (!grid) return;

            grid.innerHTML = KITS_DATA.map(kit => {
                const pricing = calculateTotalWithInsurance(kit.price, globalInsuranceEnabled);
                const hasVerifiedPerks = Array.isArray(kit.perks) && kit.perks.length > 0;
                const cardShadow = kit.featured
                    ? 'shadow-[0_20px_50px_rgba(250,204,21,0.16)] ring-1 ring-pineapple-400/40'
                    : 'shadow-xl';

                return `
                    <div class="bg-gradient-to-b from-obsidian-850 to-obsidian-900 border-2 ${kit.accent} rounded-3xl p-6 sm:p-7 flex flex-col justify-between ${cardShadow} relative overflow-hidden transition-transform duration-200 hover:-translate-y-1">
                        <div>
                            <div class="flex items-center justify-between mb-4">
                                <span class="text-3xl sm:text-4xl">${kit.icon}</span>
                                <span class="px-3 py-1 rounded-full text-[11px] font-extrabold tracking-wider ${kit.badgeBg}">
                                    ${kit.badge}
                                </span>
                            </div>

                            <h3 class="font-display font-black text-2xl text-white">${kit.name}</h3>
                            
                            <div class="mt-3 mb-5">
                                <div class="flex items-baseline gap-1.5">
                                    <span class="font-display font-black text-4xl text-pineapple-400">₹${pricing.total}</span>
                                    <span class="text-xs text-zinc-400 font-semibold">INR</span>
                                </div>
                                ${globalInsuranceEnabled 
                                    ? `<div class="text-xs text-emerald-400 font-medium mt-1">Includes ₹${pricing.insFee} Insurance + ₹${pricing.gstFee} GST</div>`
                                    : `<div class="text-xs text-zinc-500 mt-1">Base Price ₹${kit.price} INR</div>`
                                }
                            </div>

                            ${hasVerifiedPerks ? `
                                <div class="text-xs font-bold uppercase tracking-wider text-pineapple-400 mb-3">Kit Includes:</div>
                                <ul class="space-y-2 text-sm text-zinc-200 border-t border-zinc-800 pt-4 mb-6">
                                    ${kit.perks.map(perk => `
                                        <li class="flex items-center gap-2.5">
                                            <span class="w-5 h-5 rounded-md bg-pineapple-500/20 text-pineapple-400 flex items-center justify-center text-xs font-extrabold shrink-0">✓</span>
                                            <span class="${perk === 'AND MORE' ? 'font-extrabold text-pineapple-400 tracking-wide' : 'font-medium'}">${perk}</span>
                                        </li>
                                    `).join('')}
                                </ul>
                            ` : `
                                <div class="border-t border-zinc-800 pt-4 mb-6">
                                    <div class="bg-obsidian-950/80 border border-zinc-800 rounded-2xl p-4 text-center space-y-2">
                                        <span class="inline-block px-2.5 py-1 rounded-lg bg-pineapple-500/10 border border-pineapple-500/30 text-pineapple-400 text-[11px] font-extrabold uppercase tracking-wider">
                                            🎁 Mystery / In-Game Kit Pack
                                        </span>
                                        <p class="text-xs text-zinc-400 leading-relaxed">
                                            Instant in-game kit delivery upon UPI confirmation. Check in-game <code class="text-zinc-300">/kits</code> preview for live contents.
                                        </p>
                                    </div>
                                </div>
                            `}
                        </div>

                        <button onclick="openCheckoutModal('${kit.id}')" class="mc-btn w-full bg-pineapple-500 text-obsidian-950 font-extrabold text-sm py-3.5 rounded-2xl">
                            Buy Now — ₹${pricing.total} ⚔️
                        </button>
                    </div>
                `;
            }).join('');
        }

        // ==========================================
        // 4. UPI CHECKOUT MODAL & QR CODE GENERATOR
        // ==========================================
        function generateQrSvg(upiUri) {
            // Deterministic pseudo-matrix SVG QR representation for ghostmc.fund@axl
            let hash = 0;
            for (let i = 0; i < upiUri.length; i++) {
                hash = ((hash << 5) - hash) + upiUri.charCodeAt(i);
                hash |= 0;
            }
            const size = 21;
            let cells = '';
            for (let r = 0; r < size; r++) {
                for (let c = 0; c < size; c++) {
                    const isFinderTopLeft = r < 7 && c < 7;
                    const isFinderTopRight = r < 7 && c >= size - 7;
                    const isFinderBottomLeft = r >= size - 7 && c < 7;

                    let fill = false;
                    if (isFinderTopLeft || isFinderTopRight || isFinderBottomLeft) {
                        const lr = isFinderBottomLeft ? r - (size - 7) : r;
                        const lc = isFinderTopRight ? c - (size - 7) : c;
                        fill = lr === 0 || lr === 6 || lc === 0 || lc === 6 || (lr >= 2 && lr <= 4 && lc >= 2 && lc <= 4);
                    } else {
                        const seed = Math.abs((hash ^ (r * 31 + c * 17)) * 2654435761);
                        fill = (seed % 3) === 0;
                    }
                    if (fill) {
                        cells += `<rect x="${c}" y="${r}" width="1" height="1" fill="#09090b"/>`;
                    }
                }
            }
            return `<svg viewBox="0 0 ${size} ${size}" class="w-full h-full" shape-rendering="crispEdges">${cells}</svg>`;
        }

        function openCheckoutModal(kitId) {
            const kit = KITS_DATA.find(k => k.id === kitId) || KITS_DATA[1];
            selectedKit = kit;

            document.getElementById('checkout-form-view').classList.remove('hidden');
            document.getElementById('checkout-success-view').classList.add('hidden');
            document.getElementById('modal-kit-name').textContent = kit.name;
            document.getElementById('modal-base-price').textContent = `₹${kit.price.toFixed(2)}`;
            document.getElementById('modal-insurance-checkbox').checked = globalInsuranceEnabled;

            updateModalPricing();

            const modal = document.getElementById('checkout-modal');
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        function closeCheckoutModal() {
            const modal = document.getElementById('checkout-modal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }

        function updateModalPricing() {
            const includeIns = document.getElementById('modal-insurance-checkbox').checked;
            const pricing = calculateTotalWithInsurance(selectedKit.price, includeIns);

            document.getElementById('modal-total-price').textContent = `₹${pricing.total}`;
            const breakdown = document.getElementById('modal-breakdown');
            if (includeIns) {
                breakdown.classList.remove('hidden');
                document.getElementById('modal-ins-fee').textContent = `₹${pricing.insFee}`;
                document.getElementById('modal-gst-fee').textContent = `₹${pricing.gstFee}`;
            } else {
                breakdown.classList.add('hidden');
            }

            const upiUri = `upi://pay?pa=ghostmc.fund@axl&pn=PineappleSMP&am=${pricing.total}&cu=INR&tn=${encodeURIComponent(selectedKit.name)}`;
            document.getElementById('dynamic-qr-container').innerHTML = generateQrSvg(upiUri);
        }

        function submitOrderConfirmation(event) {
            event.preventDefault();
            const ign = document.getElementById('order-mc-username').value.trim();
            const discord = document.getElementById('order-discord-tag').value.trim();
            const utr = document.getElementById('order-utr').value.trim();
            const totalAmount = document.getElementById('modal-total-price').textContent;

            if (!ign || !discord || !utr) {
                showToast('Please fill in all required checkout fields.', 'error');
                return;
            }

            const randomOrderNum = Math.floor(1000 + Math.random() * 9000);
            document.getElementById('receipt-ign').textContent = ign;
            document.getElementById('receipt-kit').textContent = selectedKit.name;
            document.getElementById('receipt-amount').textContent = totalAmount;
            document.getElementById('receipt-order-id').textContent = `#PSMP-${randomOrderNum}`;
            document.getElementById('receipt-discord').textContent = discord;

            document.getElementById('checkout-form-view').classList.add('hidden');
            document.getElementById('checkout-success-view').classList.remove('hidden');
            showToast(`Order #PSMP-${randomOrderNum} submitted for ${ign}!`, 'success');
        }

        // ==========================================
        // 5. LIVE SERVER TELEMETRY (mcsrvstat.us)
        // ==========================================
        async function fetchLiveServerStatus() {
            const statusBadge = document.getElementById('server-status-badge');
            const onlineCountEl = document.getElementById('online-count');
            const maxSlotsEl = document.getElementById('max-slots');
            const pingEl = document.getElementById('server-ping');
            const versionEl = document.getElementById('server-version-text');
            const playersGrid = document.getElementById('online-players-grid');
            const lastUpdatedEl = document.getElementById('last-updated-label');
            const chatOnlineBadge = document.getElementById('chat-online-badge');

            const startTime = performance.now();
            try {
                let res = await fetch('https://api.mcsrvstat.us/3/basic.vitalcloud.in:19126');
                let data = await res.json();

                if (!data || !data.online) {
                    const bedrockRes = await fetch('https://api.mcsrvstat.us/bedrock/3/basic.vitalcloud.in:19149');
                    const bedrockData = await bedrockRes.json();
                    if (bedrockData && bedrockData.online) {
                        data = bedrockData;
                    }
                }

                const latency = Math.max(12, Math.round(performance.now() - startTime));
                pingEl.textContent = latency;

                if (data && data.online) {
                    statusBadge.textContent = 'ONLINE';
                    statusBadge.className = 'px-2.5 py-1 rounded-lg bg-emerald-500/15 text-emerald-400 font-bold text-sm border border-emerald-500/30';

                    const onlinePlayers = data.players?.online ?? 0;
                    const maxPlayers = data.players?.max ?? 100;
                    onlineCountEl.textContent = onlinePlayers;
                    maxSlotsEl.textContent = maxPlayers;
                    if (chatOnlineBadge) chatOnlineBadge.textContent = onlinePlayers;

                    if (data.version) {
                        versionEl.textContent = data.version;
                    }

                    const playerList = Array.isArray(data.players?.list) ? data.players.list : [];
                    if (playerList.length > 0) {
                        playersGrid.innerHTML = playerList.map(p => {
                            const name = typeof p === 'string' ? p : (p.name || 'Player');
                            return `
                                <span class="inline-flex items-center gap-2 px-3 py-1.5 rounded-xl bg-obsidian-900 border border-zinc-700/80 text-xs font-bold text-zinc-200">
                                    <span class="w-2 h-2 rounded-full bg-emerald-400"></span>
                                    ${name}
                                </span>
                            `;
                        }).join('');
                    } else if (onlinePlayers > 0) {
                        playersGrid.innerHTML = `<span class="text-xs text-zinc-300 font-medium">${onlinePlayers} player(s) currently active in-game (player names hidden by server query).</span>`;
                    } else {
                        playersGrid.innerHTML = `<span class="text-xs text-zinc-400">0 players currently online — be the first to hop on <code class="text-pineapple-400">basic.vitalcloud.in:19126</code>!</span>`;
                    }
                } else {
                    statusBadge.textContent = 'OFFLINE / SLEEPING';
                    statusBadge.className = 'px-2.5 py-1 rounded-lg bg-rose-500/15 text-rose-400 font-bold text-sm border border-rose-500/30';
                    onlineCountEl.textContent = '0';
                    if (chatOnlineBadge) chatOnlineBadge.textContent = '0';
                    playersGrid.innerHTML = `<span class="text-xs text-zinc-400">Server node is currently offline or restarting. Try connecting in Minecraft!</span>`;
                }
            } catch (error) {
                statusBadge.textContent = 'SYNCING';
                pingEl.textContent = '--';
                playersGrid.innerHTML = `<span class="text-xs text-zinc-400">Unable to reach mcsrvstat.us API right now. Retrying automatically...</span>`;
            }

            if (lastUpdatedEl) {
                const now = new Date();
                lastUpdatedEl.textContent = `Updated ${now.toLocaleTimeString([], { hour: '2-digit', minute: '2-digit', second: '2-digit' })}`;
            }
        }

        function startTelemetryCountdown() {
            const countdownEl = document.getElementById('refresh-countdown');
            if (refreshIntervalId) clearInterval(refreshIntervalId);
            refreshIntervalId = setInterval(() => {
                countdownSeconds -= 1;
                if (countdownSeconds <= 0) {
                    countdownSeconds = 5;
                    fetchLiveServerStatus();
                }
                if (countdownEl) countdownEl.textContent = countdownSeconds;
            }, 1000);
        }

        function manualRefreshStatus() {
            countdownSeconds = 5;
            const countdownEl = document.getElementById('refresh-countdown');
            if (countdownEl) countdownEl.textContent = countdownSeconds;
            fetchLiveServerStatus();
            showToast('Refreshing live server status...', 'info');
        }

        // ==========================================
        // 6. FLOATING AI ASSISTANT & LIVE CHAT HUB
        // ==========================================
        const AI_RESPONSES = {
            en: {
                welcome: "👋 Hey warrior! I'm the PineappleSMP AI Guide. Ask me about Server IPs, Kit Prices (₹30–₹150), Insurance, or the Nov 29 PvP Event!",
                ip: "🌐 **Java IP:** `basic.vitalcloud.in:19126`\n📱 **Bedrock IP:** `basic.vitalcloud.in` | **Port:** `19149`\nSupports Minecraft 1.20 to 1.21+!",
                kits: "🛒 **PineappleSMP Store Kits:**\n• **Stone Kit:** ₹30\n• **Legend Kit:** ₹40 *(Prot 3 Diamond Armour, Sharpness 3 Sword, 2 Totem, 2 Enchanted Apples, 16 Golden Apples, 16 Ender Pearls & more)*\n• **Iron Kit:** ₹50\n• **Diamond Kit:** ₹100\n• **Netherite Kit:** ₹125\n• **Ender Kit:** ₹150\nPay via UPI (`ghostmc.fund@axl`).",
                insurance: "🛡️ **PineappleShield™ Insurance (+10% + 5% GST):**\nIncludes a **3-hour full refund policy** and **3-day damage/glitch coverage** so you never lose your kit unfairly!",
                event: "🏆 **Mega PvP Event — November 29, 2026!**\nSeason 1 is LIVE now. Grind hearts today and enter the Nov 29 tournament to win prizes!",
                fallback: "🍍 Need help? Ask me about **IP**, **Kits**, **Insurance**, **UPI**, or the **Nov 29 Event**! You can also DM owner `@devesh_37` on Discord."
            },
            hi: {
                welcome: "👋 नमस्ते योद्धा! मैं PineappleSMP AI सहायक हूँ। मुझसे सर्वर IP, सभी Kits (₹30–₹150), इंश्योरेंस या 29 नवंबर PvP इवेंट के बारे में पूछें!",
                ip: "🌐 **Java IP:** `basic.vitalcloud.in:19126`\n📱 **Bedrock IP:** `basic.vitalcloud.in` | **Port:** `19149`\nMinecraft 1.20 से 1.21+ तक सपोर्ट करता है!",
                kits: "🛒 **PineappleSMP स्टोर किट्स:**\n• **Stone Kit:** ₹30\n• **Legend Kit:** ₹40 *(Prot 3 Diamond Armour, Sharpness 3 Sword, 2 Totem, 2 Enchanted Apples, 16 Golden Apples, 16 Ender Pearls और भी बहुत कुछ)*\n• **Iron Kit:** ₹50 | **Diamond:** ₹100 | **Netherite:** ₹125 | **Ender:** ₹150\nUPI ID: `ghostmc.fund@axl`",
                insurance: "🛡️ **किट इंश्योरेंस (+10% + 5% GST):**\nइसमें **3-घंटे की रिफंड पॉलिसी** और **3-दिन की डैमेज/ग्लिच कवरेज** शामिल है!",
                event: "🏆 **मेगा PvP इवेंट — 29 नवंबर 2026!**\nसीज़न 1 अभी लाइव है! आज ही हार्ट्स इकट्ठा करें और 29 नवंबर के टूर्नामेंट में भाग लें!",
                fallback: "🍍 कृपया **IP**, **Kits**, **Insurance**, या **Nov 29 Event** के बारे में पूछें, या Discord पर `@devesh_37` से संपर्क करें।"
            },
            hinglish: {
                welcome: "👋 Yo bhai! Main PineappleSMP ka AI Assistant hoon. Server IP, saare Kits (₹30–₹150), Insurance, ya Nov 29 PvP Event ke baare mein kuch bhi pucho!",
                ip: "🌐 **Java IP:** `basic.vitalcloud.in:19126`\n📱 **Bedrock IP:** `basic.vitalcloud.in` | **Port:** `19149`\nDono Java aur Bedrock (1.20 - 1.21+) pe mast chalta hai!",
                kits: "🛒 **PineappleSMP Store Kits:**\n• **Stone Kit:** ₹30\n• **Legend Kit:** ₹40 *(Prot 3 Diamond Armour, Sharpness 3 Sword, 2 Totem, 2 Enchanted Apples, 16 Golden Apples, 16 Ender Pearls + AND MORE)*\n• **Iron Kit:** ₹50 | **Diamond:** ₹100 | **Netherite:** ₹125 | **Ender:** ₹150\nDirect UPI (`ghostmc.fund@axl`) se buy kar sakte ho!",
                insurance: "🛡️ **Kit Insurance (+10% + 5% GST):**\nIsme **3-hour refund policy** aur **3-day damage coverage** milta hai — agar glitch ya hacker se kit gayi toh free replacement!",
                event: "🏆 **Nov 29, 2026 Mega PvP Event!**\nSeason 1 abhi LIVE hai! Abhi join karke hearts grind karo aur 29 Nov ke tournament mein jeeto!",
                fallback: "🍍 Bhai **IP**, **Kits**, **Insurance**, ya **Nov 29 Event** ke baare mein pucho! Extra help ke liye Discord pe `@devesh_37` ko ping karo."
            }
        };

        function toggleAssistant() {
            const win = document.getElementById('assistant-window');
            if (!win) return;
            win.classList.toggle('hidden');
        }

        function switchHubTab(tab) {
            const panelAi = document.getElementById('panel-ai');
            const panelChat = document.getElementById('panel-chat');
            const tabAi = document.getElementById('tab-ai');
            const tabChat = document.getElementById('tab-chat');

            if (tab === 'ai') {
                panelAi.classList.remove('hidden');
                panelAi.classList.add('flex');
                panelChat.classList.add('hidden');
                panelChat.classList.remove('flex');
                tabAi.className = 'py-1.5 text-xs font-bold rounded-lg bg-pineapple-500 text-obsidian-950 transition';
                tabChat.className = 'py-1.5 text-xs font-bold rounded-lg text-zinc-400 hover:text-white transition';
            } else {
                panelChat.classList.remove('hidden');
                panelChat.classList.add('flex');
                panelAi.classList.add('hidden');
                panelAi.classList.remove('flex');
                tabChat.className = 'py-1.5 text-xs font-bold rounded-lg bg-emerald-500 text-obsidian-950 transition';
                tabAi.className = 'py-1.5 text-xs font-bold rounded-lg text-zinc-400 hover:text-white transition';
            }
        }

        function appendAiBubble(text, sender = 'bot') {
            const container = document.getElementById('ai-messages');
            if (!container) return;

            const wrapper = document.createElement('div');
            wrapper.className = sender === 'user' ? 'flex justify-end' : 'flex justify-start';

            const formatted = text
                .replace(/\*\*(.*?)\*\*/g, '<strong class="text-white">$1</strong>')
                .replace(/`(.*?)`/g, '<code class="text-pineapple-400 bg-obsidian-950 px-1 rounded">$1</code>')
                .replace(/\n/g, '<br>');

            wrapper.innerHTML = sender === 'user'
                ? `<div class="bg-pineapple-500 text-obsidian-950 font-semibold px-3 py-2 rounded-2xl rounded-br-sm max-w-[85%]">${formatted}</div>`
                : `<div class="bg-obsidian-850 border border-zinc-800 text-zinc-200 px-3 py-2.5 rounded-2xl rounded-bl-sm max-w-[90%] leading-relaxed">${formatted}</div>`;

            container.appendChild(wrapper);
            container.scrollTop = container.scrollHeight;
        }

        function setAiLang(lang) {
            currentAiLang = lang;
            ['en', 'hi', 'hinglish'].forEach(l => {
                const btn = document.getElementById(`lang-${l}`);
                if (btn) {
                    btn.className = l === lang
                        ? 'px-2 py-0.5 rounded bg-pineapple-500 text-obsidian-950 font-bold text-[11px]'
                        : 'px-2 py-0.5 rounded bg-obsidian-800 text-zinc-300 font-bold text-[11px]';
                }
            });
            const container = document.getElementById('ai-messages');
            if (container) container.innerHTML = '';
            appendAiBubble(AI_RESPONSES[lang].welcome, 'bot');
        }

        function askQuickQuestion(topic) {
            const labels = {
                ip: 'What are the Server IPs?',
                kits: 'Show all Kit Prices',
                insurance: 'How does Kit Insurance work?',
                event: 'Tell me about the Nov 29 Event'
            };
            appendAiBubble(labels[topic] || topic, 'user');
            setTimeout(() => {
                appendAiBubble(AI_RESPONSES[currentAiLang][topic] || AI_RESPONSES[currentAiLang].fallback, 'bot');
            }, 220);
        }

        function handleAiSubmit(event) {
            event.preventDefault();
            const input = document.getElementById('ai-input');
            const query = input.value.trim();
            if (!query) return;

            appendAiBubble(query, 'user');
            input.value = '';

            const lower = query.toLowerCase();
            let topic = 'fallback';
            if (lower.includes('ip') || lower.includes('port') || lower.includes('java') || lower.includes('bedrock') || lower.includes('join')) {
                topic = 'ip';
            } else if (lower.includes('kit') || lower.includes('price') || lower.includes('legend') || lower.includes('buy') || lower.includes('upi') || lower.includes('cost')) {
                topic = 'kits';
            } else if (lower.includes('insur') || lower.includes('refund') || lower.includes('shield') || lower.includes('gst')) {
                topic = 'insurance';
            } else if (lower.includes('event') || lower.includes('nov') || lower.includes('29') || lower.includes('pvp') || lower.includes('tournament')) {
                topic = 'event';
            }

            setTimeout(() => {
                appendAiBubble(AI_RESPONSES[currentAiLang][topic], 'bot');
            }, 250);
        }

        function initCommunityChat() {
            const feed = document.getElementById('community-chat-feed');
            if (!feed) return;
            const initialMessages = [
                { user: 'Devesh', role: 'OWNER', color: 'text-pineapple-400', text: 'Welcome to PineappleSMP Season 1! Use basic.vitalcloud.in:19126 to join.' },
                { user: 'flaxxy444', role: 'FUNDER', color: 'text-cyan-400', text: 'Legend Kit Prot 3 + Totems is super clean for spawn fights 🔥' },
                { user: 'PineappleBot', role: 'SYSTEM', color: 'text-emerald-400', text: 'Mega PvP Tournament locks in on November 29, 2026!' }
            ];
            feed.innerHTML = initialMessages.map(m => `
                <div class="bg-obsidian-850/90 border border-zinc-800/80 rounded-xl px-3 py-2">
                    <div class="flex items-center gap-1.5 mb-0.5">
                        <span class="font-bold ${m.color}">${m.user}</span>
                        <span class="text-[9px] px-1.5 py-0.2 rounded bg-obsidian-950 text-zinc-400 font-bold">${m.role}</span>
                    </div>
                    <div class="text-zinc-200 leading-snug">${m.text}</div>
                </div>
            `).join('');
        }

        function handleCommunityChatSubmit(event) {
            event.preventDefault();
            const input = document.getElementById('community-chat-input');
            const text = input.value.trim();
            if (!text) return;

            const feed = document.getElementById('community-chat-feed');
            const msgEl = document.createElement('div');
            msgEl.className = 'bg-obsidian-850/90 border border-emerald-500/30 rounded-xl px-3 py-2';
            msgEl.innerHTML = `
                <div class="flex items-center gap-1.5 mb-0.5">
                    <span class="font-bold text-emerald-400">You (Guest)</span>
                    <span class="text-[9px] px-1.5 py-0.2 rounded bg-obsidian-950 text-zinc-400 font-bold">PLAYER</span>
                </div>
                <div class="text-zinc-200 leading-snug"></div>
            `;
            msgEl.querySelector('div:last-child').textContent = text;
            feed.appendChild(msgEl);
            feed.scrollTop = feed.scrollHeight;
            input.value = '';
        }

        // ==========================================
        // 7. INITIALIZE ON PAGE LOAD
        // ==========================================
        window.addEventListener('DOMContentLoaded', () => {
            renderKitStore();
            setAiLang('en');
            initCommunityChat();
            fetchLiveServerStatus();
            startTelemetryCountdown();
        });
    </script>
</body>
</html>
