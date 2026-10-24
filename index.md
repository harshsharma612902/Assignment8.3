The HTML File (index.html)
HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The Tech Chronicle — Magazine Layout</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Step 2: Outer Grid Container -->
    <div class="magazine-grid">
        
        <!-- Step 1 & 4: Header Section -->
        <header class="header-area">
            <div class="brand">
                <span class="edition">Global Edition</span>
                <h1>THE TECH CHRONICLE</h1>
            </div>
        </header>

        <!-- Step 1 & 4: Navigation Section -->
        <nav class="nav-area">
            <ul>
                <li><a href="#top" class="active">Top Stories</a></li>
                <li><a href="#tech">AI & Tech</a></li>
                <li><a href="#design">Design</a></li>
                <li><a href="#culture">Culture</a></li>
                <li><a href="#opinion">Opinion</a></li>
            </ul>
        </nav>

        <!-- Steps 1, 4, & 5: Main Article (Gets maximum space) -->
        <main class="main-article-area">
            <span class="category-tag">Featured Story</span>
            <h2>The Horizon of Artificial Intelligence in Modern Web Architecture</h2>
            <p class="byline">By Elena Rostova | Published October 2026</p>
            
            <img src="https://images.unsplash.com/photo-1451187580459-43490279c0fa?auto=format&fit=crop&q=80&w=800" alt="Futuristic Network Graphic" class="featured-img">

            <p class="lead-p">
                As web development evolves, layout engines and generative tools are converging to create hyper-dynamic user interfaces. The modern web is no longer just about static responsiveness—it is about real-time adaptability.
            </p>
            <p>
                CSS Grid has redefined how editorial content is consumed online. By allowing developers to declare intent-based visual areas, digital journalism can mirror the rich typography and artful structure of classic print magazines without compromising mobile usability.
            </p>
        </main>

        <!-- Steps 1 & 4: Sidebar Section -->
        <aside class="sidebar-area">
            <h3>Trending Headlines</h3>
            
            <div class="sidebar-item">
                <span class="trending-num">01</span>
                <div>
                    <h4>CSS Grid vs. Flexbox in 2026</h4>
                    <p>When to combine both for high-density dashboard UI design.</p>
                </div>
            </div>

            <div class="sidebar-item">
                <span class="trending-num">02</span>
                <div>
                    <h4>The Renaissance of Editorial Web Design</h4>
                    <p>Why digital publications are embracing bold typography grids.</p>
                </div>
            </div>

            <div class="sidebar-item">
                <span class="trending-num">03</span>
                <div>
                    <h4>Subgrid Essentials</h4>
                    <p>Mastering nested element alignment across multi-column layouts.</p>
                </div>
            </div>
        </aside>

        <!-- Step 1 & 4: Footer Section -->
        <footer class="footer-area">
            <p>&copy; 2026 The Tech Chronicle Publishing House. All rights reserved.</p>
        </footer>

    </div>

</body>
</html>
2. The CSS File (style.css)
CSS
/* Global Reset & Typography */
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: 'Georgia', serif;
    background-color: #fcfbf9;
    color: #1a1a1a;
    line-height: 1.6;
    padding: 20px;
}

/* Steps 2, 3, & 5: CSS Grid Container with Named Areas */
.magazine-grid {
    max-width: 1100px;
    margin: 0 auto;
    display: grid;
    
    /* Step 5: Column ratio 2.5fr (Main) vs 1fr (Sidebar) gives main article majority space */
    grid-template-columns: 2.5fr 1fr;
    grid-template-rows: auto auto 1fr auto;
    
    /* Step 3: Layout definition using grid-template-areas */
    grid-template-areas: 
        "header  header"
        "nav     nav"
        "main    sidebar"
        "footer  footer";
        
    gap: 30px;
    background-color: #ffffff;
    padding: 30px;
    border: 1px solid #e0ddd7;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.03);
}

/* Step 4: Assign Named Grid Areas */

/* HEADER AREA */
.header-area {
    grid-area: header;
    text-align: center;
    border-bottom: 3px double #1a1a1a;
    padding-bottom: 20px;
}

.header-area .edition {
    font-family: sans-serif;
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 2px;
    color: #666666;
}

.header-area h1 {
    font-size: 3rem;
    font-weight: 900;
    letter-spacing: -1px;
    margin-top: 5px;
}

/* NAVIGATION AREA */
.nav-area {
    grid-area: nav;
    border-bottom: 1px solid #1a1a1a;
    padding-bottom: 10px;
}

.nav-area ul {
    list-style: none;
    display: flex;
    justify-content: center;
    gap: 30px;
    font-family: sans-serif;
    font-size: 0.85rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.nav-area a {
    text-decoration: none;
    color: #444444;
    transition: color 0.2s;
}

.nav-area a:hover, .nav-area a.active {
    color: #e63946;
}

/* MAIN ARTICLE AREA */
.main-article-area {
    grid-area: main;
    border-right: 1px solid #eee;
    padding-right: 30px;
}

.category-tag {
    font-family: sans-serif;
    background-color: #e63946;
    color: white;
    font-size: 0.7rem;
    font-weight: bold;
    text-transform: uppercase;
    padding: 3px 8px;
    letter-spacing: 1px;
}

.main-article-area h2 {
    font-size: 2rem;
    margin: 12px 0 6px 0;
    line-height: 1.25;
}

.byline {
    font-family: sans-serif;
    font-size: 0.8rem;
    color: #777;
    margin-bottom: 20px;
}

.featured-img {
    width: 100%;
    height: 320px;
    object-fit: cover;
    margin-bottom: 20px;
    border-radius: 4px;
}

.lead-p {
    font-size: 1.15rem;
    font-weight: bold;
    color: #222222;
    margin-bottom: 15px;
}

.main-article-area p {
    margin-bottom: 15px;
}

/* SIDEBAR AREA */
.sidebar-area {
    grid-area: sidebar;
    font-family: sans-serif;
}

.sidebar-area h3 {
    font-size: 1rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    border-bottom: 2px solid #1a1a1a;
    padding-bottom: 8px;
    margin-bottom: 20px;
}

.sidebar-item {
    display: flex;
    gap: 15px;
    margin-bottom: 20px;
    padding-bottom: 15px;
    border-bottom: 1px solid #f0f0f0;
}

.trending-num {
    font-size: 1.5rem;
    font-weight: 900;
    color: #e63946;
}

.sidebar-item h4 {
    font-size: 0.95rem;
    margin-bottom: 4px;
    line-height: 1.3;
}

.sidebar-item p {
    font-size: 0.8rem;
    color: #666;
}

/* FOOTER AREA */
.footer-area {
    grid-area: footer;
    border-top: 1px solid #1a1a1a;
    padding-top: 20px;
    text-align: center;
    font-family: sans-serif;
    font-size: 0.8rem;
    color: #666;
}

/* Step 6: Responsive check media query for stacked viewports */
@media (max-width: 768px) {
    .magazine-grid {
        grid-template-columns: 1fr;
        grid-template-areas: 
            "header"
            "nav"
            "main"
            "sidebar"
            "footer";
    }
    
    .main-article-area {
        border-right: none;
        padding-right: 0;
    }
}