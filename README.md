# placement-elegibility-critria
 A modern UI design with soft gradients, smooth animations, rounded cards, and a minimal layout.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Placement Eligibility Criteria Portal</title>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        /* Gradient Background */
        body {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }

        /* Navigation */
        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            padding: 1rem 0;
            transition: all 0.3s ease;
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            background: linear-gradient(45deg, #4f46e5, #06b6d4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #4f46e5;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: linear-gradient(45deg, #4f46e5, #06b6d4);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .hamburger span {
            width: 25px;
            height: 3px;
            background: #333;
            margin: 3px 0;
            transition: 0.3s;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.4);
            z-index: 1;
        }

        .hero-content {
            max-width: 800px;
            padding: 0 2rem;
            position: relative;
            z-index: 2;
            animation: fadeInUp 1s ease;
        }

        .hero h1 {
            font-size: clamp(2.5rem, 5vw, 4rem);
            font-weight: 700;
            margin-bottom: 1.5rem;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .hero p {
            font-size: 1.3rem;
            margin-bottom: 2rem;
            opacity: 0.95;
        }

        .cta-button {
            display: inline-block;
            background: linear-gradient(45deg, #10b981, #059669);
            color: white;
            padding: 1rem 2.5rem;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(16, 185, 129, 0.3);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(16, 185, 129, 0.4);
        }

        /* Sections */
        .section {
            padding: 5rem 0;
            max-width: 1200px;
            margin: 0 auto;
            padding-left: 2rem;
            padding-right: 2rem;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 3rem;
            background: linear-gradient(45deg, #4f46e5, #06b6d4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* Eligibility Cards */
        .criteria-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .criteria-card {
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            border: 1px solid rgba(255,255,255,0.2);
            position: relative;
            overflow: hidden;
        }

        .criteria-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(45deg, #4f46e5, #06b6d4);
        }

        .criteria-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 60px rgba(0,0,0,0.15);
        }

        .criteria-icon {
            font-size: 3rem;
            background: linear-gradient(45deg, #4f46e5, #06b6d4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1rem;
        }

        /* Checker Form */
        .checker-container {
            max-width: 500px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            padding: 3rem;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.1);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
            color: #333;
        }

        .form-group input, .form-group select {
            width: 100%;
            padding: 1rem;
            border: 2px solid #e5e7eb;
            border-radius: 12px;
            font-size: 1rem;
            transition: all 0.3s ease;
            font-family: inherit;
        }

        .form-group input:focus, .form-group select:focus {
            outline: none;
            border-color: #4f46e5;
            box-shadow: 0 0 0 3px rgba(79, 70, 229, 0.1);
        }

        .submit-btn {
            width: 100%;
            background: linear-gradient(45deg, #4f46e5, #06b6d4);
            color: white;
            padding: 1rem;
            border: none;
            border-radius: 12px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(79, 70, 229, 0.3);
        }

        .result {
            margin-top: 2rem;
            padding: 1.5rem;
            border-radius: 12px;
            text-align: center;
            font-weight: 600;
            display: none;
            animation: slideIn 0.5s ease;
        }

        .result.success {
            background: linear-gradient(45deg, #10b981, #059669);
            color: white;
        }

        .result.error {
            background: linear-gradient(45deg, #ef4444, #dc2626);
            color: white;
        }

        /* Accordion */
        .accordion {
            max-width: 800px;
            margin: 0 auto;
        }

        .accordion-item {
            background: rgba(255, 255, 255, 0.95);
            margin-bottom: 1rem;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .accordion-header {
            padding: 1.5rem 2rem;
            background: white;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: 600;
            transition: background 0.3s ease;
        }

        .accordion-header:hover {
            background: #f8fafc;
        }

        .accordion-content {
            max-height: 0;
            overflow: hidden;
            background: #f8fafc;
            transition: max-height 0.3s ease;
        }

        .accordion-content.active {
            max-height: 500px;
        }

        .accordion-content-inner {
            padding: 2rem;
        }

        /* Contact */
        .contact-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 3rem;
            margin-top: 3rem;
        }

        .contact-card {
            background: rgba(255, 255, 255, 0.95);
            padding: 2.5rem;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .contact-card:hover {
            transform: translateY(-5px);
        }

        .contact-icon {
            font-size: 3rem;
            background: linear-gradient(45deg, #4f46e5, #06b6d4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1rem;
        }

        /* Footer */
        .footer {
            background: rgba(0, 0, 0, 0.9);
            color: white;
            text-align: center;
            padding: 3rem 2rem 1.5rem;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 2rem;
            flex-wrap: wrap;
        }

        .footer-links a {
            color: #ccc;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-links a:hover {
            color: #4f46e5;
        }

        .social-icons {
            margin-top: 1rem;
        }

        .social-icons a {
            display: inline-block;
            margin: 0 1rem;
            font-size: 1.5rem;
            color: #ccc;
            transition: color 0.3s ease;
        }

        .social-icons a:hover {
            color: #4f46e5;
        }

        /* Animations */
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hamburger {
                display: flex;
            }

            .nav-links {
                position: fixed;
                left: -100%;
                top: 70px;
                flex-direction: column;
                background-color: white;
                width: 100%;
                text-align: center;
                transition: 0.3s;
                box-shadow: 0 10px 27px rgba(0,0,0,0.05);
                padding: 2rem 0;
            }

            .nav-links.active {
                left: 0;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .section {
                padding: 3rem 1rem;
            }

            .checker-container {
                margin: 0 1rem;
                padding: 2rem 1.5rem;
            }
        }

        /* Smooth Scroll */
        html {
            scroll-behavior: smooth;
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: #f1f1f1;
        }

        ::-webkit-scrollbar-thumb {
            background: linear-gradient(45deg, #4f46e5, #06b6d4);
            border-radius: 4px;
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar">
        <div class="nav-container">
            <div class="logo">🎓 PEC Portal</div>
            <ul class="nav-links" id="navLinks">
                <li><a href="#home">Home</a></li>
                <li><a href="#criteria">Criteria</a></li>
                <li><a href="#checker">Checker</a></li>
                <li><a href="#companies">Companies</a></li>
                <li><a href="#guidelines">Guidelines</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <div class="hamburger" id="hamburger">
                <span></span>
                <span></span>
                <span></span>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>Check Your Placement Eligibility</h1>
            <p>Ensure you meet all the placement criteria and guidelines before applying for campus placements. Get instant eligibility verification!</p>
            <a href="#checker" class="cta-button">Check Eligibility</a>
        </div>
    </section>

    <!-- Eligibility Criteria -->
    <section id="criteria" class="section">
        <h2 class="section-title">Eligibility Criteria</h2>
        <div class="criteria-grid">
            <div class="criteria-card">
                <div class="criteria-icon">
                    <i class="fas fa-graduation-cap"></i>
                </div>
                <h3>Minimum CGPA</h3>
                <p><strong>7.0</strong> or above (on 10-point scale) in all semesters up to the pre-final year.</p>
            </div>
            <div class="criteria-card">
                <div class="criteria-icon">
                    <i class="fas fa-calendar-check"></i>
                </div>
                <h3>Attendance</h3>
                <p>Minimum <strong>75%</strong> attendance in each semester. No semester should have less than 65% attendance.</p>
            </div>
            <div class="criteria-card">
                <div class="criteria-icon">
                    <i class="fas fa-exclamation-triangle"></i>
                </div>
                <h3>No Backlogs</h3>
                <p>No active backlogs at the time of placement drive. All previous backlogs must be cleared.</p>
            </div>
            <div class="criteria-card">
                <div class="criteria-icon">
                    <i class="fas fa-code-branch"></i>
                </div>
                <h3>Branch Rules</h3>
                <p>CSE/IT/ECE: CGPA 7.0+, Mechanical/Civil: CGPA 6.5+. Specific companies may have higher requirements.</p>
            </div>
            <div class="criteria-card">
                <div class="criteria-icon">
                    <i class="fas fa-clock"></i>
                </div>
                <h3>Year Gap Policy</h3>
                <p>Maximum 2 years gap allowed after 12th. Gap certificate required for explanation.</p>
            </div>
        </div>
    </section>

    <!-- Eligibility Checker -->
    <section id="checker" class="section">
        <h2 class="section-title">Eligibility Checker</h2>
        <div class="checker-container">
            <form id="eligibilityForm">
                <div class="form-group">
                    <label for="name">Full Name</label>
                    <input type="text" id="name" required>
                </div>
                <div class="form-group">
                    <label for="department">Department</label>
                    <select id="department" required>
                        <option value="">Select Department</option>
                        <option value="CSE">Computer Science</option>
                        <option value="IT">Information Technology</option>
                        <option value="ECE">Electronics & Communication</option>
                        <option value="ME">Mechanical</option>
                        <option value="CE">Civil</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="cgpa">CGPA (out of 10)</label>
                    <input type="number" id="cgpa" min="0" max="10" step="0.1" required>
                </div>
                <div class="form-group">
                    <label for="backlogs">Active Backlogs</label>
                    <input type="number" id="backlogs" min="0" required>
                </div>
                <div class="form-group">
                    <label for="attendance">Attendance %</label>
                    <input type="number" id="attendance" min="0" max="100" required>
                </div>
                <button type="submit" class="submit-btn">Check Eligibility</button>
            </form>
            <div id="result" class="result"></div>
        </div>
    </section>

    <!-- Company-wise Criteria -->
    <section id="companies" class="section">
        <h2 class="section-title">Company-wise Criteria</h2>
        <div class="accordion">
            <div class="accordion-item">
                <div class="accordion-header">
                    <span>Google - Software Engineer</span>
                    <i class="fas fa-chevron-down"></i>
                </div>
                <div class="accordion-content">
                    <div class="accordion-content-inner">
                        <p><strong>CGPA:</strong> 8.0+ | <strong>Backlogs:</strong> None | <strong>Branches:</strong> CSE/IT/ECE</p>
                        <p>DSA rounds + System Design + Behavioral</p>
                    </div>
                </div>
            </div>
            <div class="accordion-item">
                <div class="accordion-header">
                    <span>Microsoft - SDE</span>
                    <i class="fas fa-chevron-down"></i>
                </div>
                <div class="accordion-content">
                    <div class="accordion-content-inner">
                        <p><strong>CGPA:</strong> 7.5+ | <strong>Backlogs:</strong> None | <strong>Branches:</strong> CSE/IT/ECE</p>
                        <p>2 DSA rounds + 1 Project round</p>
                    </div>
                </div>
            </div>
            <div class="accordion-item">
                <div class="accordion-header">
                    <span>TCS - Digital</span>
                    <i class="fas fa-chevron-down"></i>
                </div>
                <div class="accordion-content">
                    <div class="accordion-content-inner">
                        <p><strong>CGPA:</strong> 7.0+ | <strong>Backlogs:</strong> Max 1 | <strong>Branches:</strong> All</p>
                        <p>Online test + Technical + HR</p>
                    </div>
                </div>
            </div>
            <div class="accordion-item">
                <div class="accordion-header">
                    <span>L&T - Graduate Engineer</span>
                    <i class="fas fa-chevron-down"></i>
                </div>
                <div class="accordion-content">
                    <div class="accordion-content-inner">
                        <p><strong>CGPA:</strong> 7.0+ | <strong>Backlogs:</strong> None | <strong>Branches:</strong> ME/CE/ECE</p>
                        <p>Technical test + Interview</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Guidelines -->
    <section id="guidelines" class="section">
        <h2 class="section-title">Important Guidelines</h2>
        <div class="criteria-grid">
            <div class="criteria-card">
                <h3>Placement Rules</h3>
                <p>Students can participate in maximum 3 company drives. First come first serve basis for registration.</p>
            </div>
            <div class="criteria-card">
                <h3>Code of Conduct</h3>
                <p>Maintain professionalism during interviews. No sharing of interview questions or experiences publicly.</p>
            </div>
            <div class="criteria-card">
                <h3>Registration Steps</h3>
                <p>1. Register on portal → 2. Upload documents → 3. Get approval → 4. Attend drive</p>
            </div>
        </div>
    </section>

    <!-- Contact -->
    <section id="contact" class="section">
        <h2 class="section-title">Contact Us</h2>
        <form style="max-width: 500px; margin: 0 auto 3rem;">
            <div class="form-group">
                <input type="text" placeholder="Your Name" required>
            </div>
            <div class="form-group">
                <input type="email" placeholder="Your Email" required>
            </div>
            <div class="form-group">
                <textarea style="height: 120px; padding: 1rem; border-radius: 12px; border: 2px solid #e5e7eb; width: 100%; font-family: inherit;" placeholder="Your Message" required></textarea>
            </div>
            <button type="submit" class="submit-btn">Send Message</button>
        </form>
        
        <div class="contact-info">
            <div class="contact-card">
                <div class="contact-icon">
                    <i class="fas fa-user-tie"></i>
                </div>
                <h3>GOPAL KUMAR</h3>
                <p>Placement cell<br>
                <strong>Email:</strong> 23bca10022@cuchd.in<br>
                <strong>Phone:</strong> +91 9798796398</p>
            </div>
            <div class="contact-card">
                <div class="contact-icon">
                    <i class="fas fa-building"></i>
                </div>
                <h3>Placement Cell</h3>
                <p>Training & Placement Department<br>
                A1 Block, chandigarh university <br>
                Chandigarh, India</p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
        <div class="footer-links">
            <a href="#home">Home</a>
            <a href="#criteria">Eligibility</a>
            <a href="#checker">Checker</a>
            <a href="#companies">Companies</a>
            <a href="#guidelines">Guidelines</a>
            <a href="#contact">Contact</a>
        </div>
        <div class="social-icons">
            <a href="#"><i class="fab fa-linkedin"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="#"><i class="fab fa-facebook"></i></a>
        </div>
        <p style="margin-top: 1rem; opacity: 0.8;">© 2026 Placement Eligibility Portal. All rights reserved.</p>
    </footer>

    <script>
        // Mobile Navigation
        const hamburger = document.getElementById('hamburger');
        const navLinks = document.getElementById('navLinks');

        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });

        // Close mobile menu on link click
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
            });
        });

        // Navbar background on scroll
        window.addEventListener('scroll', () => {
            const navbar = document.querySelector('.navbar');
            if (window.scrollY > 100) {
                navbar.style.background = 'rgba(255, 255, 255, 0.98)';
            } else {
                navbar.style.background = 'rgba(255, 255, 255, 0.95)';
            }
        });

        // Eligibility Checker
        const form = document.getElementById('eligibilityForm');
        const result = document.getElementById('result');

        form.addEventListener('submit', (e) => {
            e.preventDefault();
            
            const cgpa = parseFloat(document.getElementById('cgpa').value);
            const backlogs = parseInt(document.getElementById('backlogs').value);
            const attendance = parseFloat(document.getElementById('attendance').value);
            const department = document.getElementById('department').value;

            let reasons = [];
            let isEligible = true;

            // CGPA Check
            const minCGPA = department === 'ME' || department === 'CE' ? 6.5 : 7.0;
            if (cgpa < minCGPA) {
                reasons.push(`CGPA ${cgpa} is below required ${minCGPA}`);
                isEligible = false;
            }

            // Backlogs Check
            if (backlogs > 0) {
                reasons.push(`${backlogs} active backlogs found`);
                isEligible = false;
            }

            // Attendance Check
            if (attendance < 75) {
                reasons.push(`Attendance ${attendance}% is below 75%`);
                isEligible = false;
            }

            // Show result
            if (isEligible) {
                result.textContent = '🎉 Congratulations! You are ELIGIBLE for placements!';
                result.className = 'result success';
            } else {
                result.innerHTML = `❌ Not Eligible<br><small>${reasons.join(', ')}</small>`;
                result.className = 'result error';
            }
            result.style.display = 'block';
            
            // Scroll to result
            result.scrollIntoView({ behavior: 'smooth' });
        });

        // Accordion Functionality
        document.querySelectorAll('.accordion-header').forEach(header => {
            header.addEventListener('click', () => {
                const content = header.nextElementSibling;
                const icon = header.querySelector('i');
                
                content.classList.toggle('active');
                icon.style.transform = content.classList.contains('active') ? 'rotate(180deg)' : 'rotate(0deg)';
                icon.style.transition = 'transform 0.3s ease';
            });
        });

        // Form validation
        ['cgpa', 'backlogs', 'attendance'].forEach(id => {
            const input = document.getElementById(id);
            input.addEventListener('input', () => {
                if (input.validity.valid) {
                    input.style.borderColor = '#e5e7eb';
                } else {
                    input.style.borderColor = '#ef4444';
                }
            });
        });

        // Animate cards on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.criteria-card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = 'all 0.6s ease';
            observer.observe(card);
        });
    </script>
</body>
</html>
