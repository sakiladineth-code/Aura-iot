# Aura-iot
Iot
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AURA IoT Corporation | Global Tech</title>
    
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700;900&family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* --- 1. CORE VARIABLES & RESET --- */
        :root {
            --primary: #00f2ff; /* Neon Cyan */
            --secondary: #0066ff; /* Deep Blue */
            --gold: #ffc400;    /* Luxury Gold */
            --dark: #050505;    /* Pitch Black */
            --dark-gray: #111111;
            --text-gray: #a0a0a0;
            --border: 1px solid rgba(255, 255, 255, 0.1);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        html { scroll-behavior: smooth; }

        body {
            background-color: var(--dark);
            color: #fff;
            font-family: 'Roboto', sans-serif;
            font-size: 15px;
            line-height: 1.6;
            overflow-x: hidden;
        }

        h1, h2, h3, h4, .brand-font { font-family: 'Orbitron', sans-serif; letter-spacing: 1px; }
        
        .container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }
        
        /* Utility Classes */
        .text-center { text-align: center; }
        .text-primary { color: var(--primary); }
        .text-gold { color: var(--gold); }
        .mb-20 { margin-bottom: 20px; }
        .mb-50 { margin-bottom: 50px; }

        /* --- 2. LOADER --- */
        #loader {
            position: fixed; width: 100%; height: 100%; background: #000;
            z-index: 9999; display: flex; justify-content: center; align-items: center; flex-direction: column; transition: 0.5s;
        }
        .loader-text { font-size: 2rem; color: var(--primary); font-weight: 900; animation: pulse 1s infinite; }
        @keyframes pulse { 0% { opacity: 0.5; } 50% { opacity: 1; } 100% { opacity: 0.5; } }

        /* --- 3. NAVBAR --- */
        nav {
            position: fixed; top: 0; width: 100%; background: rgba(5, 5, 5, 0.95);
            border-bottom: var(--border); z-index: 1000; padding: 15px 0;
            backdrop-filter: blur(10px);
        }
        .nav-content { display: flex; justify-content: space-between; align-items: center; }
        .logo { font-size: 20px; font-weight: 900; color: #fff; }
        .logo span { color: var(--primary); }
        
        .btn-bill-nav {
            background: var(--gold); color: #000; padding: 8px 15px; border-radius: 4px; 
            font-weight: bold; text-decoration: none; font-size: 12px;
        }

        /* --- 4. HERO SECTION --- */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0,0,0,0.6), #050505), url('https://images.unsplash.com/photo-1550751827-4bd374c3f58b?q=80&w=2070&auto=format&fit=crop');
            background-size: cover; background-position: center;
            display: flex; align-items: center; justify-content: center; text-align: center;
            padding-top: 60px;
        }
        .hero h1 { font-size: 2.8rem; margin-bottom: 15px; line-height: 1.2; }
        .hero p { font-size: 1.1rem; color: #ccc; max-width: 600px; margin: 0 auto 30px; }
        .btn-hero { 
            padding: 15px 40px; background: var(--primary); color: #000; font-weight: bold; 
            border-radius: 50px; text-decoration: none; display: inline-block; transition: 0.3s;
        }
        .scroll-down { position: absolute; bottom: 30px; animation: bounce 2s infinite; color: var(--text-gray); }
        @keyframes bounce { 0%, 20%, 50%, 80%, 100% {transform: translateY(0);} 40% {transform: translateY(-10px);} 60% {transform: translateY(-5px);} }

        /* --- 5. PARTNERS --- */
        .partners { background: var(--dark-gray); padding: 20px 0; text-align: center; border-bottom: var(--border); }
        .partners span { font-size: 12px; color: #555; letter-spacing: 2px; text-transform: uppercase; }

        /* --- 6. VISION & MISSION --- */
        .section { padding: 80px 0; border-bottom: var(--border); }
        .vm-grid { display: grid; grid-template-columns: 1fr; gap: 20px; } /* Stacked on mobile */
        
        .vm-card {
            background: #0a0a0a; padding: 30px; border-left: 5px solid var(--primary); border-radius: 5px;
        }
        .vm-card.mission { border-left-color: var(--gold); }
        
        .vm-card h3 { font-size: 1.5rem; margin-bottom: 10px; color: #fff; }
        .vm-card p { color: #aaa; font-size: 0.95rem; }

        /* --- 7. ABOUT DETAILED --- */
        .about-text p { margin-bottom: 20px; color: var(--text-gray); }

        /* --- 8. STATS --- */
        .stats { background: #000; padding: 60px 0; text-align: center; }
        .stat-item h3 { font-size: 3rem; color: var(--primary); }
        .stat-item p { font-size: 0.9rem; color: #555; text-transform: uppercase; }
        .stats-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 30px; }

        /* --- 9. WHY CHOOSE US --- */
        .features-grid { display: grid; grid-template-columns: 1fr; gap: 20px; }
        .feature-box { background: #111; padding: 30px; border-radius: 10px; text-align: center; }
        .feature-box i { font-size: 3rem; color: var(--secondary); margin-bottom: 20px; }
        .feature-box h4 { margin-bottom: 10px; font-size: 1.2rem; }

        /* --- 10. 12 SERVICES --- */
        .services-grid { 
            display: grid; grid-template-columns: repeat(2, 1fr); gap: 15px; /* 2 Cols on mobile */
        }
        .service-card { 
            background: #0f0f0f; padding: 20px 10px; text-align: center; border: 1px solid #222; border-radius: 8px; 
        }
        .service-card i { font-size: 1.8rem; color: var(--primary); margin-bottom: 10px; }
        .service-card h4 { font-size: 0.9rem; margin-bottom: 5px; }
        .service-card p { font-size: 0.75rem; color: #666; display: none; } /* Hide text on mobile to save space/clean look */
        @media(min-width: 768px) { .service-card p { display: block; } }

        /* --- 11. AURA BILL (GOLD) --- */
        .aura-bill {
            background: linear-gradient(135deg, #221a00, #000); padding: 100px 0; text-align: center;
            border-top: 2px solid var(--gold); border-bottom: 2px solid var(--gold);
        }
        .aura-bill h2 { color: var(--gold); font-size: 3rem; margin-bottom: 20px; }
        .btn-gold-big {
            background: var(--gold); color: #000; padding: 15px 50px; border-radius: 50px; font-weight: bold; text-decoration: none; font-size: 1.2rem;
            display: inline-flex; align-items: center; gap: 10px;
        }

        /* --- 12. PRODUCT G1 --- */
        .product-section { background: #080808; text-align: center; }
        .g1-specs { display: grid; grid-template-columns: repeat(2, 1fr); gap: 15px; margin-top: 30px; }
        .spec { background: #111; padding: 15px; border-radius: 5px; }
        .spec h5 { color: var(--primary); }

        /* --- 13. WORKFLOW (PROCESS) --- */
        .process-step { display: flex; gap: 20px; margin-bottom: 30px; align-items: flex-start; }
        .step-num { 
            background: var(--dark-gray); border: 2px solid var(--primary); color: var(--primary); 
            width: 50px; height: 50px; display: flex; align-items: center; justify-content: center; 
            border-radius: 50%; font-weight: bold; flex-shrink: 0;
        }

        /* --- 14. FAQ --- */
        .faq-item { background: #111; margin-bottom: 10px; padding: 15px; border-radius: 5px; }
        .faq-item h4 { font-size: 1rem; color: #fff; margin-bottom: 5px; }
        .faq-item p { font-size: 0.9rem; color: #777; }

        /* --- 15. CONTACT --- */
        .form-group input, .form-group textarea {
            width: 100%; padding: 15px; margin-bottom: 15px; background: #111; border: 1px solid #333; color: #fff;
        }
        .btn-submit { width: 100%; padding: 15px; background: var(--secondary); color: #fff; border: none; font-weight: bold; cursor: pointer; }

        /* --- 16. FOOTER --- */
        footer { background: #000; padding: 50px 0 20px; font-size: 0.9rem; color: #555; text-align: center; }
        .footer-links { display: flex; justify-content: center; gap: 20px; margin-bottom: 20px; flex-wrap: wrap; }
        .footer-links a { color: #888; text-decoration: none; }

        /* TABLET/DESKTOP TWEAKS */
        @media (min-width: 768px) {
            .hero h1 { font-size: 4rem; }
            .vm-grid { grid-template-columns: 1fr 1fr; }
            .services-grid { grid-template-columns: repeat(4, 1fr); }
            .stats-grid { grid-template-columns: repeat(4, 1fr); }
            .features-grid { grid-template-columns: repeat(3, 1fr); }
        }
    </style>
</head>
<body>

    <div id="loader">
        <div class="loader-text">AURA IoT</div>
        <div style="color: #555; font-size: 12px; margin-top: 10px;">LOADING SYSTEM...</div>
    </div>

    <nav>
        <div class="container nav-content">
            <div class="logo">AURA <span>IoT</span></div>
            <a href="https://share.google/hsKXTXoogh2D3jRPF" class="btn-bill-nav" target="_blank">
                <i class="fas fa-lock"></i> BILLING
            </a>
        </div>
    </nav>

    <section class="hero">
        <div class="container">
            <h1>INTELLIGENCE <br> EVOLVED</h1>
            <p>Robotics | Automation | Web Systems<br>A Subsidiary of SGB Group & Cloud BB</p>
            <a href="#services" class="btn-hero">EXPLORE SERVICES</a>
            <div class="scroll-down">
                <i class="fas fa-chevron-down"></i> Scroll Down
            </div>
        </div>
    </section>

    <div class="partners">
        <div class="container">
            <span>POWERED BY:</span>&nbsp;&nbsp; 
            <strong style="color: #fff;">SGB GROUP</strong> &nbsp;|&nbsp; 
            <strong style="color: #fff;">CLOUD BB</strong>
        </div>
    </div>

    <section class="section">
        <div class="container">
            <div class="text-center mb-50">
                <h2 class="text-primary">OUR CORE</h2>
                <div style="width: 50px; height: 3px; background: var(--primary); margin: 10px auto;"></div>
            </div>
            <div class="vm-grid">
                <div class="vm-card">
                    <h3><i class="fas fa-eye"></i> VISION (දැක්ම)</h3>
                    <p>"To become the leading IoT infrastructure provider in Sri Lanka by 2026, creating smart ecosystems that enhance the quality of life for every citizen."</p>
                </div>
                <div class="vm-card mission">
                    <h3 class="text-gold"><i class="fas fa-bullseye"></i> MISSION (මෙහෙවර)</h3>
                    <p>"To engineer affordable, secure, and energy-efficient automation solutions while empowering the next generation through robotics education."</p>
                </div>
            </div>
        </div>
    </section>

    <section class="section" style="background: #080808;">
        <div class="container about-text">
            <h2 class="mb-20">WHO WE ARE</h2>
            <p>Aura IoT is a Grade 11 student-led innovation hub operating under the massive infrastructure of SGB Group and Cloud BB. We are not just a company; we are a movement towards a smarter Sri Lanka.</p>
            <p>Our team specializes in cutting-edge Robotics, Web Development, and complex Management Systems. We bridge the gap between imagination and reality.</p>
            <p><strong>Founded in:</strong> 2025</p>
            <p><strong>Headquarters:</strong> Colombo, Sri Lanka</p>
        </div>
    </section>

    <div class="stats">
        <div class="container stats-grid">
            <div class="stat-item">
                <h3>15+</h3>
                <p>Projects</p>
            </div>
            <div class="stat-item">
                <h3>24/7</h3>
                <p>Support</p>
            </div>
            <div class="stat-item">
                <h3>100%</h3>
                <p>Secure</p>
            </div>
            <div class="stat-item">
                <h3>2026</h3>
                <p>Goal</p>
            </div>
        </div>
    </div>

    <section class="section">
        <div class="container">
            <h2 class="text-center mb-50">WHY CHOOSE AURA?</h2>
            <div class="features-grid">
                <div class="feature-box">
                    <i class="fas fa-rocket"></i>
                    <h4>Speed & Performance</h4>
                    <p style="color: #777; font-size: 0.9rem;">We use the latest tech stacks to ensure your systems run without lag.</p>
                </div>
                <div class="feature-box">
                    <i class="fas fa-lock"></i>
                    <h4>Bank-Grade Security</h4>
                    <p style="color: #777; font-size: 0.9rem;">Your data is protected by Cloud BB's advanced encryption protocols.</p>
                </div>
                <div class="feature-box">
                    <i class="fas fa-lightbulb"></i>
                    <h4>Innovative Design</h4>
                    <p style="color: #777; font-size: 0.9rem;">We don't just build; we create art through code and circuits.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="services" class="section" style="background: #080808;">
        <div class="container">
            <h2 class="text-center mb-20">OUR SERVICES</h2>
            <p class="text-center mb-50" style="color: #666;">Comprehensive Tech Solutions</p>
            
            <div class="services-grid">
                <div class="service-card"><i class="fas fa-home"></i><h4>Smart Home</h4><p>Automation</p></div>
                <div class="service-card"><i class="fas fa-shield-alt"></i><h4>Security</h4><p>CCTV & AI</p></div>
                <div class="service-card"><i class="fas fa-robot"></i><h4>Robotics</h4><p>Engineering</p></div>
                <div class="service-card"><i class="fas fa-globe"></i><h4>Web Dev</h4><p>Systems</p></div>
                <div class="service-card"><i class="fas fa-file-invoice-dollar"></i><h4>Billing</h4><p>POS</p></div>
                <div class="service-card"><i class="fas fa-wifi"></i><h4>Networking</h4><p>IoT Mesh</p></div>
                <div class="service-card"><i class="fas fa-mobile-alt"></i><h4>Mobile Apps</h4><p>Android/iOS</p></div>
                <div class="service-card"><i class="fas fa-cloud"></i><h4>Cloud</h4><p>Storage</p></div>
                <div class="service-card"><i class="fas fa-bolt"></i><h4>Energy</h4><p>Management</p></div>
                <div class="service-card"><i class="fas fa-microchip"></i><h4>PCB</h4><p>Design</p></div>
                <div class="service-card"><i class="fas fa-headset"></i><h4>Support</h4><p>24/7</p></div>
                <div class="service-card"><i class="fas fa-graduation-cap"></i><h4>Education</h4><p>Training</p></div>
            </div>
        </div>
    </section>

    <section class="section product-section">
        <div class="container">
            <span style="background: var(--primary); color: #000; padding: 5px 10px; border-radius: 4px; font-weight: bold; font-size: 10px;">FLAGSHIP PRODUCT</span>
            <h2 style="font-size: 2.5rem; margin: 20px 0;">AURA G1</h2>
            <p style="color: #bbb;">The Ultimate Smart Home Hub for SLIoT 2026.</p>
            
            <div class="g1-specs">
                <div class="spec"><h5><i class="fas fa-microphone"></i></h5><p>Voice Control</p></div>
                <div class="spec"><h5><i class="fas fa-brain"></i></h5><p>AI Learning</p></div>
                <div class="spec"><h5><i class="fas fa-battery-full"></i></h5><p>Low Power</p></div>
                <div class="spec"><h5><i class="fas fa-wifi"></i></h5><p>WiFi 6</p></div>
            </div>
        </div>
    </section>

    <section class="aura-bill">
        <div class="container">
            <h2>AURA BILL SYSTEM</h2>
            <p style="color: #ddd; max-width: 600px; margin: 0 auto 30px;">
                The most advanced POS & Billing solution for modern businesses. Track sales, inventory, and customers in real-time.
            </p>
            <a href="https://share.google/hsKXTXoogh2D3jRPF" class="btn-gold-big" target="_blank">
                <i class="fas fa-sign-in-alt"></i> LOGIN NOW
            </a>
        </div>
    </section>

    <section class="section">
        <div class="container">
            <h2 class="mb-50 text-center">HOW WE WORK</h2>
            
            <div class="process-step">
                <div class="step-num">01</div>
                <div>
                    <h4>Consultation</h4>
                    <p style="color: #666; font-size: 0.9rem;">We discuss your needs and plan the architecture.</p>
                </div>
            </div>
            <div class="process-step">
                <div class="step-num">02</div>
                <div>
                    <h4>Development</h4>
                    <p style="color: #666; font-size: 0.9rem;">Coding and Engineering phase with rigorous testing.</p>
                </div>
            </div>
            <div class="process-step">
                <div class="step-num">03</div>
                <div>
                    <h4>Deployment</h4>
                    <p style="color: #666; font-size: 0.9rem;">Installation and system launch at your location.</p>
                </div>
            </div>
            <div class="process-step">
                <div class="step-num">04</div>
                <div>
                    <h4>Support</h4>
                    <p style="color: #666; font-size: 0.9rem;">Ongoing maintenance and 24/7 technical help.</p>
                </div>
            </div>
        </div>
    </section>

    <section class="section" style="background: #111; text-align: center;">
        <div class="container">
            <i class="fas fa-quote-left" style="font-size: 2rem; color: var(--primary); margin-bottom: 20px;"></i>
            <p style="font-style: italic; color: #ddd; font-size: 1.1rem; margin-bottom: 20px;">
                "Technology is best when it brings people together. At Aura IoT, we are building the bridges to a smarter tomorrow."
            </p>
            <h4 class="text-primary">- FOUNDER, AURA IOT -</h4>
        </div>
    </section>

    <section class="section">
        <div class="container">
            <h2 class="mb-50 text-center">FAQ</h2>
            <div class="faq-item">
                <h4>Do you provide warranty?</h4>
                <p>Yes, all Aura products come with a 1-year warranty.</p>
            </div>
            <div class="faq-item">
                <h4>Is the system secure?</h4>
                <p>Absolutely. We use Cloud BB's secure servers.</p>
            </div>
            <div class="faq-item">
                <h4>Can I control it remotely?</h4>
                <p>Yes, via our dedicated Mobile App.</p>
            </div>
        </div>
    </section>

    <section id="contact" class="section" style="background: #080808;">
        <div class="container">
            <h2 class="mb-50 text-center">CONTACT US</h2>
            
            <div style="text-align: center; margin-bottom: 40px;">
                <p class="mb-20" style="font-size: 1.2rem;"><i class="fas fa-phone text-primary"></i> 011 330 4820</p>
                <p class="mb-20"><i class="fas fa-envelope text-primary"></i> info@auraiot.lk</p>
                <p><i class="fas fa-map-marker-alt text-primary"></i> Colombo, Sri Lanka</p>
            </div>

            <form class="form-group">
                <input type="text" placeholder="Your Name">
                <input type="email" placeholder="Your Email">
                <input type="text" placeholder="Subject">
                <textarea rows="5" placeholder="Message"></textarea>
                <button type="submit" class="btn-submit">SEND MESSAGE</button>
            </form>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="logo mb-20">AURA <span>IoT</span></div>
            <div class="footer-links">
                <a href="#home">Home</a>
                <a href="#services">Services</a>
                <a href="#contact">Support</a>
                <a href="#">Privacy</a>
            </div>
            <p>&copy; 2026 Aura IoT Corporation.<br>A Subsidiary of SGB Group.</p>
        </div>
    </footer>

    <script>
        // Remove Loader
        window.addEventListener('load', () => {
            setTimeout(() => {
                document.getElementById('loader').style.opacity = '0';
                setTimeout(() => {
                    document.getElementById('loader').style.display = 'none';
                }, 500);
            }, 1500);
        });
    </script>
</body>
</html>
