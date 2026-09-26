<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Developer Portfolio | Math & Physics</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts: Inter for UI, Roboto Mono for code/technical accents -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Roboto+Mono:wght@400;500;700&display=swap" rel="stylesheet">
    
    <!-- Phosphor Icons for minimalist iconography -->
    <script src="https://unpkg.com/@phosphor-icons/web"></script>

    <!-- Tailwind Configuration (GitHub Dark Theme Aesthetic) -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        mono: ['Roboto Mono', 'monospace'],
                    },
                    colors: {
                        gh_bg: '#0d1117',
                        gh_card: '#161b22',
                        gh_border: '#30363d',
                        gh_text: '#c9d1d9',
                        gh_muted: '#8b949e',
                        gh_blue: '#58a6ff',
                        gh_green: '#238636',
                        gh_green_hover: '#2ea043',
                    }
                }
            }
        }
    </script>

    <style>
        body {
            background-color: #0d1117;
            color: #c9d1d9;
            overflow-x: hidden;
        }

        /* Subtle grid background for technical feel */
        .tech-grid {
            background-size: 30px 30px;
            background-image: 
                linear-gradient(to right, rgba(48, 54, 61, 0.2) 1px, transparent 1px),
                linear-gradient(to bottom, rgba(48, 54, 61, 0.2) 1px, transparent 1px);
            mask-image: linear-gradient(to bottom, black 20%, transparent 100%);
            -webkit-mask-image: linear-gradient(to bottom, black 20%, transparent 100%);
        }

        /* Scroll reveal animations */
        .reveal {
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.6s cubic-bezier(0.16, 1, 0.3, 1);
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Blinking cursor for typing effect */
        .cursor::after {
            content: '_';
            animation: blink 1s step-start infinite;
            color: #58a6ff;
        }

        @keyframes blink {
            50% { opacity: 0; }
        }

        /* Card hover effects mimicking GitHub repo cards */
        .repo-card {
            transition: border-color 0.2s ease, transform 0.2s ease;
        }
        .repo-card:hover {
            border-color: #8b949e;
            transform: translateY(-2px);
        }
        
        /* Language color dots */
        .lang-dot.python { background-color: #3572A5; }
        .lang-dot.c { background-color: #555555; }
        .lang-dot.shell { background-color: #89e051; }
        .lang-dot.prompt { background-color: #a074c4; }
    </style>
</head>
<body class="antialiased selection:bg-gh_blue selection:text-white">

    <nav class="fixed w-full z-50 top-0 border-b border-gh_border bg-gh_bg/90 backdrop-blur-sm">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <div class="flex items-center gap-3 cursor-pointer">
                    <i class="ph-fill ph-github-logo text-3xl text-gh_text"></i>
                    <a href="#home" class="font-mono text-lg font-bold tracking-tight text-white">
                        student<span class="text-gh_muted">@</span>portfolio<span class="text-gh_blue">:~</span>$
                    </a>
                </div>
                
                <div class="hidden md:block">
                    <div class="ml-10 flex items-baseline space-x-6">
                        <a href="#about" class="text-gh_text hover:text-gh_blue transition-colors px-3 py-2 text-sm font-medium">~/about</a>
                        <a href="#skills" class="text-gh_text hover:text-gh_blue transition-colors px-3 py-2 text-sm font-medium">~/skills</a>
                        <a href="#projects" class="text-gh_text hover:text-gh_blue transition-colors px-3 py-2 text-sm font-medium">~/projects</a>
                        <a href="#contact" class="text-gh_text hover:text-gh_blue transition-colors px-3 py-2 text-sm font-medium">~/contact</a>
                    </div>
                </div>

                <!-- Mobile menu button -->
                <div class="md:hidden flex items-center">
                    <button type="button" id="mobile-menu-btn" class="text-gh_muted hover:text-white focus:outline-none">
                        <i class="ph ph-list text-2xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Menu -->
        <div class="md:hidden hidden bg-gh_card border-b border-gh_border" id="mobile-menu">
            <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3 font-mono text-sm">
                <a href="#about" class="text-gh_text hover:text-gh_blue block px-3 py-2">cd /about</a>
                <a href="#skills" class="text-gh_text hover:text-gh_blue block px-3 py-2">cd /skills</a>
                <a href="#projects" class="text-gh_text hover:text-gh_blue block px-3 py-2">cd /projects</a>
                <a href="#contact" class="text-gh_text hover:text-gh_blue block px-3 py-2">cd /contact</a>
            </div>
        </div>
    </nav>

    <section id="home" class="relative min-h-screen flex items-center pt-16 overflow-hidden">
        <div class="absolute inset-0 tech-grid z-0 pointer-events-none"></div>
        
        <div class="relative z-10 max-w-5xl mx-auto px-4 sm:px-6 lg:px-8 w-full reveal">
            <div class="flex items-center gap-2 mb-4">
                <span class="inline-block w-3 h-3 rounded-full bg-gh_green"></span>
                <span class="font-mono text-gh_muted text-sm">Status: Available for collaboration</span>
            </div>
            
            <h1 class="text-5xl md:text-7xl font-bold tracking-tight mb-4 text-white">
                Bridging the gap between <br class="hidden md:block" />
                <span class="text-gh_blue">theory</span> & <span class="text-gh_blue">execution.</span>
            </h1>
            
            <h2 class="text-xl md:text-2xl font-mono text-gh_text mb-6 mt-6 h-8">
                > I am a <span id="typewriter" class="cursor font-bold text-white"></span>
            </h2>
            
            <p class="mt-4 text-base md:text-lg text-gh_muted max-w-2xl mb-10 leading-relaxed font-sans">
                As a college student studying Mathematics and Physics, I thrive on complex problem-solving. 
                I apply analytical frameworks to software development, specializing in Python automation, 
                low-level Android Modding, and AI Prompt Engineering.
            </p>
            
            <div class="flex flex-col sm:flex-row gap-4">
                <a href="#projects" class="inline-flex items-center justify-center gap-2 px-6 py-3 rounded-md bg-gh_green hover:bg-gh_green_hover text-white font-medium transition-colors border border-transparent">
                    <i class="ph ph-git-branch text-lg"></i> View Projects
                </a>
                <a href="https://github.com" target="_blank" class="inline-flex items-center justify-center gap-2 px-6 py-3 rounded-md bg-gh_card border border-gh_border hover:border-gh_muted text-gh_text transition-all">
                    <i class="ph ph-github-logo text-lg"></i> GitHub Profile
                </a>
            </div>
        </div>
    </section>

    <section id="skills" class="py-24 border-t border-gh_border bg-gh_bg relative">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="reveal mb-12">
                <h2 class="text-2xl font-bold text-white flex items-center font-mono">
                    <i class="ph ph-terminal-window mr-3 text-gh_muted"></i> ~/skills_and_about.md
                </h2>
                <div class="mt-2 h-[1px] bg-gh_border w-full"></div>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-12 gap-12 items-start">
                <div class="md:col-span-7 reveal space-y-4 text-gh_text leading-relaxed">
                    <p>
                        My academic background in <strong class="text-white">Mathematics and Physics</strong> provides a strong foundation for abstract thinking and algorithmic logic. I don't just write code; I model systems and solve problems from first principles.
                    </p>
                    <p>
                        Beyond academia, my technical passion lies in pushing the limits of hardware and software. I dive deep into <strong class="text-gh_blue">Android Modding</strong>, manipulating kernels to squeeze out performance, and use <strong class="text-gh_blue">Python</strong> to automate repetitive workflows into seamless pipelines.
                    </p>
                    <p>
                        Recently, I've been exploring the intersection of art and computation through advanced <strong class="text-gh_blue">AI Prompt Engineering</strong>, treating natural language as a compiled language for generating cinematic visuals.
                    </p>
                </div>
                
                <div class="md:col-span-5 reveal bg-gh_card border border-gh_border rounded-lg p-6">
                    <h3 class="text-sm font-bold text-gh_muted uppercase tracking-wider mb-4 font-mono">Core Competencies</h3>
                    
                    <div class="flex flex-wrap gap-2">
                        <span class="px-3 py-1 bg-gh_bg border border-gh_border rounded-full text-sm text-gh_blue font-mono">Python</span>
                        <span class="px-3 py-1 bg-gh_bg border border-gh_border rounded-full text-sm text-gh_blue font-mono">C / C++</span>
                        <span class="px-3 py-1 bg-gh_bg border border-gh_border rounded-full text-sm text-gh_blue font-mono">Bash Scripting</span>
                        <span class="px-3 py-1 bg-gh_bg border border-gh_border rounded-full text-sm text-white">Android Kernel Dev</span>
                        <span class="px-3 py-1 bg-gh_bg border border-gh_border rounded-full text-sm text-white">KernelSU / Zygisk</span>
                        <span class="px-3 py-1 bg-gh_bg border border-gh_border rounded-full text-sm text-white">Linux Administration</span>
                        <span class="px-3 py-1 bg-gh_bg border border-gh_border rounded-full text-sm text-white">Pillow / ReportLab</span>
                        <span class="px-3 py-1 bg-gh_bg border border-gh_border rounded-full text-sm text-white">AI Prompt Engineering</span>
                        <span class="px-3 py-1 bg-gh_bg border border-gh_border rounded-full text-sm text-gh_muted">Mathematics</span>
                        <span class="px-3 py-1 bg-gh_bg border border-gh_border rounded-full text-sm text-gh_muted">Physics</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="projects" class="py-24 border-t border-gh_border bg-[#0d1117]">
        <div class="max-w-5xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="reveal mb-12">
                <div class="flex justify-between items-end">
                    <h2 class="text-2xl font-bold text-white flex items-center font-mono">
                        <i class="ph ph-books mr-3 text-gh_muted"></i> ~/repositories
                    </h2>
                </div>
                <div class="mt-2 h-[1px] bg-gh_border w-full"></div>
            </div>

            <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
                
                <!-- Project 1: Android Kernel -->
                <div class="repo-card reveal bg-gh_card border border-gh_border rounded-lg p-6 flex flex-col h-full lg:col-span-2">
                    <div class="flex items-start justify-between mb-2">
                        <div class="flex items-center gap-2">
                            <i class="ph ph-device-mobile text-gh_muted text-xl"></i>
                            <a href="#" class="text-gh_blue font-semibold text-lg hover:underline font-mono">cmf-phone1-kernel-opt</a>
                        </div>
                        <span class="px-2 py-0.5 border border-gh_border rounded-full text-xs text-gh_muted font-mono">Public</span>
                    </div>
                    <p class="text-gh_text text-sm mb-4 flex-grow">
                        A highly optimized, custom Android kernel specifically tailored for the CMF Phone 1. Built from source to improve battery life and thermal throttling parameters. Fully integrates <strong>KernelSU</strong> and <strong>Zygisk</strong> to provide systemless root access and advanced low-level module support without tripping hardware attestations.
                    </p>
                    <div class="flex items-center gap-4 text-xs text-gh_muted font-mono mt-auto pt-4">
                        <span class="flex items-center gap-1.5"><span class="w-3 h-3 rounded-full lang-dot c"></span> C</span>
                        <span class="flex items-center gap-1.5"><span class="w-3 h-3 rounded-full lang-dot shell"></span> Makefile</span>
                        <a href="#" class="hover:text-gh_blue flex items-center gap-1"><i class="ph-fill ph-star"></i> 42</a>
                        <a href="#" class="hover:text-gh_blue flex items-center gap-1"><i class="ph-fill ph-git-fork"></i> 12</a>
                    </div>
                </div>

                <!-- Project 2: Python Automation -->
                <div class="repo-card reveal bg-gh_card border border-gh_border rounded-lg p-6 flex flex-col h-full" style="transition-delay: 100ms;">
                    <div class="flex items-start justify-between mb-2">
                        <div class="flex items-center gap-2">
                            <i class="ph ph-images text-gh_muted text-xl"></i>
                            <a href="#" class="text-gh_blue font-semibold text-lg hover:underline font-mono">py-image-to-pdf</a>
                        </div>
                    </div>
                    <p class="text-gh_text text-sm mb-4 flex-grow">
                        An automated pipeline built for bulk image processing. Utilizes <strong>Pillow (PIL)</strong> for resizing, color correction, and metadata stripping, and <strong>ReportLab</strong> to stitch processed images into lightweight, print-ready PDF documents. Reduces manual processing time by over 90%.
                    </p>
                    <div class="flex items-center gap-4 text-xs text-gh_muted font-mono mt-auto pt-4">
                        <span class="flex items-center gap-1.5"><span class="w-3 h-3 rounded-full lang-dot python"></span> Python</span>
                        <a href="#" class="hover:text-gh_blue flex items-center gap-1"><i class="ph-fill ph-star"></i> 18</a>
                    </div>
                </div>

                <!-- Project 3: AI Prompt Engineering -->
                <div class="repo-card reveal bg-gh_card border border-gh_border rounded-lg p-6 flex flex-col h-full" style="transition-delay: 200ms;">
                    <div class="flex items-start justify-between mb-2">
                        <div class="flex items-center gap-2">
                            <i class="ph ph-aperture text-gh_muted text-xl"></i>
                            <a href="#" class="text-gh_blue font-semibold text-lg hover:underline font-mono">cinematic-ai-prompts</a>
                        </div>
                    </div>
                    <p class="text-gh_text text-sm mb-4 flex-grow">
                        A curated repository of advanced, structured prompts for Midjourney and Stable Diffusion. Focuses on strict parameter control, cinematic visual styling, specific focal lengths, and complex lighting setups to achieve photorealistic and artistically coherent AI image generation.
                    </p>
                    <div class="flex items-center gap-4 text-xs text-gh_muted font-mono mt-auto pt-4">
                        <span class="flex items-center gap-1.5"><span class="w-3 h-3 rounded-full lang-dot prompt"></span> Markdown</span>
                        <a href="#" class="hover:text-gh_blue flex items-center gap-1"><i class="ph-fill ph-star"></i> 89</a>
                    </div>
                </div>

            </div>
            
            <!-- GitHub Contribution Graph Mockup -->
            <div class="mt-12 reveal bg-gh_card border border-gh_border rounded-lg p-6 text-center">
                <h3 class="text-sm text-gh_text mb-4 text-left font-mono text-gh_muted">1,248 contributions in the last year</h3>
                <!-- Simple visual mockup of GH graph using inline flex -->
                <div class="flex justify-center gap-1 overflow-hidden opacity-80">
                    <script>
                        // Generate mock contribution graph squares
                        for(let col=0; col<40; col++) {
                            document.write('<div class="flex flex-col gap-1 hidden sm:flex">');
                            for(let row=0; row<7; row++) {
                                // Randomize colors based on github greens
                                const colors = ['#161b22', '#161b22', '#161b22', '#0e4429', '#006d32', '#26a641', '#39d353'];
                                const color = colors[Math.floor(Math.random() * colors.length)];
                                document.write(`<div class="w-3 h-3 rounded-sm" style="background-color: ${color}"></div>`);
                            }
                            document.write('</div>');
                        }
                    </script>
                </div>
            </div>

        </div>
    </section>

    <section id="contact" class="py-24 border-t border-gh_border bg-gh_bg">
        <div class="max-w-3xl mx-auto px-4 sm:px-6 lg:px-8 text-center reveal">
            <i class="ph ph-paper-plane-tilt text-4xl text-gh_muted mb-4 block"></i>
            <h2 class="text-3xl font-bold mb-6 text-white">Let's Connect</h2>
            <p class="text-gh_text mb-10 leading-relaxed font-sans max-w-xl mx-auto">
                Whether you want to discuss advanced mathematics, collaborate on an open-source Android kernel, or just talk tech, my inbox is open.
            </p>
            
            <div class="flex flex-col sm:flex-row justify-center gap-4">
                <a href="mailto:student@example.com" class="inline-flex items-center justify-center gap-2 px-6 py-3 rounded-md bg-gh_card border border-gh_border hover:border-gh_blue text-white transition-all font-mono text-sm">
                    <i class="ph ph-envelope-simple text-lg text-gh_blue"></i> Send Email
                </a>
                <a href="https://github.com" target="_blank" class="inline-flex items-center justify-center gap-2 px-6 py-3 rounded-md bg-gh_card border border-gh_border hover:border-gh_muted text-white transition-all font-mono text-sm">
                    <i class="ph ph-github-logo text-lg text-gh_text"></i> github.com/username
                </a>
            </div>
        </div>
    </section>

    <footer class="bg-[#010409] py-8 border-t border-gh_border text-center">
        <div class="max-w-5xl mx-auto px-4 flex flex-col md:flex-row justify-between items-center gap-4">
            <div class="flex items-center gap-2 text-gh_muted text-sm font-mono">
                <i class="ph ph-code"></i> Built for GitHub Pages
            </div>
            <div class="text-gh_muted text-sm font-mono">
                &copy; 2026 Developer Portfolio. All rights reserved.
            </div>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            
            // Mobile Menu Toggle
            const btn = document.getElementById('mobile-menu-btn');
            const menu = document.getElementById('mobile-menu');

            btn.addEventListener('click', () => {
                menu.classList.toggle('hidden');
            });

            // Close mobile menu on link click
            document.querySelectorAll('#mobile-menu a').forEach(link => {
                link.addEventListener('click', () => {
                    menu.classList.add('hidden');
                });
            });

            // Intersection Observer for Scroll Animations
            const revealElements = document.querySelectorAll('.reveal');
            
            const revealObserver = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('active');
                    }
                });
            }, {
                threshold: 0.1,
                rootMargin: "0px 0px -30px 0px"
            });

            revealElements.forEach(el => {
                revealObserver.observe(el);
            });

            // Terminal Typewriter Effect for Hero
            const roles = ["Math & Physics Student.", "Python Developer.", "Android Kernel Modder.", "Prompt Engineer."];
            let roleIndex = 0;
            let charIndex = 0;
            let isDeleting = false;
            const typewriterEl = document.getElementById('typewriter');
            
            function type() {
                const currentRole = roles[roleIndex];
                
                if (isDeleting) {
                    typewriterEl.textContent = currentRole.substring(0, charIndex - 1);
                    charIndex--;
                } else {
                    typewriterEl.textContent = currentRole.substring(0, charIndex + 1);
                    charIndex++;
                }

                let typingSpeed = isDeleting ? 50 : 100;

                if (!isDeleting && charIndex === currentRole.length) {
                    typingSpeed = 2000; // Pause at end of word
                    isDeleting = true;
                } else if (isDeleting && charIndex === 0) {
                    isDeleting = false;
                    roleIndex = (roleIndex + 1) % roles.length;
                    typingSpeed = 500; // Pause before typing next word
                }

                setTimeout(type, typingSpeed);
            }

            // Start typing slightly after load
            setTimeout(type, 1000);
        });
    </script>
</body>
</html>
