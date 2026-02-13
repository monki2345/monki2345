<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>monki2345 - Online Safety for Everyone</title>
  <link href="https://fonts.googleapis.com/css2?family=Lexend:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Lexend', sans-serif;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      color: #fff;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }

    .container {
      max-width: 1000px;
      width: 100%;
      text-align: center;
    }

    .logo {
      width: 200px;
      height: 200px;
      margin: 0 auto 32px;
      background: #ffe66b;
      border-radius: 50%;
      border: 8px solid white;
      box-shadow: 0 12px 40px rgba(0,0,0,0.3);
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
      animation: float 3s ease-in-out infinite;
    }

    .logo img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    @keyframes float {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-20px); }
    }

    h1 {
      font-size: 4rem;
      margin-bottom: 16px;
      text-shadow: 0 4px 12px rgba(0,0,0,0.3);
      animation: fadeIn 1s ease-out;
    }

    .tagline {
      font-size: 1.5rem;
      margin-bottom: 48px;
      opacity: 0.95;
      animation: fadeIn 1.5s ease-out;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .welcome-box {
      background: rgba(255,255,255,0.15);
      backdrop-filter: blur(10px);
      border-radius: 24px;
      padding: 40px;
      margin-bottom: 40px;
      border: 2px solid rgba(255,255,255,0.3);
      box-shadow: 0 8px 32px rgba(0,0,0,0.2);
    }

    .welcome-box h2 {
      font-size: 2rem;
      margin-bottom: 16px;
    }

    .welcome-box p {
      font-size: 1.2rem;
      line-height: 1.8;
      margin-bottom: 12px;
    }

    .features {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 24px;
      margin: 40px 0;
    }

    .feature {
      background: rgba(255,255,255,0.1);
      backdrop-filter: blur(10px);
      border-radius: 20px;
      padding: 32px;
      border: 2px solid rgba(255,255,255,0.2);
      transition: all 0.3s;
    }

    .feature:hover {
      transform: translateY(-8px);
      background: rgba(255,255,255,0.2);
      box-shadow: 0 12px 32px rgba(0,0,0,0.3);
    }

    .feature .icon {
      font-size: 3.5rem;
      margin-bottom: 16px;
    }

    .feature h3 {
      font-size: 1.4rem;
      margin-bottom: 12px;
    }

    .feature p {
      font-size: 1rem;
      opacity: 0.9;
      line-height: 1.6;
    }

    .cta-buttons {
      display: flex;
      gap: 20px;
      justify-content: center;
      flex-wrap: wrap;
      margin-top: 40px;
    }

    .btn {
      padding: 18px 40px;
      font-size: 1.3rem;
      font-weight: 600;
      font-family: 'Lexend', sans-serif;
      border: none;
      border-radius: 16px;
      cursor: pointer;
      transition: all 0.3s;
      text-decoration: none;
      display: inline-block;
      box-shadow: 0 6px 20px rgba(0,0,0,0.2);
    }

    .btn-primary {
      background: #ffe66b;
      color: #333;
    }

    .btn-primary:hover {
      background: #ffd700;
      transform: translateY(-4px);
      box-shadow: 0 12px 32px rgba(255,230,107,0.4);
    }

    .btn-secondary {
      background: white;
      color: #667eea;
    }

    .btn-secondary:hover {
      background: #f0f0f0;
      transform: translateY(-4px);
      box-shadow: 0 12px 32px rgba(255,255,255,0.3);
    }

    footer {
      margin-top: 60px;
      padding: 24px;
      opacity: 0.8;
      font-size: 0.95rem;
    }

    footer a {
      color: #ffe66b;
      text-decoration: none;
    }

    footer a:hover {
      text-decoration: underline;
    }

    @media (max-width: 768px) {
      h1 {
        font-size: 2.5rem;
      }

      .tagline {
        font-size: 1.2rem;
      }

      .welcome-box {
        padding: 24px;
      }

      .logo {
        width: 150px;
        height: 150px;
      }
    }

    /* Welcome message modal */
    .modal {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.7);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 999;
      animation: fadeIn 0.3s ease-out;
    }

    .modal-content {
      background: white;
      padding: 40px;
      border-radius: 20px;
      width: 90%;
      max-width: 500px;
      text-align: center;
      color: #333;
      box-shadow: 0 12px 48px rgba(0,0,0,0.3);
    }

    .modal-content h2 {
      color: #667eea;
      margin-bottom: 16px;
    }

    .modal-content p {
      color: #666;
      line-height: 1.6;
      margin-bottom: 24px;
    }

    .modal-content button {
      background: #667eea;
      color: white;
      border: none;
      padding: 12px 32px;
      border-radius: 12px;
      font-size: 1.1rem;
      font-weight: 600;
      cursor: pointer;
      font-family: 'Lexend', sans-serif;
      transition: all 0.3s;
    }

    .modal-content button:hover {
      background: #5568d3;
      transform: translateY(-2px);
    }

    .hidden {
      display: none;
    }
  </style>
</head>
<body>

  <!-- Welcome Message Modal -->
  <div id="welcomeMessage" class="modal">
    <div class="modal-content">
      <h2>Welcome to monki2345!</h2>
      <p><strong>monki2345 does not collect or store any personal information.</strong></p>
      <p>Everything you do stays on your device. Your privacy and safety are our top priority!</p>
      <button onclick="closeWelcome()">Let's Get Started! 🚀</button>
    </div>
  </div>

  <div class="container">
    <div class="logo">
      <img src="logo.png" alt="monki2345 mascot">
    </div>

    <h1>monki2345</h1>
    <p class="tagline">Learn to Stay Safe Online</p>

    <div class="welcome-box">
      <h2>Stay Safe, Stay Smart, Stay Secure</h2>
      <p>Learn essential online safety skills through fun, interactive lessons. Created for the Girls Who Code Challenge to help everyone navigate the internet safely!</p>
      <p><strong>No accounts needed. No personal data collected. 100% free forever.</strong></p>
    </div>

    <div class="features">
      <div class="feature">
        <div class="icon">🔐</div>
        <h3>Strong Passwords</h3>
        <p>Learn how to create passwords that keep hackers out and protect your digital life.</p>
      </div>

      <div class="feature">
        <div class="icon">🎣</div>
        <h3>Spot Scams</h3>
        <p>Recognize phishing attempts, fake messages, and online tricks before they fool you.</p>
      </div>

      <div class="feature">
        <div class="icon">👣</div>
        <h3>Digital Footprints</h3>
        <p>Understand how your online actions create a lasting trail and how to manage it wisely.</p>
      </div>
    </div>

    <div class="cta-buttons">
      <a href="lessons.html" class="btn btn-primary">Start Learning →</a>
      <a href="#about" class="btn btn-secondary" onclick="scrollToAbout(event)">Learn More</a>
    </div>

    <div id="about" class="welcome-box" style="margin-top: 60px; text-align: left;">
      <h2>About This Project</h2>
      <p>monki2345 is an educational platform focusing on AI + Cybersecurity and online safety.</p>
      
      <p style="margin-top: 16px;"><strong>What You'll Learn:</strong></p>
      <ul style="margin-left: 24px; margin-top: 8px;">
        <li>How to create strong, memorable passwords</li>
        <li>How to identify and avoid online scams and phishing</li>
        <li>How to manage your digital footprint responsibly</li>
        <li>How AI can both help and harm online safety</li>
      </ul>

      <p style="margin-top: 16px;"><strong>Why It Matters:</strong></p>
      <p>Every day, millions of people fall victim to online scams, weak passwords get hacked, and careless posts affect future opportunities. These free lessons give you the knowledge to stay safe online.</p>

      <p style="margin-top: 16px;"><strong>Open Source & Free:</strong></p>
      <p>This project is licensed under Creative Commons Attribution 4.0 (CC BY 4.0). You're free to share, adapt, and use this project - even commercially - as long as you give credit.</p>
    </div>

    <footer>
      <p>© 2026 monki2345 — Licensed under <a href="https://creativecommons.org/licenses/by/4.0/" target="_blank">CC BY 4.0</a></p>
    </footer>
  </div>

  <script>
    // Show welcome message on first visit
    window.onload = function() {
      const hasVisited = localStorage.getItem('hasVisited');
      if (!hasVisited) {
        document.getElementById('welcomeMessage').style.display = 'flex';
      } else {
        document.getElementById('welcomeMessage').classList.add('hidden');
      }
    };

    function closeWelcome() {
      document.getElementById('welcomeMessage').classList.add('hidden');
      localStorage.setItem('hasVisited', 'true');
    }

    function scrollToAbout(event) {
      event.preventDefault();
      document.getElementById('about').scrollIntoView({ 
        behavior: 'smooth',
        block: 'center'
      });
    }

    // If logo doesn't load, show text instead
    document.querySelector('.logo img').addEventListener('error', function() {
      this.style.display = 'none';
      this.parentElement.innerHTML += '<div style="font-size: 1.5rem; color: #333; font-weight: 600;">monki2345<br><small style="font-size: 0.8rem;">mascot</small></div>';
    });
  </script>
</body>
</html>
