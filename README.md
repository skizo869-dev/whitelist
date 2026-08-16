
   <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blackout City - Applications</title>
    <style>
        :root {
            --bg-dark: #07080a;
            --card-bg: #111316;
            --text-main: #ffffff;
            --text-muted: #8b949e;
            --accent-red: #e71d36;
            --border-color: #21262d;
            --font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: var(--bg-dark);
            color: var(--text-main);
            font-family: var(--font-family);
            background-image: 
                linear-gradient(to bottom, rgba(7, 8, 10, 0.90), rgba(7, 8, 10, 0.98)),
                url('https://i.imgur.com/q1jX18g.png');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            overflow-x: hidden;
        }

        /* --- Navbar --- */
        .navbar {
            background-color: rgba(11, 13, 16, 0.95);
            border-bottom: 1px solid var(--border-color);
            padding: 15px 30px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            width: 100%;
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .nav-brand {
            font-weight: 900;
            font-size: 18px;
            letter-spacing: 1px;
            color: var(--text-main);
            text-decoration: none;
        }

        .nav-links {
            display: flex;
            gap: 25px;
            list-style: none;
        }

        .navbar a {
            text-decoration: none;
            color: var(--text-muted);
            font-weight: 600;
            font-size: 13px;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: color 0.3s ease;
        }

        .navbar a:hover, .navbar a.active {
            color: var(--text-main);
        }

        /* --- Main Header --- */
        .main-header {
            text-align: center;
            padding: 40px 20px 20px;
            max-width: 900px;
            margin: 0 auto;
        }

        .main-header h1 {
            font-size: 38px;
            font-weight: 900;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 10px;
            color: var(--text-main);
        }

        .main-header h1 span {
            color: var(--accent-red);
        }

        .main-header p {
            color: var(--text-muted);
            font-size: 13px;
            letter-spacing: 1px;
            text-transform: uppercase;
        }

        /* --- Cards Container --- */
        .cards-container {
            max-width: 1200px;
            width: 100%;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 20px;
            padding: 20px;
            flex-grow: 1;
            align-content: center;
        }

        .app-card {
            background: linear-gradient(135deg, rgba(17, 19, 22, 0.95), rgba(11, 13, 16, 0.98));
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 30px 20px;
            text-decoration: none;
            color: var(--text-main);
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            position: relative;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.4);
        }

        .app-card:hover {
            transform: translateY(-4px);
            border-color: var(--accent-red);
            box-shadow: 0 10px 25px rgba(231, 29, 54, 0.2);
        }

        .app-card h3 {
            font-size: 20px;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 8px;
        }

        .app-card p {
            color: var(--text-muted);
            font-size: 12px;
            line-height: 1.4;
        }

        /* --- Responsive Design --- */
        @media (max-width: 768px) {
            .navbar {
                padding: 12px 15px;
                flex-direction: column;
                gap: 10px;
            }
            .nav-links {
                gap: 15px;
            }
            .main-header h1 {
                font-size: 26px;
            }
            .cards-container {
                grid-template-columns: 1fr;
                padding: 15px;
            }
        }
    </style>
</head>
<body>

    <!-- Top Navigation Bar -->
    <nav class="navbar">
        <a href="#" class="nav-brand">BLACKOUT CITY</a>
        <div class="nav-links">
            <a href="#">Home</a>
            <a href="#">Events</a>
            <a href="#">Rules</a>
            <a href="#" class="active">Applications</a>
            <a href="#">Team</a>
        </div>
    </nav>

    <!-- Main Header Section -->
    <header class="main-header">
        <h1>Blackout City <span>Applications</span></h1>
        <p>Select a department to submit your official application directly to the staff team</p>
    </header>

    <!-- Applications Cards Grid -->
    <div class="cards-container">
        <a href="whitelist.html" class="app-card">
            <h3>Whitelist (Citizen)</h3>
            <p>Become an official citizen of Blackout City.</p>
        </a>

        <a href="police.html" class="app-card">
            <h3>Police Department</h3>
            <p>Enforce the law and protect the streets.</p>
        </a>

        <a href="ems.html" class="app-card">
            <h3>EMS Department</h3>
            <p>Save lives and provide emergency medical services.</p>
        </a>

        <a href="gang.html" class="app-card">
            <h3>Gang & Family</h3>
            <p>Establish your faction or family legacy.</p>
        </a>
    </div>

</body>
</html>
