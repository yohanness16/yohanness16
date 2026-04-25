html_content = '''<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Yohannes Desalegn | Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        'inter': ['Inter', 'sans-serif'],
                        'space': ['Space Grotesk', 'sans-serif'],
                    },
                    colors: {
                        primary: '#6366f1',
                        secondary: '#8b5cf6',
                        accent: '#06b6d4',
                        dark: '#0f172a',
                        darker: '#020617',
                    },
                    animation: {
                        'float': 'float 6s ease-in-out infinite',
                        'pulse-slow': 'pulse 4s cubic-bezier(0.4, 0, 0.6, 1) infinite',
                        'spin-slow': 'spin 12s linear infinite',
                        'bounce-slow': 'bounce 3s infinite',
                    }
                }
            }
        }
    </script>
    <style>
        :root {
            --primary: #6366f1;
            --secondary: #8b5cf6;
            --accent: #06b6d4;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background: #020617;
            color: #e2e8f0;
            overflow-x: hidden;
        }
        
        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #0f172a;
        }
        ::-webkit-scrollbar-thumb {
            background: linear-gradient(180deg, var(--primary), var(--secondary));
            border-radius: 4px;
        }
        
        /* 3D Card Effect */
        .card-3d {
            transform-style: preserve-3d;
            transition: transform 0.5s cubic-bezier(0.23, 1, 0.32, 1);
        }
        .card-3d:hover {
            transform: translateY(-10px) rotateX(5deg) rotateY(5deg);
        }
        
        /* Glassmorphism */
        .glass {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .glass-strong {
            background: rgba(15, 23, 42, 0.7);
            backdrop-filter: blur(30px);
            -webkit-backdrop-filter: blur(30px);
            border: 1px solid rgba(255, 255, 255, 0.08);
        }
        
        /* Gradient Text */
        .gradient-text {
            background: linear-gradient(135deg, #6366f1, #8b5cf6, #06b6d4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        .gradient-text-alt {
            background: linear-gradient(135deg, #f472b6, #a78bfa, #22d3ee);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        /* Glow Effects */
        .glow {
            box-shadow: 0 0 40px rgba(99, 102, 241, 0.3), 0 0 80px rgba(139, 92, 246, 0.1);
        }
        
        .glow-accent {
            box-shadow: 0 0 40px rgba(6, 182, 212, 0.3);
        }
        
        /* Animated Background */
        .bg-grid {
            background-image: 
                linear-gradient(rgba(99, 102, 241, 0.03) 1px, transparent 1px),
                linear-gradient(90deg, rgba(99, 102, 241, 0.03) 1px, transparent 1px);
            background-size: 50px 50px;
        }
        
        /* Floating Orbs */
        .orb {
            position: absolute;
            border-radius: 50%;
            filter: blur(80px);
            opacity: 0.4;
            animation: float 8s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px) scale(1); }
            50% { transform: translateY(-30px) scale(1.1); }
        }
        
        /* Skill Badge Hover */
        .skill-badge {
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }
        .skill-badge:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 20px 40px rgba(99, 102, 241, 0.2);
        }
        
        /* Social Link Hover */
        .social-link {
            position: relative;
            overflow: hidden;
        }
        .social-link::before {
            content: '';
            position: absolute;
            inset: 0;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            opacity: 0;
            transition: opacity 0.3s;
            border-radius: inherit;
        }
        .social-link:hover::before {
            opacity: 1;
        }
        .social-link:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(99, 102, 241, 0.3);
        }
        
        /* Stats Counter Animation */
        @keyframes countUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* Timeline */
        .timeline-line {
            background: linear-gradient(180deg, var(--primary), var(--accent));
        }
        
        /* Reveal Animation */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s cubic-bezier(0.23, 1, 0.32, 1);
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }
        
        /* Custom Cursor */
        .cursor-dot {
            width: 8px;
            height: 8px;
            background: var(--primary);
            border-radius: 50%;
            position: fixed;
            pointer-events: none;
            z-index: 9999;
            transition: transform 0.1s;
        }
        .cursor-outline {
            width: 40px;
            height: 40px;
            border: 2px solid rgba(99, 102, 241, 0.3);
            border-radius: 50%;
            position: fixed;
            pointer-events: none;
            z-index: 9998;
            transition: all 0.15s ease-out;
        }
        
        /* Typewriter */
        .typewriter {
            overflow: hidden;
            border-right: 3px solid var(--primary);
            white-space: nowrap;
            animation: typing 3.5s steps(40, end), blink-caret 0.75s step-end infinite;
        }
        
        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }
        
        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: var(--primary) }
        }
        
        /* Particle Canvas */
        #particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }
        
        /* Section Divider */
        .section-divider {
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(99, 102, 241, 0.3), transparent);
        }
        
        /* Achievement Card */
        .achievement-card {
            background: linear-gradient(135deg, rgba(99, 102, 241, 0.1), rgba(139, 92, 246, 0.05));
            border: 1px solid rgba(99, 102, 241, 0.1);
        }
        
        /* Explore Item */
        .explore-item {
            background: linear-gradient(135deg, rgba(6, 182, 212, 0.05), rgba(99, 102, 241, 0.05));
            border: 1px solid rgba(6, 182, 212, 0.1);
            transition: all 0.4s cubic-bezier(0.23, 1, 0.32, 1);
        }
        .explore-item:hover {
            transform: translateX(10px);
            background: linear-gradient(135deg, rgba(6, 182, 212, 0.1), rgba(99, 102, 241, 0.1));
            border-color: rgba(6, 182, 212, 0.3);
        }
        
        /* 3D Tilt Container */
        .tilt-container {
            perspective: 1000px;
        }
        .tilt-element {
            transform-style: preserve-3d;
            transition: transform 0.1s ease-out;
        }
        
        /* Loading Animation */
        .loading-bar {
            height: 3px;
            background: linear-gradient(90deg, var(--primary), var(--secondary), var(--accent));
            background-size: 200% 100%;
            animation: shimmer 2s infinite;
        }
        
        @keyframes shimmer {
            0% { background-position: 200% 0; }
            100% { background-position: -200% 0; }
        }
    </style>
</head>
<body class="bg-darker min-h-screen relative">
    <!-- Particle Background -->
    <canvas id="particles"></canvas>
    
    <!-- Custom Cursor -->
    <div class="cursor-dot hidden md:block" id="cursor-dot"></div>
    <div class="cursor-outline hidden md:block" id="cursor-outline"></div>
    
    <!-- Floating Orbs -->
    <div class="fixed inset-0 overflow-hidden pointer-events-none z-0">
        <div class="orb w-96 h-96 bg-primary/30 top-0 left-1/4" style="animation-delay: 0s;"></div>
        <div class="orb w-80 h-80 bg-secondary/20 top-1/3 right-1/4" style="animation-delay: 2s;"></div>
        <div class="orb w-72 h-72 bg-accent/20 bottom-1/4 left-1/3" style="animation-delay: 4s;"></div>
    </div>
    
    <!-- Grid Background -->
    <div class="fixed inset-0 bg-grid pointer-events-none z-0 opacity-50"></div>
    
    <!-- Navigation -->
    <nav class="fixed top-0 left-0 right-0 z-50 glass-strong border-b border-white/5">
        <div class="max-w-7xl mx-auto px-6 py-4 flex justify-between items-center">
            <div class="font-space font-bold text-xl gradient-text">YD.</div>
            <div class="hidden md:flex gap-8 text-sm font-medium text-slate-400">
                <a href="#about" class="hover:text-white transition-colors">About</a>
                <a href="#skills" class="hover:text-white transition-colors">Skills</a>
                <a href="#stats" class="hover:text-white transition-colors">Stats</a>
                <a href="#explore" class="hover:text-white transition-colors">Exploring</a>
                <a href="#connect" class="hover:text-white transition-colors">Connect</a>
            </div>
            <a href="mailto:yohanness1621@gmail.com" class="px-6 py-2 rounded-full bg-gradient-to-r from-primary to-secondary text-white text-sm font-medium hover:shadow-lg hover:shadow-primary/25 transition-all hover:-translate-y-0.5">
                Let's Talk
            </a>
        </div>
    </nav>
    
    <!-- Hero Section -->
    <section class="relative min-h-screen flex items-center justify-center pt-20 z-10">
        <div class="max-w-6xl mx-auto px-6 text-center">
            <div class="reveal active">
                <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full glass mb-8">
                    <span class="w-2 h-2 rounded-full bg-green-400 animate-pulse"></span>
                    <span class="text-sm text-slate-300">Available for opportunities</span>
                </div>
            </div>
            
            <h1 class="reveal font-space font-bold text-5xl md:text-7xl lg:text-8xl mb-6 leading-tight" style="transition-delay: 0.1s;">
                Hi, I'm <span class="gradient-text">Yohannes</span><br>
                <span class="text-slate-400 text-3xl md:text-5xl lg:text-6xl">Desalegn</span>
            </h1>
            
            <div class="reveal mb-8" style="transition-delay: 0.2s;">
                <p class="text-xl md:text-2xl text-slate-400 font-light max-w-2xl mx-auto">
                    Electrical & Computer Engineering Student @ <span class="text-primary font-medium">AASTU</span>
                </p>
                <div class="mt-4 h-8">
                    <p class="text-lg text-slate-500 typewriter inline-block" style="animation-delay: 1s;">
                        Building at the intersection of software, hardware, and security
                    </p>
                </div>
            </div>
            
            <div class="reveal flex flex-wrap justify-center gap-4 mb-12" style="transition-delay: 0.3s;">
                <span class="px-4 py-2 rounded-full glass text-sm text-slate-300 border border-primary/20">
                    <i class="fas fa-code mr-2 text-primary"></i>Full Stack
                </span>
                <span class="px-4 py-2 rounded-full glass text-sm text-slate-300 border border-secondary/20">
                    <i class="fas fa-microchip mr-2 text-secondary"></i>Embedded
                </span>
                <span class="px-4 py-2 rounded-full glass text-sm text-slate-300 border border-accent/20">
                    <i class="fas fa-shield-alt mr-2 text-accent"></i>Security
                </span>
            </div>
            
            <div class="reveal flex justify-center gap-4" style="transition-delay: 0.4s;">
                <a href="https://github.com/yohanness16" target="_blank" class="social-link relative px-8 py-3 rounded-full glass text-white font-medium transition-all">
                    <span class="relative z-10 flex items-center gap-2">
                        <i class="fab fa-github"></i> GitHub
                    </span>
                </a>
                <a href="https://linkedin.com/in/yohannes-desalegn" target="_blank" class="social-link relative px-8 py-3 rounded-full glass text-white font-medium transition-all">
                    <span class="relative z-10 flex items-center gap-2">
                        <i class="fab fa-linkedin"></i> LinkedIn
                    </span>
                </a>
            </div>
            
            <!-- Scroll Indicator -->
            <div class="absolute bottom-10 left-1/2 -translate-x-1/2 animate-bounce">
                <div class="w-6 h-10 rounded-full border-2 border-slate-600 flex justify-center pt-2">
                    <div class="w-1 h-2 bg-primary rounded-full animate-pulse"></div>
                </div>
            </div>
        </div>
    </section>
    
    <div class="section-divider max-w-4xl mx-auto"></div>
    
    <!-- Tech Stack Section -->
    <section id="skills" class="relative py-24 z-10">
        <div class="max-w-7xl mx-auto px-6">
            <div class="reveal text-center mb-16">
                <h2 class="font-space font-bold text-4xl md:text-5xl mb-4">
                    <span class="gradient-text">Tech Stack</span>
                </h2>
                <p class="text-slate-400 max-w-xl mx-auto">Technologies and tools I use to bring ideas to life</p>
            </div>
            
            <!-- Languages -->
            <div class="reveal mb-12" style="transition-delay: 0.1s;">
                <h3 class="font-space font-semibold text-xl mb-6 text-slate-300 flex items-center gap-2">
                    <i class="fas fa-code text-primary"></i> Languages
                </h3>
                <div class="grid grid-cols-2 md:grid-cols-4 lg:grid-cols-6 gap-4">
                    <div class="skill-badge glass rounded-2xl p-6 text-center cursor-pointer group">
                        <i class="fab fa-js text-4xl text-yellow-400 mb-3 group-hover:scale-110 transition-transform"></i>
                        <p class="text-sm font-medium text-slate-300">JavaScript</p>
                    </div>
                    <div class="skill-badge glass rounded-2xl p-6 text-center cursor-pointer group">
                        <i class="fab fa-python text-4xl text-blue-400 mb-3 group-hover:scale-110 transition-transform"></i>
                        <p class="text-sm font-medium text-slate-300">Python</p>
                    </div>
                    <div class="skill-badge glass rounded-2xl p-6 text-center cursor-pointer group">
                        <i class="fas fa-c text-4xl text-blue-300 mb-3 group-hover:scale-110 transition-transform"></i>
                        <p class="text-sm font-medium text-slate-300">C</p>
                    </div>
                    <div class="skill-badge glass rounded-2xl p-6 text-center cursor-pointer group">
                        <i class="fab fa-rust text-4xl text-orange-400 mb-3 group-hover:scale-110 transition-transform"></i>
                        <p class="text-sm font-medium text-slate-300">Rust</p>
                    </div>
                    <div class="skill-badge glass rounded-2xl p-6 text-center cursor-pointer group">
                        <i class="fab fa-golang text-4xl text-cyan-400 mb-3 group-hover:scale-110 transition-transform"></i>
                        <p class="text-sm font-medium text-slate-300">Go</p>
                    </div>
                    <div class="skill-badge glass rounded-2xl p-6 text-center cursor-pointer group">
                        <i class="fab fa-java text-4xl text-red-400 mb-3 group-hover:scale-110 transition-transform"></i>
                        <p class="text-sm font-medium text-slate-300">Java</p>
                    </div>
                    <div class="skill-badge glass rounded-2xl p-6 text-center cursor-pointer group">
                        <i class="fas fa-plus text-4xl text-blue-500 mb-3 group-hover:scale-110 transition-transform"></i>
                        <p class="text-sm font-medium text-slate-300">C++</p>
                    </div>
                    <div class="skill-badge glass rounded-2xl p-6 text-center cursor-pointer group">
                        <i class="fab fa-html5 text-4xl text-orange-500 mb-3 group-hover:scale-110 transition-transform"></i>
                        <p class="text-sm font-medium text-slate-300">HTML</p>
                    </div>
                    <div class="skill-badge glass rounded-2xl p-6 text-center cursor-pointer group">
                        <i class="fab fa-css3-alt text-4xl text-blue-500 mb-3 group-hover:scale-110 transition-transform"></i>
                        <p class="text-sm font-medium text-slate-300">CSS</p>
                    </div>
                    <div class="skill-badge glass rounded-2xl p-6 text-center cursor-pointer group">
                        <i class="fas fa-terminal text-4xl text-green-400 mb-3 group-hover:scale-110 transition-transform"></i>
                        <p class="text-sm font-medium text-slate-300">Bash</p>
                    </div>
                    <div class="skill-badge glass rounded-2xl p-6 text-center cursor-pointer group">
                        <i class="fab fa-ts text-4xl text-blue-400 mb-3 group-hover:scale-110 transition-transform"></i>
                        <p class="text-sm font-medium text-slate-300">TypeScript</p>
                    </div>
                </div>
            </div>
            
            <!-- Frontend & Backend -->
            <div class="grid md:grid-cols-2 gap-8 mb-12">
                <div class="reveal" style="transition-delay: 0.2s;">
                    <h3 class="font-space font-semibold text-xl mb-6 text-slate-300 flex items-center gap-2">
                        <i class="fas fa-laptop-code text-secondary"></i> Frontend
                    </h3>
                    <div class="flex flex-wrap gap-3">
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fab fa-react text-2xl text-cyan-400"></i>
                            <span class="text-sm font-medium">React</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-n text-2xl text-white"></i>
                            <span class="text-sm font-medium">Next.js</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-wind text-2xl text-cyan-300"></i>
                            <span class="text-sm font-medium">Tailwind</span>
                        </div>
                    </div>
                </div>
                
                <div class="reveal" style="transition-delay: 0.3s;">
                    <h3 class="font-space font-semibold text-xl mb-6 text-slate-300 flex items-center gap-2">
                        <i class="fas fa-server text-accent"></i> Backend
                    </h3>
                    <div class="flex flex-wrap gap-3">
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fab fa-node text-2xl text-green-500"></i>
                            <span class="text-sm font-medium">Node.js</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-bolt text-2xl text-yellow-400"></i>
                            <span class="text-sm font-medium">Express</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fab fa-python text-2xl text-blue-400"></i>
                            <span class="text-sm font-medium">Flask</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-rocket text-2xl text-green-400"></i>
                            <span class="text-sm font-medium">FastAPI</span>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Mobile & Databases -->
            <div class="grid md:grid-cols-2 gap-8 mb-12">
                <div class="reveal" style="transition-delay: 0.4s;">
                    <h3 class="font-space font-semibold text-xl mb-6 text-slate-300 flex items-center gap-2">
                        <i class="fas fa-mobile-alt text-pink-400"></i> Mobile
                    </h3>
                    <div class="flex flex-wrap gap-3">
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fab fa-react text-2xl text-cyan-400"></i>
                            <span class="text-sm font-medium">React Native</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fab fa-android text-2xl text-green-400"></i>
                            <span class="text-sm font-medium">Kotlin</span>
                        </div>
                    </div>
                </div>
                
                <div class="reveal" style="transition-delay: 0.5s;">
                    <h3 class="font-space font-semibold text-xl mb-6 text-slate-300 flex items-center gap-2">
                        <i class="fas fa-database text-emerald-400"></i> Databases
                    </h3>
                    <div class="flex flex-wrap gap-3">
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-elephant text-2xl text-blue-300"></i>
                            <span class="text-sm font-medium">PostgreSQL</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-leaf text-2xl text-green-500"></i>
                            <span class="text-sm font-medium">MongoDB</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-database text-2xl text-blue-400"></i>
                            <span class="text-sm font-medium">SQLite</span>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- ML & Embedded -->
            <div class="grid md:grid-cols-2 gap-8 mb-12">
                <div class="reveal" style="transition-delay: 0.6s;">
                    <h3 class="font-space font-semibold text-xl mb-6 text-slate-300 flex items-center gap-2">
                        <i class="fas fa-brain text-purple-400"></i> ML & Data
                    </h3>
                    <div class="flex flex-wrap gap-3">
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-fire text-2xl text-orange-500"></i>
                            <span class="text-sm font-medium">PyTorch</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-cube text-2xl text-orange-400"></i>
                            <span class="text-sm font-medium">TensorFlow</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-chart-line text-2xl text-blue-400"></i>
                            <span class="text-sm font-medium">Scikit-learn</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-table text-2xl text-blue-300"></i>
                            <span class="text-sm font-medium">NumPy</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-pandas text-2xl text-purple-400"></i>
                            <span class="text-sm font-medium">Pandas</span>
                        </div>
                    </div>
                </div>
                
                <div class="reveal" style="transition-delay: 0.7s;">
                    <h3 class="font-space font-semibold text-xl mb-6 text-slate-300 flex items-center gap-2">
                        <i class="fas fa-microchip text-cyan-400"></i> Embedded & IoT
                    </h3>
                    <div class="flex flex-wrap gap-3">
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-arduino text-2xl text-teal-400"></i>
                            <span class="text-sm font-medium">Arduino</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fab fa-raspberry-pi text-2xl text-red-400"></i>
                            <span class="text-sm font-medium">Raspberry Pi</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-wifi text-2xl text-red-500"></i>
                            <span class="text-sm font-medium">ESP32</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-microchip text-2xl text-blue-500"></i>
                            <span class="text-sm font-medium">STM32</span>
                        </div>
                    </div>
                </div>
            </div>
            
            <!-- Security & Tools -->
            <div class="grid md:grid-cols-2 gap-8">
                <div class="reveal" style="transition-delay: 0.8s;">
                    <h3 class="font-space font-semibold text-xl mb-6 text-slate-300 flex items-center gap-2">
                        <i class="fas fa-shield-alt text-red-400"></i> Security Tools
                    </h3>
                    <div class="flex flex-wrap gap-3">
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-bug text-2xl text-orange-500"></i>
                            <span class="text-sm font-medium">Burp Suite</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-network-wired text-2xl text-blue-500"></i>
                            <span class="text-sm font-medium">Wireshark</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-search text-2xl text-purple-400"></i>
                            <span class="text-sm font-medium">Nmap</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-terminal text-2xl text-blue-600"></i>
                            <span class="text-sm font-medium">Metasploit</span>
                        </div>
                    </div>
                </div>
                
                <div class="reveal" style="transition-delay: 0.9s;">
                    <h3 class="font-space font-semibold text-xl mb-6 text-slate-300 flex items-center gap-2">
                        <i class="fas fa-tools text-slate-400"></i> Tools & Platforms
                    </h3>
                    <div class="flex flex-wrap gap-3">
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fab fa-git-alt text-2xl text-orange-500"></i>
                            <span class="text-sm font-medium">Git</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fab fa-docker text-2xl text-blue-400"></i>
                            <span class="text-sm font-medium">Docker</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fab fa-linux text-2xl text-yellow-400"></i>
                            <span class="text-sm font-medium">Linux</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fas fa-server text-2xl text-green-400"></i>
                            <span class="text-sm font-medium">Nginx</span>
                        </div>
                        <div class="skill-badge glass rounded-xl px-5 py-3 flex items-center gap-3 cursor-pointer">
                            <i class="fab fa-figma text-2xl text-purple-400"></i>
                            <span class="text-sm font-medium">Figma</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <div class="section-divider max-w-4xl mx-auto"></div>
    
    <!-- GitHub Stats Section -->
    <section id="stats" class="relative py-24 z-10">
        <div class="max-w-7xl mx-auto px-6">
            <div class="reveal text-center mb-16">
                <h2 class="font-space font-bold text-4xl md:text-5xl mb-4">
                    <span class="gradient-text-alt">GitHub Stats</span>
                </h2>
                <p class="text-slate-400 max-w-xl mx-auto">My coding journey in numbers</p>
            </div>
            
            <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6 mb-12">
                <div class="reveal tilt-container" style="transition-delay: 0.1s;">
                    <div class="tilt-element glass rounded-3xl p-8 text-center card-3d glow">
                        <div class="text-5xl font-bold gradient-text mb-2" data-count="19">0</div>
                        <p class="text-slate-400 text-sm">Public Repositories</p>
                        <i class="fab fa-github text-4xl text-slate-600 mt-4"></i>
                    </div>
                </div>
                
                <div class="reveal tilt-container" style="transition-delay: 0.2s;">
                    <div class="tilt-element glass rounded-3xl p-8 text-center card-3d glow-accent">
                        <div class="text-5xl font-bold gradient-text-alt mb-2" data-count="1">0</div>
                        <p class="text-slate-400 text-sm">Followers</p>
                        <i class="fas fa-users text-4xl text-slate-600 mt-4"></i>
                    </div>
                </div>
                
                <div class="reveal tilt-container" style="transition-delay: 0.3s;">
                    <div class="tilt-element glass rounded-3xl p-8 text-center card-3d glow">
                        <div class="text-5xl font-bold text-green-400 mb-2">Active</div>
                        <p class="text-slate-400 text-sm">Status</p>
                        <div class="w-3 h-3 bg-green-400 rounded-full mx-auto mt-4 animate-pulse"></div>
                    </div>
                </div>
                
                <div class="reveal tilt-container" style="transition-delay: 0.4s;">
                    <div class="tilt-element glass rounded-3xl p-8 text-center card-3d glow-accent">
                        <div class="text-5xl font-bold text-cyan-400 mb-2">Student</div>
                        <p class="text-slate-400 text-sm">Role</p>
                        <i class="fas fa-graduation-cap text-4xl text-slate-600 mt-4"></i>
                    </div>
                </div>
            </div>
            
            <!-- Achievement Cards -->
            <div class="reveal grid md:grid-cols-2 gap-6" style="transition-delay: 0.5s;">
                <div class="achievement-card rounded-3xl p-8">
                    <div class="flex items-center gap-4 mb-4">
                        <div class="w-12 h-12 rounded-2xl bg-primary/20 flex items-center justify-center">
                            <i class="fas fa-code-branch text-primary text-xl"></i>
                        </div>
                        <div>
                            <h4 class="font-space font-semibold text-lg">Growing Network</h4>
                            <p class="text-slate-400 text-sm">Building connections in the dev community</p>
                        </div>
                    </div>
                    <div class="loading-bar rounded-full mt-4"></div>
                </div>
                
                <div class="achievement-card rounded-3xl p-8">
                    <div class="flex items-center gap-4 mb-4">
                        <div class="w-12 h-12 rounded-2xl bg-secondary/20 flex items-center justify-center">
                            <i class="fas fa-fire text-secondary text-xl"></i>
                        </div>
                        <div>
                            <h4 class="font-space font-semibold text-lg">Active Contributor</h4>
                            <p class="text-slate-400 text-sm">Consistently pushing code and learning</p>
                        </div>
                    </div>
                    <div class="loading-bar rounded-full mt-4"></div>
                </div>
            </div>
        </div>
    </section>
    
    <div class="section-divider max-w-4xl mx-auto"></div>
    
    <!-- Currently Exploring Section -->
    <section id="explore" class="relative py-24 z-10">
        <div class="max-w-7xl mx-auto px-6">
            <div class="reveal text-center mb-16">
                <h2 class="font-space font-bold text-4xl md:text-5xl mb-4">
                    <span class="gradient-text">Currently Exploring</span>
                </h2>
                <p class="text-slate-400 max-w-xl mx-auto">Areas I'm diving deep into right now</p>
            </div>
            
            <div class="grid md:grid-cols-2 gap-6 max-w-4xl mx-auto">
                <div class="reveal explore-item rounded-2xl p-6 flex items-center gap-4 cursor-pointer" style="transition-delay: 0.1s;">
                    <div class="w-14 h-14 rounded-2xl bg-orange-500/10 flex items-center justify-center flex-shrink-0">
                        <i class="fas fa-brain text-orange-400 text-2xl"></i>
                    </div>
                    <div>
                        <h4 class="font-space font-semibold text-lg mb-1">Deep Learning Architectures</h4>
                        <p class="text-slate-400 text-sm">Neural networks, CNNs, RNNs, and Transformers</p>
                    </div>
                </div>
                
                <div class="reveal explore-item rounded-2xl p-6 flex items-center gap-4 cursor-pointer" style="transition-delay: 0.2s;">
                    <div class="w-14 h-14 rounded-2xl bg-blue-500/10 flex items-center justify-center flex-shrink-0">
                        <i class="fab fa-docker text-blue-400 text-2xl"></i>
                    </div>
                    <div>
                        <h4 class="font-space font-semibold text-lg mb-1">Cloud-Native Microservices</h4>
                        <p class="text-slate-400 text-sm">Kubernetes, Docker orchestration, and scalable systems</p>
                    </div>
                </div>
                
                <div class="reveal explore-item rounded-2xl p-6 flex items-center gap-4 cursor-pointer" style="transition-delay: 0.3s;">
                    <div class="w-14 h-14 rounded-2xl bg-red-500/10 flex items-center justify-center flex-shrink-0">
                        <i class="fas fa-shield-alt text-red-400 text-2xl"></i>
                    </div>
                    <div>
                        <h4 class="font-space font-semibold text-lg mb-1">Secure Boot & HW Security</h4>
                        <p class="text-slate-400 text-sm">Firmware security, TPM, and hardware-level protection</p>
                    </div>
                </div>
                
                <div class="reveal explore-item rounded-2xl p-6 flex items-center gap-4 cursor-pointer" style="transition-delay: 0.4s;">
                    <div class="w-14 h-14 rounded-2xl bg-teal-500/10 flex items-center justify-center flex-shrink-0">
                        <i class="fas fa-network-wired text-teal-400 text-2xl"></i>
                    </div>
                    <div>
                        <h4 class="font-space font-semibold text-lg mb-1">Protocol-Level Security</h4>
                        <p class="text-slate-400 text-sm">Network protocols, encryption, and secure communications</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <div class="section-divider max-w-4xl mx-auto"></div>
    
    <!-- Connect Section -->
    <section id="connect" class="relative py-24 z-10">
        <div class="max-w-4xl mx-auto px-6 text-center">
            <div class="reveal mb-16">
                <h2 class="font-space font-bold text-4xl md:text-5xl mb-4">
                    <span class="gradient-text-alt">Let's Connect</span>
                </h2>
                <p class="text-slate-400 max-w-xl mx-auto">Open for collaborations, opportunities, and interesting conversations</p>
            </div>
            
            <div class="reveal flex flex-wrap justify-center gap-4 mb-12" style="transition-delay: 0.2s;">
                <a href="mailto:yohanness1621@gmail.com" class="group relative px-8 py-4 rounded-2xl glass overflow-hidden transition-all hover:-translate-y-1 hover:shadow-xl hover:shadow-red-500/10">
                    <div class="absolute inset-0 bg-gradient-to-r from-red-500/10 to-orange-500/10 opacity-0 group-hover:opacity-100 transition-opacity"></div>
                    <span class="relative z-10 flex items-center gap-3">
                        <i class="fas fa-envelope text-red-400 text-xl"></i>
                        <span class="font-medium">Email</span>
                    </span>
                </a>
                
                <a href="https://linkedin.com/in/yohannes-desalegn" target="_blank" class="group relative px-8 py-4 rounded-2xl glass overflow-hidden transition-all hover:-translate-y-1 hover:shadow-xl hover:shadow-blue-500/10">
                    <div class="absolute inset-0 bg-gradient-to-r from-blue-500/10 to-cyan-500/10 opacity-0 group-hover:opacity-100 transition-opacity"></div>
                    <span class="relative z-10 flex items-center gap-3">
                        <i class="fab fa-linkedin text-blue-400 text-xl"></i>
                        <span class="font-medium">LinkedIn</span>
                    </span>
                </a>
                
                <a href="https://twitter.com/yohannesdev" target="_blank" class="group relative px-8 py-4 rounded-2xl glass overflow-hidden transition-all hover:-translate-y-1 hover:shadow-xl hover:shadow-sky-500/10">
                    <div class="absolute inset-0 bg-gradient-to-r from-sky-500/10 to-blue-500/10 opacity-0 group-hover:opacity-100 transition-opacity"></div>
                    <span class="relative z-10 flex items-center gap-3">
                        <i class="fab fa-twitter text-sky-400 text-xl"></i>
                        <span class="font-medium">Twitter</span>
                    </span>
                </a>
                
                <a href="https://github.com/yohanness16" target="_blank" class="group relative px-8 py-4 rounded-2xl glass overflow-hidden transition-all hover:-translate-y-1 hover:shadow-xl hover:shadow-purple-500/10">
                    <div class="absolute inset-0 bg-gradient-to-r from-purple-500/10 to-pink-500/10 opacity-0 group-hover:opacity-100 transition-opacity"></div>
                    <span class="relative z-10 flex items-center gap-3">
                        <i class="fab fa-github text-purple-400 text-xl"></i>
                        <span class="font-medium">GitHub</span>
                    </span>
                </a>
            </div>
            
            <!-- Quote -->
            <div class="reveal glass rounded-3xl p-8 max-w-2xl mx-auto" style="transition-delay: 0.4s;">
                <i class="fas fa-quote-left text-4xl text-primary/30 mb-4"></i>
                <p class="text-xl md:text-2xl font-space font-medium text-slate-300 italic leading-relaxed">
                    "Engineers are not just builders — we are translators between human needs and technical possibility."
                </p>
                <div class="mt-6 flex items-center justify-center gap-2">
                    <div class="w-8 h-0.5 bg-primary/50"></div>
                    <span class="text-sm text-slate-500">Yohannes Desalegn</span>
                    <div class="w-8 h-0.5 bg-primary/50"></div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Footer -->
    <footer class="relative py-12 z-10 border-t border-white/5">
        <div class="max-w-7xl mx-auto px-6 flex flex-col md:flex-row justify-between items-center gap-4">
            <div class="font-space font-bold text-2xl gradient-text">YD.</div>
            <p class="text-slate-500 text-sm"> Electrical & Computer Engineering Student @ AASTU</p>
            <div class="flex gap-4">
                <a href="https://github.com/yohanness16" class="text-slate-500 hover:text-white transition-colors">
                    <i class="fab fa-github text-xl"></i>
                </a>
                <a href="https://linkedin.com/in/yohannes-desalegn" class="text-slate-500 hover:text-white transition-colors">
                    <i class="fab fa-linkedin text-xl"></i>
                </a>
                <a href="https://twitter.com/yohannesdev" class="text-slate-500 hover:text-white transition-colors">
                    <i class="fab fa-twitter text-xl"></i>
                </a>
            </div>
        </div>
    </footer>
    
    <script>
        // Particle System
        const canvas = document.getElementById('particles');
        const ctx = canvas.getContext('2d');
        let particles = [];
        let mouseX = 0;
        let mouseY = 0;
        
        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }
        resizeCanvas();
        window.addEventListener('resize', resizeCanvas);
        
        class Particle {
            constructor() {
                this.x = Math.random() * canvas.width;
                this.y = Math.random() * canvas.height;
                this.size = Math.random() * 2 + 0.5;
                this.speedX = Math.random() * 0.5 - 0.25;
                this.speedY = Math.random() * 0.5 - 0.25;
                this.opacity = Math.random() * 0.5 + 0.1;
            }
            
            update() {
                this.x += this.speedX;
                this.y += this.speedY;
                
                if (this.x > canvas.width) this.x = 0;
                if (this.x < 0) this.x = canvas.width;
                if (this.y > canvas.height) this.y = 0;
                if (this.y < 0) this.y = canvas.height;
                
                // Mouse interaction
                const dx = mouseX - this.x;
                const dy = mouseY - this.y;
                const distance = Math.sqrt(dx * dx + dy * dy);
                if (distance < 100) {
                    const force = (100 - distance) / 100;
                    this.x -= dx * force * 0.02;
                    this.y -= dy * force * 0.02;
                }
            }
            
            draw() {
                ctx.fillStyle = `rgba(99, 102, 241, ${this.opacity})`;
                ctx.beginPath();
                ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
                ctx.fill();
            }
        }
        
        function initParticles() {
            particles = [];
            const particleCount = Math.min(window.innerWidth / 10, 100);
            for (let i = 0; i < particleCount; i++) {
                particles.push(new Particle());
            }
        }
        initParticles();
        
        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            
            particles.forEach(particle => {
                particle.update();
                particle.draw();
            });
            
            // Draw connections
            particles.forEach((a, i) => {
                particles.slice(i + 1).forEach(b => {
                    const dx = a.x - b.x;
                    const dy = a.y - b.y;
                    const distance = Math.sqrt(dx * dx + dy * dy);
                    
                    if (distance < 150) {
                        ctx.strokeStyle = `rgba(99, 102, 241, ${0.1 * (1 - distance / 150)})`;
                        ctx.lineWidth = 0.5;
                        ctx.beginPath();
                        ctx.moveTo(a.x, a.y);
                        ctx.lineTo(b.x, b.y);
                        ctx.stroke();
                    }
                });
            });
            
            requestAnimationFrame(animateParticles);
        }
        animateParticles();
        
        window.addEventListener('mousemove', (e) => {
            mouseX = e.clientX;
            mouseY = e.clientY;
        });
        
        // Custom Cursor
        const cursorDot = document.getElementById('cursor-dot');
        const cursorOutline = document.getElementById('cursor-outline');
        
        window.addEventListener('mousemove', (e) => {
            cursorDot.style.left = e.clientX + 'px';
            cursorDot.style.top = e.clientY + 'px';
            
            setTimeout(() => {
                cursorOutline.style.left = e.clientX - 16 + 'px';
                cursorOutline.style.top = e.clientY - 16 + 'px';
            }, 50);
        });
        
        document.querySelectorAll('a, button, .skill-badge, .card-3d').forEach(el => {
            el.addEventListener('mouseenter', () => {
                cursorOutline.style.transform = 'scale(1.5)';
                cursorOutline.style.borderColor = 'rgba(99, 102, 241, 0.6)';
            });
            el.addEventListener('mouseleave', () => {
                cursorOutline.style.transform = 'scale(1)';
                cursorOutline.style.borderColor = 'rgba(99, 102, 241, 0.3)';
            });
        });
        
        // Scroll Reveal
        const revealElements = document.querySelectorAll('.reveal');
        const revealObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('active');
                }
            });
        }, { threshold: 0.1 });
        
        revealElements.forEach(el => revealObserver.observe(el));
        
        // 3D Tilt Effect
        document.querySelectorAll('.tilt-container').forEach(container => {
            const element = container.querySelector('.tilt-element');
            
            container.addEventListener('mousemove', (e) => {
                const rect = container.getBoundingClientRect();
                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;
                const centerX = rect.width / 2;
                const centerY = rect.height / 2;
                const rotateX = (y - centerY) / 10;
                const rotateY = (centerX - x) / 10;
                
                element.style.transform = `perspective(1000px) rotateX(${rotateX}deg) rotateY(${rotateY}deg) scale(1.02)`;
            });
            
            container.addEventListener('mouseleave', () => {
                element.style.transform = 'perspective(1000px) rotateX(0) rotateY(0) scale(1)';
            });
        });
        
        // Counter Animation
        const counters = document.querySelectorAll('[data-count]');
        const counterObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const target = parseInt(entry.target.getAttribute('data-count'));
                    let current = 0;
                    const increment = target / 50;
                    const timer = setInterval(() => {
                        current += increment;
                        if (current >= target) {
                            entry.target.textContent = target;
                            clearInterval(timer);
                        } else {
                            entry.target.textContent = Math.floor(current);
                        }
                    }, 30);
                    counterObserver.unobserve(entry.target);
                }
            });
        }, { threshold: 0.5 });
        
        counters.forEach(counter => counterObserver.observe(counter));
        
        // Smooth Scroll
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });
        
        // Navbar Background on Scroll
        const nav = document.querySelector('nav');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                nav.classList.add('shadow-lg', 'shadow-primary/5');
            } else {
                nav.classList.remove('shadow-lg', 'shadow-primary/5');
            }
        });
    </script>
</body>
</html>'''

with open('/mnt/agents/output/index.html', 'w', encoding='utf-8') as f:
    f.write(html_content)
    
print("File saved successfully!")
print(f"File size: {len(html_content)} characters")
