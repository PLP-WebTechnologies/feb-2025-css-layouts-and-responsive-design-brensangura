<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Layout</title>
    <style>
        /* Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }
        
        body {
            line-height: 1.6;
            color: #333;
        }
        
        /* Navigation Bar - Flexbox */
        nav {
            background-color: #2c3e50;
            padding: 1rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .logo {
            color: white;
            font-size: 1.5rem;
            font-weight: bold;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 1.5rem;
        }
        
        .nav-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .nav-links a:hover {
            color: #3498db;
        }
        
        /* Main Content - Grid */
        .container {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1.5rem;
            padding: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .card {
            background: #f9f9f9;
            border-radius: 8px;
            padding: 1.5rem;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .card h2 {
            margin-bottom: 1rem;
            color: #2c3e50;
        }
        
        /* Footer */
        footer {
            background-color: #2c3e50;
            color: white;
            text-align: center;
            padding: 1.5rem;
            margin-top: 2rem;
        }
        
        /* Media Queries for Responsiveness */
        /* Tablet */
        @media (min-width: 768px) {
            .container {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .nav-links {
                gap: 1rem;
            }
        }
        
        /* Desktop */
        @media (min-width: 1024px) {
            .container {
                grid-template-columns: repeat(3, 1fr);
            }
            
            .nav-links {
                gap: 2rem;
            }
            
            .header {
                padding: 2rem;
            }
        }
        
        /* Mobile - Hamburger Menu */
        @media (max-width: 600px) {
            .nav-links {
                display: none;
                flex-direction: column;
                width: 100%;
                position: absolute;
                top: 60px;
                left: 0;
                background-color: #2c3e50;
                padding: 1rem;
            }
            
            .nav-links.active {
                display: flex;
            }
            
            .nav-links li {
                margin: 0.5rem 0;
            }
            
            .hamburger {
                display: block;
                cursor: pointer;
                color: white;
                font-size: 1.5rem;
            }
            
            .hamburger.active {
                transform: rotate(90deg);
            }
        }
        
        .hamburger {
            display: none;
        }
    </style>
</head>
<body>
    <nav>
        <div class="logo">MySite</div>
        <div class="hamburger">☰</div>
        <ul class="nav-links">
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Services</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </nav>
    
    <div class="container">
        <div class="card">
            <h2>Card 1</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam in dui mauris.</p>
        </div>
        <div class="card">
            <h2>Card 2</h2>
            <p>Vivamus luctus urna sed urna ultricies ac tempor dui sagittis.</p>
        </div>
        <div class="card">
            <h2>Card 3</h2>
            <p>In condimentum facilisis porta. Sed nec diam eu diam mattis viverra.</p>
        </div>
        <div class="card">
            <h2>Card 4</h2>
            <p>Fusce quam. Maecenas fermentum consequat mi. Donec fermentum.</p>
        </div>
        <div class="card">
            <h2>Card 5</h2>
            <p>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas.</p>
        </div>
        <div class="card">
            <h2>Card 6</h2>
            <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
        </div>
    </div>
    
    <footer>
        <p>&copy; 2023 MySite. All rights reserved.</p>
    </footer>

    <script>
        // Hamburger menu toggle for mobile
        const hamburger = document.querySelector('.hamburger');
        const navLinks = document.querySelector('.nav-links');
        
        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            hamburger.classList.toggle('active');
        });
    </script>
</body>
</html>
