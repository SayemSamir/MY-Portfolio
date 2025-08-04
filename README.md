<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>My Portfolio</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <link rel="stylesheet" href="https://unpkg.com/aos@next/dist/aos.css" />
  <style id="app-style">
    :root {
      --primary-bg: #121212;
      --secondary-bg: #1e1e1e;
      --tertiary-bg: #2a2a2a;
      --primary-text: #f0f0f0;
      --secondary-text: #a0a0a0;
      --accent: #64ffda;
      --gradient-start: #64ffda;
      --gradient-end: #4c6ef5;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background-color: var(--primary-bg);
      color: var(--primary-text);
      font-family: 'Inter', sans-serif;
    }

    .section {
      min-height: 100vh;
      padding: 6rem 0;
    }

    .accent-text {
      color: var(--accent);
    }

    .accent-gradient {
      background: linear-gradient(90deg, var(--gradient-start), var(--gradient-end));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .navbar-active {
      color: var(--accent);
      position: relative;
    }

    .navbar-active::after {
      content: "";
      position: absolute;
      bottom: -4px;
      left: 0;
      width: 100%;
      height: 2px;
      background-color: var(--accent);
    }

    .card {
      background-color: var(--secondary-bg);
      border-radius: 0.5rem;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }

    .card:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
    }

    .skill-bar {
      height: 8px;
      background-color: var(--tertiary-bg);
      border-radius: 4px;
    }

    .skill-progress {
      height: 100%;
      background: linear-gradient(90deg, var(--gradient-start), var(--gradient-end));
      border-radius: 4px;
    }

    .timeline-dot {
      width: 16px;
      height: 16px;
      background-color: var(--accent);
      border-radius: 50%;
    }

    .timeline-line {
      width: 2px;
      background-color: var(--tertiary-bg);
    }

    .mobile-menu {
      transform: translateY(-100%);
      transition: transform 0.3s ease;
    }

    .mobile-menu.active {
      transform: translateY(0);
    }

    .hero-particles {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 0;
    }

    .form-input {
      background-color: var(--secondary-bg);
      border: 1px solid var(--tertiary-bg);
      color: var(--primary-text);
      padding: 0.75rem 1rem;
      border-radius: 0.375rem;
      width: 100%;
      transition: border-color 0.3s ease;
    }

    .form-input:focus {
      outline: none;
      border-color: var(--accent);
    }
    .light-theme {
  --primary-bg: #ffffff;
  --secondary-bg: #f5f5f5;
  --tertiary-bg: #e0e0e0;
  --primary-text: #333333;
  --secondary-text: #666666;
  --accent: #4c6ef5;
}

  </style>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
</head>
<body>
  <!-- Navbar -->
  <nav class="fixed top-0 left-0 right-0 z-50 bg-opacity-80 backdrop-blur-md bg-[var(--primary-bg)] shadow-md">
    <div class="container mx-auto px-4 py-4">
      <div class="flex justify-between items-center">
        <div class="text-xl font-bold accent-text">
          <a href="#home">Sayem Uddin Samir</a>
        </div>
<!-- In your navbar -->
<div class="flex items-center ml-4">
  <button id="theme-toggle" class="p-2 rounded-full hover:bg-[var(--tertiary-bg)] transition-colors">
    <i class="fas fa-moon text-[var(--primary-text)]"></i>
    <i class="fas fa-sun text-[var(--primary-text)] hidden"></i>
  </button>
</div>
        <div class="hidden md:flex space-x-8 items-center">
          <a href="#home" class="navbar-active hover:text-[var(--accent)] transition-colors">Home</a>
          <a href="#about" class="hover:text-[var(--accent)] transition-colors">About Me</a>
          <a href="#projects" class="hover:text-[var(--accent)] transition-colors">Projects</a>
          <a href="#blog" class="hover:text-[var(--accent)] transition-colors">Blog</a>
          <a href="#skills" class="hover:text-[var(--accent)] transition-colors">Skills</a>
          <a href="#resume" class="hover:text-[var(--accent)] transition-colors">Resume</a>
          <a href="#contact" class="hover:text-[var(--accent)] transition-colors">Contact</a>
        </div>
        <div class="md:hidden">
          <button id="menu-toggle" class="text-2xl text-[var(--primary-text)]">
            <i class="fas fa-bars"></i>
          </button>
        </div>
      </div>
    </div>
  </nav>

  <!-- Mobile Menu -->
  <div id="mobile-menu" class="mobile-menu fixed top-16 left-0 right-0 bg-[var(--secondary-bg)] z-40 shadow-md">
    <div class="container mx-auto px-4 py-4">
      <div class="flex flex-col space-y-4">
        <a href="#home" class="py-2 hover:text-[var(--accent)] transition-colors">Home</a>
        <a href="#about" class="py-2 hover:text-[var(--accent)] transition-colors">About Me</a>
        <a href="#projects" class="py-2 hover:text-[var(--accent)] transition-colors">Projects</a>
        <a href="#blog" class="py-2 hover:text-[var(--accent)] transition-colors">Blog</a>
        <a href="#skills" class="py-2 hover:text-[var(--accent)] transition-colors">Skills</a>
        <a href="#resume" class="py-2 hover:text-[var(--accent)] transition-colors">Resume</a>
        <a href="#contact" class="py-2 hover:text-[var(--accent)] transition-colors">Contact</a>
      </div>
    </div>
  </div>

  <!-- Home Section -->
  <section id="home" class="section flex items-center justify-center relative overflow-hidden">
    <div id="particles-js" class="hero-particles"></div>
    <div class="container mx-auto px-4 z-10">
      <div class="text-center" data-aos="fade-up" data-aos-duration="1000">
        <p class="text-lg text-[var(--accent)] mb-4 font-medium">Hello, I'm</p>
        <h1 class="text-5xl md:text-7xl font-bold mb-4">Gazi Sayem Uddin Samir</h1>
        <h2 class="text-2xl md:text-4xl font-light mb-8 text-[var(--secondary-text)]">
          <span class="accent-gradient">Full-Stack Developer</span> crafting digital experiences
        </h2>
        <div class="flex justify-center space-x-4 mt-8">
          <a href="#projects" class="px-8 py-3 bg-[var(--accent)] text-[var(--primary-bg)] font-medium rounded-md hover:opacity-90 transition-opacity">
            View My Work
          </a>
          <a href="#contact" class="px-8 py-3 border border-[var(--accent)] text-[var(--accent)] font-medium rounded-md hover:bg-[var(--accent)] hover:bg-opacity-10 transition-all">
            Contact Me
          </a>
        </div>
      </div>
    </div>
  </section>

  <!-- About Me Section -->
  <section id="about" class="section bg-[var(--secondary-bg)]">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl md:text-4xl font-bold mb-12 text-center" data-aos="fade-up">About <span class="accent-text">Me</span></h2>
      <div class="grid grid-cols-1 md:grid-cols-12 gap-12">
        <div class="md:col-span-4 flex justify-center" data-aos="fade-right">
          <div class="relative w-64 h-64 md:w-80 md:h-80">
            <div class="w-full h-full rounded-full overflow-hidden border-4 border-[var(--accent)]">
              <img src="https://avatars.githubusercontent.com/u/205399761?v=4" alt="Profile Photo" class="w-full h-full object-cover">
            </div>
          </div>
        </div>
        <div class="md:col-span-8" data-aos="fade-left">
          <h3 class="text-2xl font-bold mb-4">Who am I?</h3>
          <p class="text-lg text-[var(--secondary-text)] mb-6">
            I'm a passionate full-stack developer with over 5 years of experience building web applications that are both beautiful and functional.
            I specialize in modern JavaScript frameworks, responsive design, and creating intuitive user experiences.
          </p>
          <p class="text-lg text-[var(--secondary-text)] mb-6">
            When I'm not coding, you'll find me exploring new technologies, contributing to open-source projects, or hiking in the mountains.
            I believe in continuous learning and pushing the boundaries of what's possible on the web.
          </p>
          
          <div class="mt-8 grid grid-cols-2 gap-4">
            <div>
              <p class="text-[var(--accent)] font-medium mb-2">Name:</p>
              <p class="text-[var(--secondary-text)]">Gazi Sayem Uddin Samir</p>
            </div>
            <div>
              <p class="text-[var(--accent)] font-medium mb-2">Email:</p>
              <p class="text-[var(--secondary-text)]">sayemuddinsamir00@gmail.com</p>
            </div>
            <div>
              <p class="text-[var(--accent)] font-medium mb-2">From:</p>
              <p class="text-[var(--secondary-text)]">Chattogram , Bangladesh</p>
            </div>
            <div>
              <p class="text-[var(--accent)] font-medium mb-2">Experience:</p>
              <p class="text-[var(--secondary-text)]">No Experience</p>
            </div>
          </div>
        </div>
      </div>

      <!-- Experience Timeline -->
      <div class="mt-20" data-aos="fade-up">
        <h3 class="text-2xl font-bold mb-8 text-center">Experience <span class="accent-text">Timeline</span></h3>
        <div class="relative">
          <!-- Timeline Line -->
          <div class="timeline-line absolute left-1/2 transform -translate-x-1/2 top-0 bottom-0"></div>
          
          <!-- Timeline Item 1 -->
          <div class="relative mb-16">
            <div class="timeline-dot absolute left-1/2 transform -translate-x-1/2"></div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
              <div class="md:text-right md:pr-12" data-aos="fade-right">
                <h4 class="text-xl font-bold mb-2">Senior Developer</h4>
                <p class="text-[var(--accent)] mb-2">2023 - Present</p>
                <p class="text-[var(--secondary-text)]">Tech Innovations Inc.</p>
              </div>
              <div class="md:pl-12" data-aos="fade-left">
                <p class="text-[var(--secondary-text)]">
                  Lead development on enterprise-level applications. Managed a team of 5 developers and implemented modern CI/CD practices.
                </p>
              </div>
            </div>
          </div>
          
          <!-- Timeline Item 2 -->
          <div class="relative mb-16">
            <div class="timeline-dot absolute left-1/2 transform -translate-x-1/2"></div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
              <div class="md:text-right md:pr-12" data-aos="fade-right">
                <h4 class="text-xl font-bold mb-2">Full-Stack Developer</h4>
                <p class="text-[var(--accent)] mb-2">2020 - 2023</p>
                <p class="text-[var(--secondary-text)]">WebSolutions Co.</p>
              </div>
              <div class="md:pl-12" data-aos="fade-left">
                <p class="text-[var(--secondary-text)]">
                  Developed and maintained multiple client projects. Focused on React, Node.js, and modern database solutions.
                </p>
              </div>
            </div>
          </div>
          
          <!-- Timeline Item 3 -->
          <div class="relative">
            <div class="timeline-dot absolute left-1/2 transform -translate-x-1/2"></div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
              <div class="md:text-right md:pr-12" data-aos="fade-right">
                <h4 class="text-xl font-bold mb-2">Junior Developer</h4>
                <p class="text-[var(--accent)] mb-2">2018 - 2020</p>
                <p class="text-[var(--secondary-text)]">StartUp Ventures</p>
              </div>
              <div class="md:pl-12" data-aos="fade-left">
                <p class="text-[var(--secondary-text)]">
                  Started my journey building responsive frontends and learning backend technologies. Collaborated in an agile team environment.
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Projects Section -->
  <section id="projects" class="section">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl md:text-4xl font-bold mb-12 text-center" data-aos="fade-up">
        My <span class="accent-text">Projects</span>
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <!-- Project Card 1 -->
        <div class="card p-6" data-aos="fade-up" data-aos-delay="100">
          <h3 class="text-xl font-bold mb-3">E-Commerce Platform</h3>
          <p class="text-[var(--secondary-text)] mb-4">
            A full-featured online shopping platform with product management, cart functionality, and payment processing.
          </p>
          <div class="flex space-x-2 mb-4">
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">React</span>
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">Node.js</span>
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">MongoDB</span>
          </div>
          <div class="flex space-x-3 mt-4">
            <a href="https://github.com/SayemSamir" class="px-4 py-2 bg-[var(--tertiary-bg)] hover:bg-opacity-80 rounded-md text-sm flex items-center transition-colors">
              <i class="fab fa-github mr-2"></i> Code
            </a>
            <a href="https://github.com/SayemSamir" class="px-4 py-2 bg-[var(--accent)] text-[var(--primary-bg)] hover:bg-opacity-90 rounded-md text-sm flex items-center transition-colors">
              <i class="fas fa-external-link-alt mr-2"></i> Live Demo
            </a>
          </div>
        </div>
        
        <!-- Project Card 2 -->
        <div class="card p-6" data-aos="fade-up" data-aos-delay="200">
          <h3 class="text-xl font-bold mb-3">Task Management App</h3>
          <p class="text-[var(--secondary-text)] mb-4">
            A productivity tool for organizing tasks with drag-and-drop functionality, due dates, and team collaboration features.
          </p>
          <div class="flex space-x-2 mb-4">
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">Vue.js</span>
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">Express</span>
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">PostgreSQL</span>
          </div>
          <div class="flex space-x-3 mt-4">
            <a href="https://github.com/SayemSamir" class="px-4 py-2 bg-[var(--tertiary-bg)] hover:bg-opacity-80 rounded-md text-sm flex items-center transition-colors">
              <i class="fab fa-github mr-2"></i> Code
            </a>
            <a href="https://github.com/SayemSamir" class="px-4 py-2 bg-[var(--accent)] text-[var(--primary-bg)] hover:bg-opacity-90 rounded-md text-sm flex items-center transition-colors">
              <i class="fas fa-external-link-alt mr-2"></i> Live Demo
            </a>
          </div>
        </div>
        
        <!-- Project Card 3 -->
        <div class="card p-6" data-aos="fade-up" data-aos-delay="300">
          <h3 class="text-xl font-bold mb-3">Weather Dashboard</h3>
          <p class="text-[var(--secondary-text)] mb-4">
            Real-time weather application with location-based forecasts, historical data analysis, and interactive maps.
          </p>
          <div class="flex space-x-2 mb-4">
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">React</span>
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">API Integration</span>
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">Chart.js</span>
          </div>
          <div class="flex space-x-3 mt-4">
            <a href="https://github.com/SayemSamir" class="px-4 py-2 bg-[var(--tertiary-bg)] hover:bg-opacity-80 rounded-md text-sm flex items-center transition-colors">
              <i class="fab fa-github mr-2"></i> Code
            </a>
            <a href="https://github.com/SayemSamir" class="px-4 py-2 bg-[var(--accent)] text-[var(--primary-bg)] hover:bg-opacity-90 rounded-md text-sm flex items-center transition-colors">
              <i class="fas fa-external-link-alt mr-2"></i> Live Demo
            </a>
          </div>
        </div>
        
        <!-- Project Card 4 -->
        <div class="card p-6" data-aos="fade-up" data-aos-delay="100">
          <h3 class="text-xl font-bold mb-3">Social Media Dashboard</h3>
          <p class="text-[var(--secondary-text)] mb-4">
            All-in-one dashboard for managing multiple social media accounts with analytics and scheduling capabilities.
          </p>
          <div class="flex space-x-2 mb-4">
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">Angular</span>
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">Firebase</span>
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">OAuth</span>
          </div>
          <div class="flex space-x-3 mt-4">
            <a href="https://github.com/SayemSamir" class="px-4 py-2 bg-[var(--tertiary-bg)] hover:bg-opacity-80 rounded-md text-sm flex items-center transition-colors">
              <i class="fab fa-github mr-2"></i> Code
            </a>
            <a href="https://github.com/SayemSamir" class="px-4 py-2 bg-[var(--accent)] text-[var(--primary-bg)] hover:bg-opacity-90 rounded-md text-sm flex items-center transition-colors">
              <i class="fas fa-external-link-alt mr-2"></i> Live Demo
            </a>
          </div>
        </div>
        
        <!-- Project Card 5 -->
        <div class="card p-6" data-aos="fade-up" data-aos-delay="200">
          <h3 class="text-xl font-bold mb-3">Fitness Tracker</h3>
          <p class="text-[var(--secondary-text)] mb-4">
            Personalized workout planning and progress tracking application with goal setting and achievement badges.
          </p>
          <div class="flex space-x-2 mb-4">
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">React Native</span>
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">GraphQL</span>
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">AWS</span>
          </div>
          <div class="flex space-x-3 mt-4">
            <a href="https://github.com/SayemSamir" class="px-4 py-2 bg-[var(--tertiary-bg)] hover:bg-opacity-80 rounded-md text-sm flex items-center transition-colors">
              <i class="fab fa-github mr-2"></i> Code
            </a>
            <a href="https://github.com/SayemSamir" class="px-4 py-2 bg-[var(--accent)] text-[var(--primary-bg)] hover:bg-opacity-90 rounded-md text-sm flex items-center transition-colors">
              <i class="fas fa-external-link-alt mr-2"></i> Live Demo
            </a>
          </div>
        </div>
        
        <!-- Project Card 6 -->
        <div class="card p-6" data-aos="fade-up" data-aos-delay="300">
          <h3 class="text-xl font-bold mb-3">Recipe Finder</h3>
          <p class="text-[var(--secondary-text)] mb-4">
            Discover recipes based on available ingredients, dietary restrictions, and cuisine preferences with step-by-step instructions.
          </p>
          <div class="flex space-x-2 mb-4">
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">Vue.js</span>
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">Node.js</span>
            <span class="px-2 py-1 bg-[var(--tertiary-bg)] text-xs rounded-md">MongoDB</span>
          </div>
          <div class="flex space-x-3 mt-4">
            <a href="https://github.com/SayemSamir" class="px-4 py-2 bg-[var(--tertiary-bg)] hover:bg-opacity-80 rounded-md text-sm flex items-center transition-colors">
              <i class="fab fa-github mr-2"></i> Code
            </a>
            <a href="https://github.com/SayemSamir" class="px-4 py-2 bg-[var(--accent)] text-[var(--primary-bg)] hover:bg-opacity-90 rounded-md text-sm flex items-center transition-colors">
              <i class="fas fa-external-link-alt mr-2"></i> Live Demo
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Blog Section -->
  <section id="blog" class="section bg-[var(--secondary-bg)]">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl md:text-4xl font-bold mb-12 text-center" data-aos="fade-up">
        Latest <span class="accent-text">Blog Posts</span>
      </h2>
      <div class="space-y-8">
        <!-- Blog Post 1 -->
        <div class="bg-[var(--primary-bg)] p-6 rounded-lg" data-aos="fade-up" data-aos-delay="100">
          <div class="flex flex-col md:flex-row gap-6">
            <div class="md:w-1/4">
              <img src="https://cdn.pixabay.com/photo/2016/11/19/14/00/code-1839406_960_720.jpg" alt="Blog post image" class="w-full h-40 object-cover rounded-lg">
            </div>
            <div class="md:w-3/4">
              <div class="flex items-center text-sm text-[var(--secondary-text)] mb-2">
                <i class="far fa-calendar-alt mr-2"></i> March 15, 2025
                <span class="mx-2">•</span>
                <i class="far fa-folder mr-2"></i> Web Development
              </div>
              <h3 class="text-xl font-bold mb-2">The Future of Frontend Development in 2025</h3>
              <p class="text-[var(--secondary-text)] mb-4 line-clamp-2">
                Exploring the latest trends and technologies that are shaping the future of frontend development. From AI-assisted coding to revolutionary new frameworks.
              </p>
              <a href="javascript:void(0)" class="text-[var(--accent)] hover:underline flex items-center">
                Read More <i class="fas fa-arrow-right ml-2"></i>
              </a>
            </div>
          </div>
        </div>
        
        <!-- Blog Post 2 -->
        <div class="bg-[var(--primary-bg)] p-6 rounded-lg" data-aos="fade-up" data-aos-delay="200">
          <div class="flex flex-col md:flex-row gap-6">
            <div class="md:w-1/4">
              <img src="https://cdn.pixabay.com/photo/2017/08/10/08/47/laptop-2620118_960_720.jpg" alt="Blog post image" class="w-full h-40 object-cover rounded-lg">
            </div>
            <div class="md:w-3/4">
              <div class="flex items-center text-sm text-[var(--secondary-text)] mb-2">
                <i class="far fa-calendar-alt mr-2"></i> February 28, 2025
                <span class="mx-2">•</span>
                <i class="far fa-folder mr-2"></i> Performance
              </div>
              <h3 class="text-xl font-bold mb-2">Optimizing Web Performance for Core Web Vitals</h3>
              <p class="text-[var(--secondary-text)] mb-4 line-clamp-2">
                A deep dive into strategies and techniques for optimizing your web application to achieve excellent Core Web Vitals scores and improve user experience.
              </p>
              <a href="javascript:void(0)" class="text-[var(--accent)] hover:underline flex items-center">
                Read More <i class="fas fa-arrow-right ml-2"></i>
              </a>
            </div>
          </div>
        </div>
        
        <!-- Blog Post 3 -->
        <div class="bg-[var(--primary-bg)] p-6 rounded-lg" data-aos="fade-up" data-aos-delay="300">
          <div class="flex flex-col md:flex-row gap-6">
            <div class="md:w-1/4">
              <img src="https://cdn.pixabay.com/photo/2015/09/09/21/37/monitor-933392_960_720.jpg" alt="Blog post image" class="w-full h-40 object-cover rounded-lg">
            </div>
            <div class="md:w-3/4">
              <div class="flex items-center text-sm text-[var(--secondary-text)] mb-2">
                <i class="far fa-calendar-alt mr-2"></i> January 10, 2025
                <span class="mx-2">•</span>
                <i class="far fa-folder mr-2"></i> Design
              </div>
              <h3 class="text-xl font-bold mb-2">Creating Accessible Web Interfaces</h3>
              <p class="text-[var(--secondary-text)] mb-4 line-clamp-2">
                How to design and develop websites that are accessible to all users, including those with disabilities. Best practices, tools, and techniques.
              </p>
              <a href="javascript:void(0)" class="text-[var(--accent)] hover:underline flex items-center">
                Read More <i class="fas fa-arrow-right ml-2"></i>
              </a>
            </div>
          </div>
        </div>
      </div>
      <div class="mt-10 text-center" data-aos="fade-up">
        <a href="javascript:void(0)" class="inline-block px-6 py-3 border border-[var(--accent)] text-[var(--accent)] rounded-md hover:bg-[var(--accent)] hover:bg-opacity-10 transition-all">
          View All Posts
        </a>
      </div>
    </div>
  </section>

  <!-- Skills Section -->
  <section id="skills" class="section">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl md:text-4xl font-bold mb-12 text-center" data-aos="fade-up">
        My <span class="accent-text">Skills</span>
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
        <!-- Technical Skills -->
        <div data-aos="fade-right">
          <h3 class="text-2xl font-bold mb-6">Technical Skills</h3>
          
          <!-- Skill Bar 1 -->
          <div class="mb-6">
            <div class="flex justify-between mb-2">
              <span>JavaScript / TypeScript</span>
              <span>95%</span>
            </div>
            <div class="skill-bar">
              <div class="skill-progress" style="width: 95%"></div>
            </div>
          </div>
          
          <!-- Skill Bar 2 -->
          <div class="mb-6">
            <div class="flex justify-between mb-2">
              <span>React & React Native</span>
              <span>90%</span>
            </div>
            <div class="skill-bar">
              <div class="skill-progress" style="width: 90%"></div>
            </div>
          </div>
          
          <!-- Skill Bar 3 -->
          <div class="mb-6">
            <div class="flex justify-between mb-2">
              <span>Node.js / Express</span>
              <span>85%</span>
            </div>
            <div class="skill-bar">
              <div class="skill-progress" style="width: 85%"></div>
            </div>
          </div>
          
          <!-- Skill Bar 4 -->
          <div class="mb-6">
            <div class="flex justify-between mb-2">
              <span>HTML5 & CSS3</span>
              <span>95%</span>
            </div>
            <div class="skill-bar">
              <div class="skill-progress" style="width: 95%"></div>
            </div>
          </div>
          
          <!-- Skill Bar 5 -->
          <div class="mb-6">
            <div class="flex justify-between mb-2">
              <span>Database Design</span>
              <span>80%</span>
            </div>
            <div class="skill-bar">
              <div class="skill-progress" style="width: 80%"></div>
            </div>
          </div>
          
          <!-- Skill Bar 6 -->
          <div class="mb-6">
            <div class="flex justify-between mb-2">
              <span>DevOps / CI/CD</span>
              <span>75%</span>
            </div>
            <div class="skill-bar">
              <div class="skill-progress" style="width: 75%"></div>
            </div>
          </div>
        </div>
        
        <!-- Tools & Technologies -->
        <div data-aos="fade-left">
          <h3 class="text-2xl font-bold mb-6">Tools & Technologies</h3>
          <div class="grid grid-cols-3 gap-4">
            <div class="flex flex-col items-center p-4 bg-[var(--secondary-bg)] rounded-lg">
              <i class="fab fa-react text-4xl mb-3 text-[var(--accent)]"></i>
              <span>React</span>
            </div>
            <div class="flex flex-col items-center p-4 bg-[var(--secondary-bg)] rounded-lg">
              <i class="fab fa-node-js text-4xl mb-3 text-[var(--accent)]"></i>
              <span>Node.js</span>
            </div>
            <div class="flex flex-col items-center p-4 bg-[var(--secondary-bg)] rounded-lg">
              <i class="fab fa-vuejs text-4xl mb-3 text-[var(--accent)]"></i>
              <span>Vue.js</span>
            </div>
            <div class="flex flex-col items-center p-4 bg-[var(--secondary-bg)] rounded-lg">
              <i class="fab fa-angular text-4xl mb-3 text-[var(--accent)]"></i>
              <span>Angular</span>
            </div>
            <div class="flex flex-col items-center p-4 bg-[var(--secondary-bg)] rounded-lg">
              <i class="fab fa-aws text-4xl mb-3 text-[var(--accent)]"></i>
              <span>AWS</span>
            </div>
            <div class="flex flex-col items-center p-4 bg-[var(--secondary-bg)] rounded-lg">
              <i class="fab fa-docker text-4xl mb-3 text-[var(--accent)]"></i>
              <span>Docker</span>
            </div>
            <div class="flex flex-col items-center p-4 bg-[var(--secondary-bg)] rounded-lg">
              <i class="fab fa-github text-4xl mb-3 text-[var(--accent)]"></i>
              <span>GitHub</span>
            </div>
            <div class="flex flex-col items-center p-4 bg-[var(--secondary-bg)] rounded-lg">
              <i class="fas fa-database text-4xl mb-3 text-[var(--accent)]"></i>
              <span>MongoDB</span>
            </div>
            <div class="flex flex-col items-center p-4 bg-[var(--secondary-bg)] rounded-lg">
              <i class="fab fa-sass text-4xl mb-3 text-[var(--accent)]"></i>
              <span>Sass</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
  
  <!-- Resume Section -->
  <section id="resume" class="section bg-[var(--secondary-bg)]">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl md:text-4xl font-bold mb-12 text-center" data-aos="fade-up">
        My <span class="accent-text">Resume</span>
      </h2>
      <div class="flex flex-col items-center" data-aos="zoom-in">
        <p class="text-lg text-center text-[var(--secondary-text)] max-w-2xl mb-8">
          Download my resume to learn more about my education, work experience, skills, and achievements. I'm always open to new opportunities and challenges.
        </p>
        <a href="javascript:void(0)" class="inline-flex items-center px-8 py-4 bg-[var(--accent)] text-[var(--primary-bg)] rounded-md hover:bg-opacity-90 transition-colors">
          <i class="fas fa-download mr-3"></i> Download Resume
        </a>
      </div>
      <div class="mt-20 grid grid-cols-1 md:grid-cols-2 gap-12">
        <!-- Education -->
        <div data-aos="fade-right">
          <h3 class="text-2xl font-bold mb-6 flex items-center">
            <i class="fas fa-graduation-cap text-[var(--accent)] mr-3"></i> Education
          </h3>
          <div class="space-y-8">
            <div class="bg-[var(--primary-bg)] p-6 rounded-lg">
              <h4 class="text-xl font-bold mb-1">Master of Computer Science</h4>
              <p class="text-[var(--accent)] mb-2">2016 - 2018</p>
              <p class="text-[var(--secondary-text)]">Stanford University</p>
              <p class="mt-3 text-[var(--secondary-text)]">
                Specialized in Software Engineering with a focus on web technologies and distributed systems.
              </p>
            </div>
            <div class="bg-[var(--primary-bg)] p-6 rounded-lg">
              <h4 class="text-xl font-bold mb-1">Bachelor of Science in Computer Science</h4>
              <p class="text-[var(--accent)] mb-2">2012 - 2016</p>
              <p class="text-[var(--secondary-text)]">University of California, Berkeley</p>
              <p class="mt-3 text-[var(--secondary-text)]">
                Graduated with honors. Coursework in algorithms, data structures, and web development.
              </p>
            </div>
          </div>
        </div>
        
        <!-- Certifications -->
        <div data-aos="fade-left">
          <h3 class="text-2xl font-bold mb-6 flex items-center">
            <i class="fas fa-certificate text-[var(--accent)] mr-3"></i> Certifications
          </h3>
          <div class="space-y-8">
            <div class="bg-[var(--primary-bg)] p-6 rounded-lg">
              <h4 class="text-xl font-bold mb-1">AWS Certified Solutions Architect</h4>
              <p class="text-[var(--accent)] mb-2">2023</p>
              <p class="text-[var(--secondary-text)]">Amazon Web Services</p>
              <p class="mt-3 text-[var(--secondary-text)]">
                Expertise in designing distributed applications and systems on the AWS platform.
              </p>
            </div>
            <div class="bg-[var(--primary-bg)] p-6 rounded-lg">
              <h4 class="text-xl font-bold mb-1">Professional Scrum Master</h4>
              <p class="text-[var(--accent)] mb-2">2022</p>
              <p class="text-[var(--secondary-text)]">Scrum.org</p>
              <p class="mt-3 text-[var(--secondary-text)]">
                Certified in agile project management methodologies and team leadership.
              </p>
            </div>
            <div class="bg-[var(--primary-bg)] p-6 rounded-lg">
              <h4 class="text-xl font-bold mb-1">Full-Stack Web Development</h4>
              <p class="text-[var(--accent)] mb-2">2021</p>
              <p class="text-[var(--secondary-text)]">Udacity</p>
              <p class="mt-3 text-[var(--secondary-text)]">
                Comprehensive program covering modern frontend and backend development technologies.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact Section -->
  <section id="contact" class="section">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl md:text-4xl font-bold mb-12 text-center" data-aos="fade-up">
        Get In <span class="accent-text">Touch</span>
      </h2>
      <div class="grid grid-cols-1 md:grid-cols-12 gap-12">
        <!-- Contact Info -->
        <div class="md:col-span-5" data-aos="fade-right">
          <h3 class="text-2xl font-bold mb-6">Let's Talk</h3>
          <p class="text-[var(--secondary-text)] mb-8">
            Have a project in mind or just want to say hello? Feel free to reach out to me. I'm always open to discussing new projects, creative ideas, or opportunities to be part of your vision.
          </p>
          <div class="space-y-4">
            <div class="flex items-start">
              <div class="bg-[var(--secondary-bg)] p-3 rounded-full mr-4">
                <i class="fas fa-map-marker-alt text-[var(--accent)]"></i>
              </div>
              <div>
                <h4 class="text-lg font-medium mb-1">Location</h4>
                <p class="text-[var(--secondary-text)]">Chattogram, Bangladesh</p>
              </div>
            </div>
            <div class="flex items-start">
              <div class="bg-[var(--secondary-bg)] p-3 rounded-full mr-4">
                <i class="fas fa-envelope text-[var(--accent)]"></i>
              </div>
              <div>
                <h4 class="text-lg font-medium mb-1">Email</h4>
                <p class="text-[var(--secondary-text)]">sayemuddinsamir00@gmail.com</p>
              </div>
            </div>
            <div class="flex items-start">
              <div class="bg-[var(--secondary-bg)] p-3 rounded-full mr-4">
                <i class="fas fa-phone text-[var(--accent)]"></i>
              </div>
              <div>
                <h4 class="text-lg font-medium mb-1">Phone</h4>
                <p class="text-[var(--secondary-text)]">+8801816612332</p>
              </div>
            </div>
          </div>
          
          <!-- Social Media Links -->
          <div class="mt-8">
            <h4 class="text-lg font-medium mb-4">Connect With Me</h4>
            <div class="flex space-x-4">
              <a href="https://www.linkedin.com/in/mdsayem197/" class="bg-[var(--secondary-bg)] hover:bg-[var(--tertiary-bg)] p-3 rounded-full transition-colors">
                <i class="fab fa-linkedin-in text-[var(--accent)]"></i>
              </a>
              <a href="https://github.com/SayemSamir" class="bg-[var(--secondary-bg)] hover:bg-[var(--tertiary-bg)] p-3 rounded-full transition-colors">
                <i class="fab fa-github text-[var(--accent)]"></i>
              </a>
              <a href="https://x.com/SamirSayem80470" class="bg-[var(--secondary-bg)] hover:bg-[var(--tertiary-bg)] p-3 rounded-full transition-colors">
                <i class="fab fa-twitter text-[var(--accent)]"></i>
              </a>
              <a href="javascript:void(0)" class="bg-[var(--secondary-bg)] hover:bg-[var(--tertiary-bg)] p-3 rounded-full transition-colors">
                <i class="fab fa-dribbble text-[var(--accent)]"></i>
              </a>
            </div>
          </div>
        </div>
        
        <!-- Contact Form -->
        <div class="md:col-span-7" data-aos="fade-left">
          <div class="bg-[var(--secondary-bg)] p-8 rounded-lg">
            <h3 class="text-2xl font-bold mb-6">Send Me a Message</h3>
            <form id="contact-form">
              <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                <div>
                  <label for="name" class="block mb-2 text-sm">Name</label>
                  <input type="text" id="name" name="name" class="form-input" placeholder="Your name" required>
                </div>
                <div>
                  <label for="email" class="block mb-2 text-sm">Email</label>
                  <input type="email" id="email" name="email" class="form-input" placeholder="Your email" required>
                </div>
              </div>
              <div class="mb-6">
                <label for="subject" class="block mb-2 text-sm">Subject</label>
                <input type="text" id="subject" name="subject" class="form-input" placeholder="Subject" required>
              </div>
              <div class="mb-6">
                <label for="message" class="block mb-2 text-sm">Message</label>
                <textarea id="message" name="message" rows="5" class="form-input" placeholder="Your message" required></textarea>
              </div>
              
              <!-- Form Response Message -->
              <div id="form-response" class="mb-6 hidden">
                <p class="text-green-500"><i class="fas fa-check-circle mr-2"></i> <span id="response-message"></span></p>
              </div>
              
              <button type="submit" class="w-full py-3 bg-[var(--accent)] text-[var(--primary-bg)] rounded-md hover:bg-opacity-90 transition-colors flex justify-center items-center">
                <span id="submit-text">Send Message</span>
                <span id="submit-loader" class="hidden"><i class="fas fa-circle-notch fa-spin"></i></span>
              </button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="bg-[var(--secondary-bg)] py-8">
    <div class="container mx-auto px-4">
      <div class="flex flex-col md:flex-row justify-between items-center">
        <div class="mb-4 md:mb-0">
          <span class="text-lg font-bold">Sayem Uddin Samir</span>
          <p class="text-[var(--secondary-text)]">© 2025 | All Rights Reserved</p>
        </div>
        <div class="flex space-x-4">
          <a href="https://www.linkedin.com/in/mdsayem197/" class="hover:text-[var(--accent)] transition-colors">
            <i class="fab fa-linkedin-in"></i>
          </a>
          <a href="https://github.com/SayemSamir" class="hover:text-[var(--accent)] transition-colors">
            <i class="fab fa-github"></i>
          </a>
          <a href="https://x.com/SamirSayem80470" class="hover:text-[var(--accent)] transition-colors">
            <i class="fab fa-twitter"></i>
          </a>
          <a href="javascript:void(0)" class="hover:text-[var(--accent)] transition-colors">
            <i class="fab fa-dribbble"></i>
          </a>
        </div>
      </div>
    </div>
  </footer>
  <div id="scroll-progress" class="fixed top-0 left-0 h-1 bg-[var(--accent)] z-50"></div>
  <!-- Back to top button -->
  <button id="back-to-top" class="fixed bottom-6 right-6 p-3 rounded-full bg-[var(--accent)] text-[var(--primary-bg)] hidden">
    <i class="fas fa-arrow-up"></i>
  </button>
<!-- Floating Action Button -->
<button id="fab" class="fixed bottom-6 right-24 z-50 w-14 h-14 bg-[var(--accent)] text-[var(--primary-bg)] rounded-full shadow-lg flex items-center justify-center hover:scale-110 transition-transform">
  <i class="fas fa-paper-plane text-xl"></i>
</button>
<!-- Add at the top of your body -->
<div id="scroll-progress" class="fixed top-0 left-0 h-1 bg-[var(--accent)] z-50"></div>
  <script src="https://unpkg.com/aos@next/dist/aos.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js"></script>
  <script id="app-script">
    // Initialize AOS
    AOS.init({
      duration: 800,
      once: true,
    });

    // Mobile Menu Toggle
    const menuToggle = document.getElementById('menu-toggle');
    const mobileMenu = document.getElementById('mobile-menu');

    menuToggle.addEventListener('click', () => {
      mobileMenu.classList.toggle('active');
      const icon = menuToggle.querySelector('i');
      if (mobileMenu.classList.contains('active')) {
        icon.classList.remove('fa-bars');
        icon.classList.add('fa-times');
      } else {
        icon.classList.remove('fa-times');
        icon.classList.add('fa-bars');
      }
    });

    // Back to top button
    const backToTopButton = document.getElementById('back-to-top');
    
    window.addEventListener('scroll', () => {
      if (window.pageYOffset > 300) {
        backToTopButton.classList.remove('hidden');
      } else {
        backToTopButton.classList.add('hidden');
      }
    });
    
    backToTopButton.addEventListener('click', () => {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    });

    // Initialize Particles.js for hero background
    if (typeof particlesJS !== 'undefined') {
      particlesJS('particles-js', {
        "particles": {
          "number": {
            "value": 80,
            "density": {
              "enable": true,
              "value_area": 800
            }
          },
          "color": {
            "value": "#64ffda"
          },
          "shape": {
            "type": "circle",
            "stroke": {
              "width": 0,
              "color": "#000000"
            }
          },
          "opacity": {
            "value": 0.3,
            "random": false,
            "anim": {
              "enable": false,
              "speed": 1,
              "opacity_min": 0.1,
              "sync": false
            }
          },
          "size": {
            "value": 3,
            "random": true,
            "anim": {
              "enable": false,
              "speed": 40,
              "size_min": 0.1,
              "sync": false
            }
          },
          "line_linked": {
            "enable": true,
            "distance": 150,
            "color": "#64ffda",
            "opacity": 0.2,
            "width": 1
          },
          "move": {
            "enable": true,
            "speed": 2,
            "direction": "none",
            "random": false,
            "straight": false,
            "out_mode": "out",
            "bounce": false,
            "attract": {
              "enable": false,
              "rotateX": 600,
              "rotateY": 1200
            }
          }
        },
        "interactivity": {
          "detect_on": "canvas",
          "events": {
            "onhover": {
              "enable": true,
              "mode": "grab"
            },
            "onclick": {
              "enable": true,
              "mode": "push"
            },
            "resize": true
          },
          "modes": {
            "grab": {
              "distance": 140,
              "line_linked": {
                "opacity": 1
              }
            },
            "push": {
              "particles_nb": 4
            }
          }
        },
        "retina_detect": true
      });
    }

    // Navbar active state based on scroll position
    const sections = document.querySelectorAll('.section');
    const navLinks = document.querySelectorAll('nav a');

    function setActiveNavLink() {
      let current = '';
      sections.forEach(section => {
        const sectionTop = section.offsetTop;
        const sectionHeight = section.clientHeight;
        if (window.pageYOffset >= sectionTop - 200) {
          current = section.getAttribute('id');
        }
      });

      navLinks.forEach(link => {
        link.classList.remove('navbar-active');
        if (link.getAttribute('href') === `#${current}`) {
          link.classList.add('navbar-active');
        }
      });
    }

    window.addEventListener('scroll', setActiveNavLink);
    window.addEventListener('load', setActiveNavLink);

    // Form submission handling
    const contactForm = document.getElementById('contact-form');
    const formResponse = document.getElementById('form-response');
    const responseMessage = document.getElementById('response-message');
    const submitText = document.getElementById('submit-text');
    const submitLoader = document.getElementById('submit-loader');

    contactForm.addEventListener('submit', (e) => {
      e.preventDefault();
      
      // Show loading state
      submitText.classList.add('hidden');
      submitLoader.classList.remove('hidden');
      
      // Simulate form submission (would be replaced with actual API call)
      setTimeout(() => {
        // Hide loading state
        submitText.classList.remove('hidden');
        submitLoader.classList.add('hidden');
        
        // Show success message
        formResponse.classList.remove('hidden');
        responseMessage.textContent = "Your message has been sent successfully. I'll get back to you soon!";
        
        // Reset form
        contactForm.reset();
        
        // Hide message after 5 seconds
        setTimeout(() => {
          formResponse.classList.add('hidden');
        }, 5000);
      }, 1500);
    });
    // Floating Action Button
const fab = document.getElementById('fab');
fab.addEventListener('click', () => {
  window.location.href = '#contact';
});
// Theme Toggle
const themeToggle = document.getElementById('theme-toggle');
const moonIcon = themeToggle.querySelector('.fa-moon');
const sunIcon = themeToggle.querySelector('.fa-sun');

themeToggle.addEventListener('click', () => {
  document.body.classList.toggle('light-theme');
  moonIcon.classList.toggle('hidden');
  sunIcon.classList.toggle('hidden');
  
  // Save preference to localStorage
  const isLight = document.body.classList.contains('light-theme');
  localStorage.setItem('lightTheme', isLight);
});

// Check for saved theme preference
if (localStorage.getItem('lightTheme') === 'true') {
  document.body.classList.add('light-theme');
  moonIcon.classList.add('hidden');
  sunIcon.classList.remove('hidden');
}
// Scroll Progress Indicator
const scrollProgress = document.getElementById('scroll-progress');
window.addEventListener('scroll', () => {
  const scrollHeight = document.documentElement.scrollHeight - window.innerHeight;
  const scrolled = (window.scrollY / scrollHeight) * 100;
  scrollProgress.style.width = `${scrolled}%`;
});
  </script>
</body>
</html>
