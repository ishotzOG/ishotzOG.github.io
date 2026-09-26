<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DevPortfolio | Personal Website</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts: Inter for UI, Fira Code for technical accents -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Fira+Code:wght@400;500&display=swap" rel="stylesheet">
    
    <!-- Phosphor Icons -->
    <script src="https://unpkg.com/@phosphor-icons/web"></script>

    <!-- Configuration for Tailwind -->
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        mono: ['Fira Code', 'monospace'],
                    },
                    colors: {
                        dark: '#0a0a0a',
                        darker: '#050505',
                        card: '#141414',
                        accent: '#3b82f6', // blue-500
                        accentHover: '#2563eb', // blue-600
                    }
                }
            }
        }
    </script>

    <style>
        body {
            background-color: theme('colors.dark');
            color: #f3f4f6; /* gray-100 */
            overflow-x: hidden;
        }

        /* Subtle grid background for the hero section */
        .bg-grid {
            background-size: 40px 40px;
            background-image: linear-gradient(to right, rgba(255, 255, 255, 0.05) 1px, transparent 1px),
                              linear-gradient(to bottom, rgba(255, 255, 255, 0.05) 1px, transparent 1px);
            mask-image: linear-gradient(to bottom, black 40%, transparent 100%);
            -webkit-mask-image: linear-gradient(to bottom, black 40%, transparent 100%);
        }

        /* Scroll reveal animations */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease-out;
        }

        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Typing effect cursor */
        .cursor::after {
            content: '|';
            animation: blink 1s step-start infinite;
        }

        @keyframes blink {
            50% { opacity: 0; }
        }

        /* Gradient text utility */
        .text-gradient {
            background: linear-gradient(to right, #3b82f6, #8b5cf6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }
        
        /* Card hover effects */
        .project-card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px -10px rgba(59, 130, 246, 0.3);
        }
    </style>
</head>
<body class="antialiased selection:bg-accent selection:text-white relative">

    <nav class="fixed w-full z-50 top-0 transition-all duration-300 backdrop-blur-md bg-dark/80 border-b border-white/10" id="navbar">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-16">
                <!-- Logo -->
                <div class="flex-shrink-0 cursor-pointer">
                    <a href="#home" class="font-mono text-xl font-bold tracking-tighter text-white">
                        <span class="text-accent">&lt;</span>AlexDev<span class="text-accent">/&gt;</span>
                    </a>
                </div>
                
                <!-- Desktop Menu -->
                <div class="hidden md:block">
                    <div class="ml-10 flex items-baseline space-x-8">
                        <a href="#home" class="text-gray-300 hover:text-white transition-colors px-3 py-2 text-sm font-medium">Home</a>
                        <a href="#about" class="text-gray-300 hover:text-white transition-colors px-3 py-2 text-sm font-medium">About</a>
                        <a href="#projects" class="text-gray-300 hover:text-white transition-colors px-3 py-2 text-sm font-medium">Projects</a>
                        <a href="#contact" class="text-gray-300 hover:text-white transition-colors px-3 py-2 text-sm font-medium">Contact</a>
                    </div>
                </div>

                <!-- Mobile menu button -->
                <div class="md:hidden flex items-center">
                    <button type="button" id="mobile-menu-btn" class="text-gray-400 hover:text-white focus:outline-none">
                        <i class="ph ph-list text-2xl"></i>
                    </button>
                </div>
            </div>
        </div>

        <!-- Mobile Menu Panel -->
        <div class="md:hidden hidden bg-card border-b border-white/10" id="mobile-menu">
            <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
                <a href="#home" class="text-gray-300 hover:text-white block px-3 py-2 text-base font-medium">Home</a>
                <a href="#about" class="text-gray-300 hover:text-white block px-3 py-2 text-base font-medium">About</a>
                <a href="#projects" class="text-gray-300 hover:text-white block px-3 py-2 text-base font-medium">Projects</a>
                <a href="#contact" class="text-gray-300 hover:text-white block px-3 py-2 text-base font-medium">Contact</a>
            </div>
        </div>
    </nav>

    <section id="home" class="relative min-h-screen flex items-center justify-center pt-16 overflow-hidden">
        <!-- Background Grid -->
        <div class="absolute inset-0 bg-grid z-0 pointer-events-none"></div>
        
        <!-- Glowing orb behind text -->
        <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[500px] h-[500px] bg-accent/20 rounded-full blur-[120px] -z-10 pointer-events-none"></div>

        <div class="relative z-10 max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center reveal">
            <p class="font-mono text-accent mb-4">Hi, my name is</p>
            <h1 class="text-5xl md:text-7xl font-bold tracking-tight mb-4 text-white">
                Alex Developer.
            </h1>
            <h2 class="text-4xl md:text-6xl font-bold text-gray-400 mb-6">
                I build things for the <span id="typewriter" class="text-gradient cursor"></span>
            </h2>
            <p class="mt-4 text-lg text-gray-400 max-w-2xl mx-auto mb-10 leading-relaxed">
                I'm a computer science student and software developer specializing in building exceptional digital experiences. Currently, I'm focused on accessible, human-centered products.
            </p>
            <div class="flex flex-col sm:flex-row gap-4 justify-center">
                <a href="#projects" class="px-8 py-3 rounded-md bg-accent hover:bg-accentHover text-white font-medium transition-all duration-300 shadow-[0_0_20px_rgba(59,130,246,0.3)]">
                    Check out my work
                </a>
                <a href="#contact" class="px-8 py-3 rounded-md border border-white/20 hover:border-accent hover:text-accent transition-all duration-300 bg-white/5 backdrop-blur-sm">
                    Contact Me
                </a>
            </div>
        </div>
    </section>

    <section id="about" class="py-24 bg-darker">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="reveal">
                <h2 class="text-3xl font-bold mb-12 flex items-center">
                    <span class="font-mono text-accent text-xl mr-2">01.</span> About Me
                    <div class="ml-4 h-[1px] bg-white/10 flex-grow max-w-xs"></div>
                </h2>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-start">
                <div class="reveal text-gray-400 space-y-4 leading-relaxed">
                    <p>
                        Hello! My name is Alex and I enjoy creating things that live on the internet. My interest in web development started back in 2018 when I decided to try editing custom Tumblr themes — turns out hacking together HTML & CSS taught me a lot about architecture!
                    </p>
                    <p>
                        Fast-forward to today, and I'm currently a senior studying Computer Science. I've had the privilege of building software for a student-led organization, participating in multiple hackathons, and developing open-source tools.
                    </p>
                    <p>
                        Here are a few technologies I've been working with recently:
                    </p>
                    
                    <!-- Skills Grid -->
                    <ul class="grid grid-cols-2 gap-2 mt-4 font-mono text-sm text-gray-300">
                        <li class="flex items-center"><i class="ph-fill ph-caret-right text-accent mr-2"></i> JavaScript (ES6+)</li>
                        <li class="flex items-center"><i class="ph-fill ph-caret-right text-accent mr-2"></i> React & Next.js</li>
                        <li class="flex items-center"><i class="ph-fill ph-caret-right text-accent mr-2"></i> Node.js</li>
                        <li class="flex items-center"><i class="ph-fill ph-caret-right text-accent mr-2"></i> TypeScript</li>
                        <li class="flex items-center"><i class="ph-fill ph-caret-right text-accent mr-2"></i> Python</li>
                        <li class="flex items-center"><i class="ph-fill ph-caret-right text-accent mr-2"></i> Tailwind CSS</li>
                    </ul>
                </div>
                
                <!-- Profile Image Placeholder -->
                <div class="reveal relative group w-3/4 mx-auto md:w-full max-w-md">
                    <div class="absolute -inset-2 bg-gradient-to-r from-accent to-purple-600 rounded-lg blur opacity-25 group-hover:opacity-50 transition duration-500"></div>
                    <div class="relative rounded-lg overflow-hidden border border-white/10 bg-card aspect-square flex items-center justify-center">
                        <img src="https://placehold.co/600x600/141414/3b82f6?text=Developer+Image" alt="Profile" class="object-cover w-full h-full grayscale hover:grayscale-0 transition-all duration-500">
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="projects" class="py-24 bg-dark">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="reveal mb-12">
                <h2 class="text-3xl font-bold flex items-center">
                    <span class="font-mono text-accent text-xl mr-2">02.</span> Some Things I've Built
                    <div class="ml-4 h-[1px] bg-white/10 flex-grow max-w-xs"></div>
                </h2>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                
                <!-- Project 1 -->
                <div class="project-card reveal bg-card border border-white/5 rounded-xl overflow-hidden flex flex-col">
                    <div class="h-48 overflow-hidden relative group">
                        <img src="https://placehold.co/600x400/1e293b/ffffff?text=E-Commerce+Dashboard" alt="Project 1" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110">
                        <div class="absolute inset-0 bg-accent/20 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <a href="#" class="p-3 bg-dark/80 rounded-full text-white hover:text-accent transition"><i class="ph ph-link text-xl"></i></a>
                        </div>
                    </div>
                    <div class="p-6 flex-grow flex flex-col">
                        <div class="flex justify-between items-center mb-4">
                            <i class="ph ph-folder text-3xl text-accent"></i>
                            <div class="flex space-x-3 text-gray-400">
                                <a href="#" class="hover:text-accent transition"><i class="ph ph-github-logo text-xl"></i></a>
                                <a href="#" class="hover:text-accent transition"><i class="ph ph-arrow-square-out text-xl"></i></a>
                            </div>
                        </div>
                        <h3 class="text-xl font-bold mb-2 group-hover:text-accent transition-colors">Admin Dashboard</h3>
                        <p class="text-gray-400 text-sm mb-4 flex-grow">A comprehensive dashboard for e-commerce stores to track sales, manage inventory, and analyze user behavior with real-time charts.</p>
                        <ul class="flex flex-wrap gap-3 font-mono text-xs text-gray-500 mt-auto">
                            <li>React</li>
                            <li>Chart.js</li>
                            <li>Tailwind</li>
                        </ul>
                    </div>
                </div>

                <!-- Project 2 -->
                <div class="project-card reveal bg-card border border-white/5 rounded-xl overflow-hidden flex flex-col" style="transition-delay: 100ms;">
                    <div class="h-48 overflow-hidden relative group">
                        <img src="https://placehold.co/600x400/1e293b/ffffff?text=AI+Chat+Interface" alt="Project 2" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110">
                        <div class="absolute inset-0 bg-accent/20 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <a href="#" class="p-3 bg-dark/80 rounded-full text-white hover:text-accent transition"><i class="ph ph-link text-xl"></i></a>
                        </div>
                    </div>
                    <div class="p-6 flex-grow flex flex-col">
                        <div class="flex justify-between items-center mb-4">
                            <i class="ph ph-folder text-3xl text-accent"></i>
                            <div class="flex space-x-3 text-gray-400">
                                <a href="#" class="hover:text-accent transition"><i class="ph ph-github-logo text-xl"></i></a>
                            </div>
                        </div>
                        <h3 class="text-xl font-bold mb-2">AI Chat Interface</h3>
                        <p class="text-gray-400 text-sm mb-4 flex-grow">A responsive chat interface integrating with OpenAI's API. Features include conversation history, markdown support, and dark mode.</p>
                        <ul class="flex flex-wrap gap-3 font-mono text-xs text-gray-500 mt-auto">
                            <li>Next.js</li>
                            <li>OpenAI API</li>
                            <li>Framer Motion</li>
                        </ul>
                    </div>
                </div>

                <!-- Project 3 -->
                <div class="project-card reveal bg-card border border-white/5 rounded-xl overflow-hidden flex flex-col" style="transition-delay: 200ms;">
                    <div class="h-48 overflow-hidden relative group">
                        <img src="https://placehold.co/600x400/1e293b/ffffff?text=Algorithm+Visualizer" alt="Project 3" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110">
                        <div class="absolute inset-0 bg-accent/20 opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-center justify-center">
                            <a href="#" class="p-3 bg-dark/80 rounded-full text-white hover:text-accent transition"><i class="ph ph-link text-xl"></i></a>
                        </div>
                    </div>
                    <div class="p-6 flex-grow flex flex-col">
                        <div class="flex justify-between items-center mb-4">
                            <i class="ph ph-folder text-3xl text-accent"></i>
                            <div class="flex space-x-3 text-gray-400">
                                <a href="#" class="hover:text-accent transition"><i class="ph ph-github-logo text-xl"></i></a>
                                <a href="#" class="hover:text-accent transition"><i class="ph ph-arrow-square-out text-xl"></i></a>
                            </div>
                        </div>
                        <h3 class="text-xl font-bold mb-2">Algorithm Visualizer</h3>
                        <p class="text-gray-400 text-sm mb-4 flex-grow">An interactive educational tool that visualizes sorting and pathfinding algorithms in real-time, helping students understand computer science fundamentals.</p>
                        <ul class="flex flex-wrap gap-3 font-mono text-xs text-gray-500 mt-auto">
                            <li>Vanilla JS</li>
                            <li>HTML Canvas</li>
                            <li>CSS Grid</li>
                        </ul>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <section id="contact" class="py-24 bg-darker relative overflow-hidden">
        <!-- Decorative blur -->
        <div class="absolute bottom-0 right-0 w-[400px] h-[400px] bg-accent/10 rounded-full blur-[100px] pointer-events-none"></div>

        <div class="max-w-2xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <div class="reveal">
                <p class="font-mono text-accent mb-2">03. What's Next?</p>
                <h2 class="text-4xl font-bold mb-6">Get In Touch</h2>
                <p class="text-gray-400 mb-10 leading-relaxed">
                    Although I'm not currently looking for any new opportunities, my inbox is always open. Whether you have a question or just want to say hi, I'll try my best to get back to you!
                </p>
            </div>

            <form id="contact-form" class="reveal space-y-6 text-left">
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-6">
                    <div>
                        <label for="name" class="block text-sm font-medium text-gray-400 mb-2 font-mono">Name</label>
                        <input type="text" id="name" required class="w-full bg-card border border-white/10 rounded-md px-4 py-3 text-white focus:outline-none focus:border-accent focus:ring-1 focus:ring-accent transition-colors">
                    </div>
                    <div>
                        <label for="email" class="block text-sm font-medium text-gray-400 mb-2 font-mono">Email</label>
                        <input type="email" id="email" required class="w-full bg-card border border-white/10 rounded-md px-4 py-3 text-white focus:outline-none focus:border-accent focus:ring-1 focus:ring-accent transition-colors">
                    </div>
                </div>
                <div>
                    <label for="message" class="block text-sm font-medium text-gray-400 mb-2 font-mono">Message</label>
                    <textarea id="message" rows="5" required class="w-full bg-card border border-white/10 rounded-md px-4 py-3 text-white focus:outline-none focus:border-accent focus:ring-1 focus:ring-accent transition-colors resize-none"></textarea>
                </div>
                <div class="text-center pt-4">
                    <button type="submit" class="px-8 py-3 rounded-md bg-transparent border border-accent text-accent hover:bg-accent/10 transition-all duration-300 font-mono">
                        Send Message
                    </button>
                </div>
                <!-- Form Status Message -->
                <p id="form-status" class="text-center mt-4 hidden"></p>
            </form>
        </div>
    </section>

    <footer class="bg-dark py-8 border-t border-white/5 text-center">
        <div class="flex justify-center space-x-6 mb-6">
            <a href="#" class="text-gray-400 hover:text-accent transition transform hover:-translate-y-1"><i class="ph ph-github-logo text-2xl"></i></a>
            <a href="#" class="text-gray-400 hover:text-accent transition transform hover:-translate-y-1"><i class="ph ph-linkedin-logo text-2xl"></i></a>
            <a href="#" class="text-gray-400 hover:text-accent transition transform hover:-translate-y-1"><i class="ph ph-twitter-logo text-2xl"></i></a>
            <a href="#" class="text-gray-400 hover:text-accent transition transform hover:-translate-y-1"><i class="ph ph-envelope-simple text-2xl"></i></a>
        </div>
        <p class="font-mono text-sm text-gray-500">
            Designed & Built by Alex Developer <br>
            <span class="text-xs opacity-50 mt-2 block">&copy; 2026 All rights reserved.</span>
        </p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            
            // 1. Mobile Menu Toggle
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

            // 2. Navbar Scroll Effect (Blur & Shadow)
            const navbar = document.getElementById('navbar');
            window.addEventListener('scroll', () => {
                if (window.scrollY > 50) {
                    navbar.classList.add('shadow-lg');
                    navbar.style.backgroundColor = 'rgba(10, 10, 10, 0.9)';
                } else {
                    navbar.classList.remove('shadow-lg');
                    navbar.style.backgroundColor = 'rgba(10, 10, 10, 0.8)';
                }
            });

            // 3. Scroll Reveal Animation using Intersection Observer
            const revealElements = document.querySelectorAll('.reveal');
            
            const revealOptions = {
                threshold: 0.15,
                rootMargin: "0px 0px -50px 0px"
            };

            const revealObserver = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('active');
                        // Optional: stop observing once revealed
                        // observer.unobserve(entry.target);
                    }
                });
            }, revealOptions);

            revealElements.forEach(el => {
                revealObserver.observe(el);
            });

            // 4. Typewriter Effect for Hero Section
            const words = ["web.", "future.", "cloud.", "world."];
            let i = 0;
            let timer;
            const typewriterEl = document.getElementById('typewriter');

            function typingEffect() {
                let word = words[i].split("");
                var loopTyping = function() {
                    if (word.length > 0) {
                        typewriterEl.innerHTML += word.shift();
                    } else {
                        setTimeout(deletingEffect, 2000); // Wait before deleting
                        return false;
                    }
                    timer = setTimeout(loopTyping, 150);
                };
                loopTyping();
            }

            function deletingEffect() {
                let word = words[i].split("");
                var loopDeleting = function() {
                    if (word.length > 0) {
                        word.pop();
                        typewriterEl.innerHTML = word.join("");
                    } else {
                        if (words.length > (i + 1)) {
                            i++;
                        } else {
                            i = 0; // Loop back to start
                        }
                        typingEffect();
                        return false;
                    }
                    timer = setTimeout(loopDeleting, 100);
                };
                loopDeleting();
            }

            // Start typing effect slightly after load
            setTimeout(typingEffect, 1000);

            // 5. Handle Contact Form Submission
            const form = document.getElementById('contact-form');
            const statusMsg = document.getElementById('form-status');

            form.addEventListener('submit', (e) => {
                e.preventDefault(); // Prevent actual form submission for demo
                
                // Show loading state
                const btn = form.querySelector('button[type="submit"]');
                const originalText = btn.innerText;
                btn.innerText = 'Sending...';
                btn.disabled = true;

                // Simulate API call
                setTimeout(() => {
                    btn.innerText = originalText;
                    btn.disabled = false;
                    
                    form.reset(); // Clear form
                    
                    // Show success message
                    statusMsg.textContent = "Thanks! Your message has been sent.";
                    statusMsg.classList.remove('hidden', 'text-red-500');
                    statusMsg.classList.add('text-green-400');
                    
                    setTimeout(() => {
                        statusMsg.classList.add('hidden');
                    }, 5000);
                }, 1500);
            });
        });
    </script>
</body>
</html>
