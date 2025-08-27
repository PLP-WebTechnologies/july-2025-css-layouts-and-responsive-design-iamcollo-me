<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CSS Layouts & Responsive Web Design</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <header>
    <h1>CSS Layouts & Responsive Web Design</h1>
    <nav>
      <ul class="nav-list">
        <li><a href="#home">Home</a></li>
        <li><a href="#features">Features</a></li>
        <li><a href="#about">About</a></li>
      </ul>
    </nav>
  </header>

  <div class="container">
    <aside class="sidebar">
      <h2>Sidebar</h2>
      <ul>
        <li>Layout tips</li>
        <li>Responsive units</li>
        <li>Media queries</li>
      </ul>
    </aside>
    <main class="main-content">
      <section id="home">
        <h2>Welcome</h2>
        <p>
          This page showcases modern CSS layout techniques using Flexbox and Grid, along with responsive web design principles.
        </p>
      </section>
      <section id="features" class="features-grid">
        <div class="feature-card">
          <h3>Flexbox</h3>
          <p>Great for 1D layouts—align, justify, and reorder items in rows or columns.</p>
        </div>
        <div class="feature-card">
          <h3>CSS Grid</h3>
          <p>Perfect for 2D layouts—build complex grids of rows and columns.</p>
        </div>
        <div class="feature-card">
          <h3>Responsive Design</h3>
          <p>Use media queries and flexible units to adapt your layout to any device.</p>
        </div>
      </section>
      <section id="about">
        <h2>About This Assignment</h2>
        <p>
          You are using both Flexbox and Grid to create a layout that looks great on desktop, tablet, and mobile screens.
        </p>
      </section>
    </main>
  </div>

  <footer>
    <p>&copy; 2025 CSS Layouts Assignment</p>
  </footer>
</body>
</html>/* Base styles and variables */
:root {
  --primary: #3a6ea5;
  --secondary: #f6f8fa;
  --accent: #e2eafc;
  --sidebar: #d9e8f6;
  --card: #f9fafb;
  --radius: 8px;
  --shadow: 0 2px 8px rgba(58,110,165,0.08);
}

*,
*::before,
*::after {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: 'Segoe UI', Arial, sans-serif;
  background: var(--secondary);
  color: #222;
  line-height: 1.6;
}

/* Header with Flexbox for nav alignment */
header {
  background: var(--primary);
  color: #fff;
  padding: 1.5rem 1rem 1rem 1rem;
  border-bottom-left-radius: var(--radius);
  border-bottom-right-radius: var(--radius);
  box-shadow: var(--shadow);
}

header h1 {
  margin: 0 0 0.5rem 0;
  font-size: 2rem;
}

nav {
  display: flex;
  justify-content: flex-end;
}

.nav-list {
  display: flex;
  gap: 2rem;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-list a {
  color: #fff;
  text-decoration: none;
  font-weight: 500;
  font-size: 1.1rem;
  padding: 0.5rem 1rem;
  border-radius: var(--radius);
  transition: background 0.2s;
}

.nav-list a:hover {
  background: var(--accent);
  color: var(--primary);
}

/* Main layout with CSS Grid */
.container {
  display: grid;
  grid-template-columns: 220px 1fr;
  gap: 2rem;
  max-width: 1080px;
  margin: 2rem auto;
  padding: 0 1rem;
}

/* Sidebar styling */
.sidebar {
  background: var(--sidebar);
  border-radius: var(--radius);
  box-shadow: var(--shadow);
  padding: 1.5rem 1rem;
  min-width: 180px;
}

.sidebar h2 {
  margin-top: 0;
  font-size: 1.3rem;
  color: var(--primary);
}

.sidebar ul {
  padding-left: 1.2rem;
}

.sidebar li {
  margin-bottom: 0.7rem;
}

/* Main content area */
.main-content {
  background: var(--card);
  border-radius: var(--radius);
  box-shadow: var(--shadow);
  padding: 2rem 1.5rem;
}

.main-content h2 {
  color: var(--primary);
  margin-top: 0;
}

/* Features section with Flexbox cards */
.features-grid {
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
  margin: 2rem 0;
}

.feature-card {
  background: var(--accent);
  border-radius: var(--radius);
  box-shadow: var(--shadow);
  flex: 1 1 220px;
  min-width: 220px;
  max-width: 320px;
  padding: 1rem;
  margin-bottom: 1.2rem;
}

.feature-card h3 {
  margin-top: 0;
  color: var(--primary);
}

/* Footer */
footer {
  background: var(--primary);
  color: #fff;
  text-align: center;
  padding: 1rem;
  border-top-left-radius: var(--radius);
  border-top-right-radius: var(--radius);
  margin-top: 2rem;
}

/* Responsive Design */
/* Tablet layout */
@media (max-width: 900px) {
  .container {
    grid-template-columns: 170px 1fr;
    gap: 1rem;
  }
  .main-content {
    padding: 1.2rem 1rem;
  }
  .features-grid {
    gap: 1rem;
  }
}

/* Mobile layout */
@media (max-width: 600px) {
  .container {
    grid-template-columns: 1fr;
    gap: 0;
  }
  .sidebar {
    display: none; /* Hide sidebar on mobile */
  }
  .main-content {
    padding: 1rem 0.5rem;
  }
  .features-grid {
    flex-direction: column;
    gap: 1rem;
  }
  .feature-card {
    max-width: 100%;
    min-width: 0;
  }
  header {
    padding: 1rem 0.5rem;
    border-radius: 0;
  }
  footer {
    border-radius: 0;
  }
}

/* Utility for accessibility and best practices */
a:focus {
  outline: 2px dashed var(--primary);
  outline-offset: 2px;
}

/* Comments:
  - Flexbox is used for nav and feature cards
  - Grid is used for main page layout (sidebar + main content)
  - Media queries adjust layout for tablet/mobile
  - Responsive units (rem, %, etc.) are used throughout
*/