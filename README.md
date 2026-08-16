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
            background-attachment: fixed;
            min-height: 100vh;
            padding-bottom: 60px;
        }

        /* --- Navbar --- */
        .navbar {
            background-color: rgba(11, 13, 16, 0.95);
            border-bottom: 1px solid var(--border-color);
            padding: 15px 40px;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 35px;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.6);
        }

        .nav-logo {
            height: 45px;
            margin: 0 20px;
            object-fit: contain;
        }

        .navbar a {
            text-decoration: none;
            color: var(--text-muted);
            font-weight: 600;
            font-size: 13px;
            text-transform: uppercase;
            letter-spacing: 2px;
            transition: color 0.3s ease;
            position: relative;
        }

        .navbar a:hover {
            color: var(--text-main);
        }

        .navbar a.active {
            color: var(--text-main);
            font-weight: 700;
        }

        .navbar a.active::after {
            content: '';
            position: absolute;
            bottom: -6px;
            left: 0;
            width: 100%;
            height: 2px;
            background-color: var(--accent-red);
        }

        /* --- Main Header --- */
        .main-header {
            text-align: center;
            padding: 60px 20px 40px;
        }

        .main-header h1 {
            font-size: 48px;
            font-weight: 900;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 12px;
            color: var(--text-main);
        }

        .main-header h1 span {
            color: var(--accent-red);
        }

        .main-header p {
            color: var(--text-muted);
            font-size: 14px;
            max-width: 600px;
            margin: 0 auto;
            letter-spacing: 1.5px;
            text-transform: uppercase;
        }

        /* --- Cards Container --- */
        .cards-container {
            max-width: 1050px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 25px;
            padding: 0 20px;
        }

        .app-card {
            background: linear-gradient(135deg, rgba(17, 19, 22, 0.9), rgba(11, 13, 16, 0.95));
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 50px 30px;
            text-decoration: none;
            color: var(--text-main);
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            position: relative;
            overflow: hidden;
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.4);
        }

        .app-card:hover {
            transform: translateY(-4px);
            border-color: #30363d;
            box-shadow: 0 12px 35px rgba(0, 0, 0, 0.6);
        }

        .app-card::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background-color: var(--accent-red);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .app-card:hover::after {
            transform: scaleX(1);
        }

        .app-card h3 {
            font-size: 28px;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            margin: 0;
        }

        /* --- Responsive Design --- */
        @media (max-width: 768px) {
            .navbar {
                padding: 15px 10px;
                gap: 15px;
                flex-wrap: wrap;
            }
            .nav-logo {
                height: 35px;
                order: -1;
                width: 100%;
            }
            .navbar a {
                font-size: 11px;
                letter-spacing: 1px;
            }
            .main-header h1 {
                font-size: 32px;
            }
            .cards-container {
                grid-template-columns: 1fr;
            }
            .app-card {
                padding: 35px 20px;
            }
            .app-card h3 {
                font-size: 22px;
            }
        }
    </style>
</head>
<body>

    <!-- Top Navigation Bar -->
    <nav class="navbar">
        <a href="#">Home</a>
        <a href="#">Events</a>
        <img src="https://i.imgur.com/rX97K2X.png" alt="Blackout City Logo" class="nav-logo">
        <a href="#">Rules</a>
        <a href="#" class="active">Applications</a>
        <a href="#">Team</a>
    </nav>

    <!-- Main Header Section -->
    <header class="main-header">
        <h1>Blackout City <span>Applications</span></h1>
        <p>Select a department to submit your official application</p>
    </header>

    <!-- Applications Cards Grid -->
    <div class="cards-container">
        <a href="whitelist.html" class="app-card">
            <h3>Whitelist (Citizen)</h3>
        </a>

        <a href="police.html" class="app-card">
            <h3>Police Department</h3>
        </a>

        <a href="ems.html" class="app-card">
            <h3>EMS Department</h3>
        </a>

        <a href="gang.html" class="app-card">
            <h3>Gang & Family</h3>
        </a>
    </div>

</body>
</html>
