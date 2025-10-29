# sanc.github.io
page
<!DOCTYPE html>
<html lang="ka">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>San Consulting LLC - sanc.ge</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #1a4d4d;
            --secondary-color: #5a0000;
            --accent-color: #d4af37;
            --text-light: #ffffff;
            --text-dark: #333333;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: #f5f5f5;
            position: relative;
            min-height: 100vh;
        }

        /* Chess Board Background */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                repeating-linear-gradient(
                    0deg,
                    #e0e0e0 0px,
                    #e0e0e0 80px,
                    #ffffff 80px,
                    #ffffff 160px
                ),
                repeating-linear-gradient(
                    90deg,
                    #e0e0e0 0px,
                    #e0e0e0 80px,
                    #ffffff 80px,
                    #ffffff 160px
                );
            opacity: 0.3;
            z-index: -1;
        }

        /* Logo Container */
        .logo-container {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            padding: 2rem;
            position: relative;
        }

        .logo-wrapper {
            position: relative;
            width: 80vw;
            max-width: 1200px;
        }

        .logo-image {
            width: 100%;
            height: auto;
            cursor: pointer;
            transition: transform 0.3s ease;
            display: block;
        }

        .logo-image:hover {
            transform: scale(1.02);
        }

        /* Navigation Menu */
        .nav-menu {
            position: absolute;
            top: 100%;
            left: 50%;
            transform: translateX(-50%);
            background: rgba(255, 255, 255, 0.98);
            border-radius: 15px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.2);
            padding: 1.5rem;
            display: none;
            flex-direction: column;
            gap: 1rem;
            min-width: 300px;
            max-width: 90vw;
            z-index: 1000;
            border: 2px solid var(--primary-color);
            margin-top: 1rem;
        }

        .nav-menu.active {
            display: flex;
            animation: slideDown 0.3s ease;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateX(-50%) translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateX(-50%) translateY(0);
            }
        }

        .nav-menu a {
            padding: 1rem 1.5rem;
            text-decoration: none;
            color: var(--primary-color);
            font-size: 1.1rem;
            font-weight: 600;
            border-radius: 8px;
            transition: all 0.3s ease;
            text-align: center;
            border: 2px solid transparent;
        }

        .nav-menu a:hover {
            background: var(--primary-color);
            color: var(--text-light);
            border-color: var(--primary-color);
            transform: translateX(5px);
        }

        /* Main Content */
        .content {
            max-width: 1400px;
            margin: 0 auto;
            padding: 2rem;
            display: none;
        }

        .content.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .page-title {
            font-size: 3rem;
            color: var(--primary-color);
            text-align: center;
            margin-bottom: 3rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1);
        }

        /* Services Grid */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .service-card {
            background: white;
            padding: 2.5rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            cursor: pointer;
            border: 2px solid transparent;
            text-align: center;
        }

        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2);
            border-color: var(--primary-color);
        }

        .chess-icon {
            font-size: 4rem;
            margin-bottom: 1.5rem;
            filter: drop-shadow(2px 2px 4px rgba(0, 0, 0, 0.2));
        }

        .service-card h3 {
            font-size: 1.5rem;
            color: var(--primary-color);
            margin-bottom: 1rem;
        }

        .service-card p {
            color: #666;
            line-height: 1.6;
        }

        /* About Section */
        .about-content {
            background: white;
            padding: 3rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            max-width: 900px;
            margin: 0 auto;
        }

        .about-content p {
            font-size: 1.2rem;
            line-height: 1.8;
            color: #555;
            margin-bottom: 1.5rem;
        }

        .email-link {
            display: inline-block;
            padding: 1rem 2rem;
            background: var(--primary-color);
            color: white;
            text-decoration: none;
            border-radius: 8px;
            font-size: 1.2rem;
            margin-top: 2rem;
            transition: all 0.3s ease;
        }

        .email-link:hover {
            background: var(--secondary-color);
            transform: scale(1.05);
        }

        /* Consultation Form */
        .consultation-form {
            background: white;
            padding: 3rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            max-width: 700px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--primary-color);
            font-weight: 600;
            font-size: 1.1rem;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            font-family: inherit;
            transition: border-color 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary-color);
        }

        .form-group textarea {
            min-height: 200px;
            resize: vertical;
        }

        .submit-btn {
            width: 100%;
            padding: 1.2rem;
            background: var(--primary-color);
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 1.2rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .submit-btn:hover {
            background: var(--secondary-color);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        /* Contact Section */
        .contact-info {
            background: white;
            padding: 3rem;
            border-radius: 15px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            max-width: 700px;
            margin: 0 auto;
            text-align: center;
        }

        .contact-info h2 {
            font-size: 2rem;
            color: var(--primary-color);
            margin-bottom: 2rem;
        }

        .contact-item {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
            padding: 1.5rem;
            margin: 1rem 0;
            background: #f9f9f9;
            border-radius: 10px;
            font-size: 1.3rem;
        }

        .contact-icon {
            font-size: 2rem;
        }

        /* Back Button */
        .back-btn {
            position: fixed;
            top: 2rem;
            left: 2rem;
            padding: 1rem 2rem;
            background: var(--primary-color);
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 1.1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            z-index: 999;
            display: none;
        }

        .back-btn.active {
            display: block;
        }

        .back-btn:hover {
            background: var(--secondary-color);
            transform: scale(1.05);
        }

        /* Success Message */
        .success-message {
            display: none;
            padding: 1.5rem;
            background: #4caf50;
            color: white;
            border-radius: 8px;
            margin-bottom: 1.5rem;
            text-align: center;
            font-size: 1.1rem;
        }

        .success-message.active {
            display: block;
            animation: slideDown 0.3s ease;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .logo-wrapper {
                width: 90vw;
            }

            .nav-menu {
                min-width: 250px;
                padding: 1.2rem;
            }

            .nav-menu a {
                padding: 0.8rem 1rem;
                font-size: 1rem;
            }

            .page-title {
                font-size: 2rem;
            }

            .services-grid {
                grid-template-columns: 1fr;
            }

            .back-btn {
                top: 1rem;
                left: 1rem;
                padding: 0.8rem 1.5rem;
                font-size: 1rem;
            }
        }

        @media (max-width: 480px) {
            .logo-wrapper {
                width: 95vw;
            }

            .logo-container {
                min-height: 80vh;
                padding: 1rem;
            }

            .nav-menu a {
                font-size: 0.95rem;
                padding: 0.7rem 0.8rem;
            }
        }
    </style>
</head>
<body>
    <button class="back-btn" id="backBtn" onclick="goHome()">← მთავარი</button>

    <div class="logo-container" id="logoContainer">
        <div class="logo-wrapper">
            <img src="https://i.imgur.com/lWhsIF8.png" 
                 alt="San Consulting Logo" 
                 class="logo-image" 
                 id="mainLogo"
                 onerror="this.src='data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 1500 600%22%3E%3Ctext x=%2250%22 y=%22300%22 font-family=%22serif%22 font-size=%22280%22 fill=%22%231a4d4d%22 font-weight=%22300%22%3ESAN%3C/text%3E%3Ctext x=%2250%22 y=%22480%22 font-family=%22Arial%22 font-size=%2280%22 fill=%22%235a0000%22 letter-spacing=%2220%22%3EConsulting%3C/text%3E%3Crect x=%22950%22 y=%2280%22 width=%22500%22 height=%22440%22 fill=%22none%22 stroke=%22black%22 stroke-width=%2212%22 rx=%2210%22/%3E%3Ctext x=%221100%22 y=%22220%22 font-family=%22monospace%22 font-size=%22120%22 fill=%22black%22%3E주문%3C/text%3E%3Ctext x=%221050%22 y=%22360%22 font-family=%22monospace%22 font-size=%22100%22 fill=%22black%22%3E컨설팅%3C/text%3E%3Ccircle cx=%221100%22 cy=%22130%22 r=%2212%22 fill=%22%23d4af37%22/%3E%3Ccircle cx=%221230%22 cy=%22340%22 r=%2215%22 fill=%22%23d4af37%22/%3E%3Ccircle cx=%221050%22 cy=%22450%22 r=%2210%22 fill=%22%23d4af37%22/%3E%3C/svg%3E'">
            <div class="nav-menu" id="navMenu">
                <a href="#" onclick="showPage('services')">სერვისები</a>
                <a href="#" onclick="showPage('about')">ჩვენს შესახებ</a>
                <a href="#" onclick="showPage('consultation')">კონსულტაციის მოთხოვნა</a>
                <a href="#" onclick="showPage('contact')">კონტაქტი</a>
            </div>
        </div>
    </div>

    <!-- Services Page -->
    <div class="content" id="servicesPage">
        <h1 class="page-title">ჩვენი სერვისები</h1>
        <div class="services-grid">
            <div class="service-card" onclick="showPage('contact')">
                <div class="chess-icon">♔</div>
                <h3>Corporate Law</h3>
                <p>კორპორატიული სამართლის სრული სპექტრი</p>
            </div>
            <div class="service-card" onclick="showPage('contact')">
                <div class="chess-icon">♕</div>
                <h3>Real Estate and Privatization</h3>
                <p>უძრავი ქონება და პრივატიზაცია</p>
            </div>
            <div class="service-card" onclick="showPage('contact')">
                <div class="chess-icon">♖</div>
                <h3>Construction Law</h3>
                <p>სამშენებლო სამართალი</p>
            </div>
            <div class="service-card" onclick="showPage('contact')">
                <div class="chess-icon">♗</div>
                <h3>Employment Law</h3>
                <p>შრომითი სამართალი</p>
            </div>
            <div class="service-card" onclick="showPage('contact')">
                <div class="chess-icon">♘</div>
                <h3>Family and Inheritance Law</h3>
                <p>საოჯახო და სამემკვიდრეო სამართალი</p>
            </div>
            <div class="service-card" onclick="showPage('contact')">
                <div class="chess-icon">♙</div>
                <h3>Civil Litigation</h3>
                <p>სამოქალაქო დავები</p>
            </div>
            <div class="service-card" onclick="showPage('contact')">
                <div class="chess-icon">♚</div>
                <h3>Public Procurement</h3>
                <p>საჯარო შესყიდვები</p>
            </div>
            <div class="service-card" onclick="showPage('contact')">
                <div class="chess-icon">♛</div>
                <h3>Legal Drafting</h3>
                <p>იურიდიული დოკუმენტაცია</p>
            </div>
            <div class="service-card" onclick="showPage('contact')">
                <div class="chess-icon">♜</div>
                <h3>Legal Opinions</h3>
                <p>იურიდიული დასკვნები</p>
            </div>
            <div class="service-card" onclick="showPage('contact')">
                <div class="chess-icon">♝</div>
                <h3>Legal Consultancy</h3>
                <p>იურიდიული კონსულტაცია</p>
            </div>
        </div>
    </div>

    <!-- About Page -->
    <div class="content" id="aboutPage">
        <h1 class="page-title">ჩვენს შესახებ</h1>
        <div class="about-content">
            <p>San Consulting LLC არის წამყვანი საკონსულტაციო კომპანია საქართველოში, რომელიც სპეციალიზირებულია იურიდიულ მომსახურებასა და ბიზნეს კონსულტაციაში.</p>
            <p>ჩვენი გამოცდილი პროფესიონალები გთავაზობთ ყოვლისმომცველ მხარდაჭერას კორპორატიულ სამართალში, უძრავ ქონებაში, სამშენებლო სამართალში და სხვა მრავალ მიმართულებაში.</p>
            <p>ჩვენ ვართ ერთგულნი ხარისხის უმაღლესი სტანდარტების დაცვისა და თითოეული კლიენტის ინდივიდუალური საჭიროებების გაგების მიმართ.</p>
            <div style="text-align: center;">
                <a href="mailto:info@sanc.ge" class="email-link">📧 info@sanc.ge</a>
            </div>
        </div>
    </div>

    <!-- Consultation Page -->
    <div class="content" id="consultationPage">
        <h1 class="page-title">კონსულტაციის მოთხოვნა</h1>
        <div class="consultation-form">
            <div class="success-message" id="successMessage">
                ✓ თქვენი შეტყობინება წარმატებით გაიგზავნა!
            </div>
            <form id="consultationForm">
                <div class="form-group">
                    <label for="name">სახელი და გვარი *</label>
                    <input type="text" id="name" name="name" required>
                </div>
                <div class="form-group">
                    <label for="email">ელ.ფოსტა *</label>
                    <input type="email" id="email" name="email" required>
                </div>
                <div class="form-group">
                    <label for="phone">ტელეფონი</label>
                    <input type="tel" id="phone" name="phone">
                </div>
                <div class="form-group">
                    <label for="message">შეტყობინება *</label>
                    <textarea id="message" name="message" required placeholder="აღწერეთ თქვენი საჭიროება..."></textarea>
                </div>
                <button type="submit" class="submit-btn">გაგზავნა</button>
            </form>
        </div>
    </div>

    <!-- Contact Page -->
    <div class="content" id="contactPage">
        <h1 class="page-title">კონტაქტი</h1>
        <div class="contact-info">
            <h2>დაგვიკავშირდით</h2>
            <div class="contact-item">
                <span class="contact-icon">📧</span>
                <a href="mailto:info@sanc.ge" style="color: var(--primary-color); text-decoration: none;">info@sanc.ge</a>
            </div>
            <div class="contact-item">
                <span class="contact-icon">🌐</span>
                <span>www.sanc.ge</span>
            </div>
            <div class="contact-item">
                <span class="contact-icon">📍</span>
                <span>თბილისი, საქართველო</span>
            </div>
        </div>
    </div>

    <script>
        const mainLogo = document.getElementById('mainLogo');
        const navMenu = document.getElementById('navMenu');
        const logoWrapper = document.querySelector('.logo-wrapper');
        const logoContainer = document.getElementById('logoContainer');
        const backBtn = document.getElementById('backBtn');
        const allPages = document.querySelectorAll('.content');

        // Toggle menu on logo hover
        mainLogo.addEventListener('mouseenter', () => {
            navMenu.classList.add('active');
        });

        logoWrapper.addEventListener('mouseleave', () => {
            navMenu.classList.remove('active');
        });

        function showPage(pageName) {
            // Hide all pages
            allPages.forEach(page => page.classList.remove('active'));
            
            // Hide logo container
            logoContainer.style.display = 'none';
            
            // Show selected page
            const pageMap = {
                'services': 'servicesPage',
                'about': 'aboutPage',
                'consultation': 'consultationPage',
                'contact': 'contactPage'
            };
            
            const pageId = pageMap[pageName];
            if (pageId) {
                document.getElementById(pageId).classList.add('active');
            }
            
            // Show back button
            backBtn.classList.add('active');
            
            // Close menu
            navMenu.classList.remove('active');
        }

        function goHome() {
            // Hide all pages
            allPages.forEach(page => page.classList.remove('active'));
            
            // Show logo container
            logoContainer.style.display = 'flex';
            
            // Hide back button
            backBtn.classList.remove('active');
        }

        // Form submission
        document.getElementById('consultationForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const phone = document.getElementById('phone').value;
            const message = document.getElementById('message').value;
            
            const subject = encodeURIComponent('კონსულტაციის მოთხოვნა - ' + name);
            const body = encodeURIComponent(
                'სახელი: ' + name + '\n' +
                'ელ.ფოსტა: ' + email + '\n' +
                'ტელეფონი: ' + phone + '\n\n' +
                'შეტყობინება:\n' + message
            );
            
            // Open email client
            window.location.href = 'mailto:info@sanc.ge?subject=' + subject + '&body=' + body;
            
            // Show success message
            document.getElementById('successMessage').classList.add('active');
            
            // Reset form
            this.reset();
            
            // Hide success message after 5 seconds
            setTimeout(() => {
                document.getElementById('successMessage').classList.remove('active');
            }, 5000);
        });
    </script>
</body>
</html>
