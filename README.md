<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Blackout City - Applications</title>
    <style>
        /* --- CSS Variables & Reset --- */
        :root {
            --bg-dark: #07080a;
            --card-bg: #111316;
            --text-main: #ffffff;
            --text-muted: #8b949e;
            --accent-red: #e71d36; /* Primary red from logo */
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
            /* Dark city skyline background */
            background-image: 
                linear-gradient(to bottom, rgba(7, 8, 10, 0.95), rgba(7, 8, 10, 1)),
                url('https://i.imgur.com/q1jX18g.png'); /* Replace with your background image */
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            background-attachment: fixed;
            min-height: 100vh;
            padding-bottom: 60px;
        }

        /* --- Top Navigation Bar --- */
        .navbar {
            background-color: rgba(17, 19, 22, 0.95);
            border-bottom: 1px solid var(--border-color);
            padding: 20px 50px;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 45px;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 20px rgba(0, 0, 0, 0.5);
        }

        .nav-logo {
            height: 35px; /* Adjusted logo height */
            filter: brightness(0) invert(1); /* Ensure logo is white */
            margin: 0 25px;
        }

        .navbar a {
            text-decoration: none;
            color: var(--text-muted);
            font-weight: 600;
            font-size: 14px;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            transition: color 0.3s ease, font-weight 0.3s ease;
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
            bottom: -8px;
            left: 0;
            width: 100%;
            height: 2px;
            background-color: var(--accent-red);
        }

        /* --- Main Header --- */
        .main-header {
            text-align: center;
            padding: 80px 20px 50px;
            animation: fadeInDown 0.6s ease-out;
        }

        .main-header h1 {
            font-size: 54px;
            font-weight: 900;
            text-transform: uppercase;
            letter-spacing: 3px;
            margin-bottom: 15px;
            background: linear-gradient(to right, var(--text-main), #4b5159);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            line-height: 1.1;
        }

        .main-header p {
            color: var(--text-muted);
            font-size: 18px;
            max-width: 550px;
            margin: 0 auto;
            letter-spacing: 0.5px;
            text-transform: uppercase;
            animation: fadeIn 0.8s ease-out 0.3s both;
        }

        /* --- Cards Container (Grid) --- */
        .cards-container {
            max-width: 1100px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(450px, 1fr));
            gap: 30px;
            padding: 0 20px;
            animation: fadeInUp 0.6s ease-out 0.2s both;
        }

        .app-card {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 10px;
            padding: 45px;
            text-decoration: none;
            color: var(--text-main);
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .app-card:hover {
            transform: translateY(-5px) scale(1.01);
            border-color: #30363d;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
        }

        /* --- Card Icons --- */
        .card-icon {
            width: 64px;
            height: 64px;
            margin-bottom: 30px;
            opacity: 0.7;
            transition: opacity 0.3s ease, filter 0.3s ease;
            filter: brightness(0) invert(1); /* Ensure icons are white by default */
        }

        .app-card:hover .card-icon {
            opacity: 1;
        }

        /* Red underline effect on hover for highlighted cards */
        .app-card::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 3px;
            background-color: var(--accent-red);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .app-card:hover::after {
            transform: scaleX(1);
        }

        .app-card h3 {
            font-size: 32px;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            margin: 0;
            line-height: 1.2;
        }

        /* --- Specific Card Color Effects on Hover --- */
        /* EMS and Gang cards turn red on hover, matching the logo */
        .ems-card:hover .card-icon,
        .gang-card:hover .card-icon {
            filter: brightness(0) saturate(100%) invert(17%) sepia(80%) saturate(7000%) hue-rotate(345deg);
        }

        /* --- Responsive Design (Mobile First) --- */
        @media (max-width: 768px) {
            .navbar {
                padding: 20px 15px;
                gap: 15px;
                flex-wrap: wrap;
            }
            .nav-logo {
                height: 30px;
                margin: 0 10px;
            }
            .navbar a {
                font-size: 12px;
                letter-spacing: 1px;
            }
            .main-header h1 {
                font-size: 38px;
            }
            .main-header p {
                font-size: 14px;
            }
            .cards-container {
                grid-template-columns: 1fr; /* Single column on small screens */
                gap: 20px;
            }
            .app-card {
                padding: 30px;
            }
            .card-icon {
                width: 48px;
                height: 48px;
            }
            .app-card h3 {
                font-size: 26px;
            }
        }

        /* --- Animations --- */
        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

    </style>
</head>
<body>

    <!-- Top Navigation Bar -->
    <nav class="navbar">
        <a href="#">Home</a>
        <a href="#">Events</a>
        <a href="#">Rules</a>
        <img src="https://i.imgur.com/rX97K2X.png" alt="Blackout City Logo" class="nav-logo">
        <a href="#" class="active">Applications</a>
        <a href="#">Team</a>
    </nav>

    <!-- Main Header Section -->
    <header class="main-header">
        <h1>Blackout City Applications</h1>
        <p>Select a department to submit your official application</p>
    </header>

    <!-- Applications Cards Grid -->
    <div class="cards-container">

        <!-- Card 1: Whitelist (Citizen) -->
        <a href="whitelist-form.html" class="app-card">
            <img src="https://img.icons8.com/?size=100&id=121357&format=png&color=FFFFFF" alt="Passport Icon" class="card-icon">
            <h3>Whitelist (Citizen)</h3>
        </a>

        <!-- Card 2: Police Department -->
        <a href="police-form.html" class="app-card">
            <img src="https://img.icons8.com/?size=100&id=66110&format=png&color=FFFFFF" alt="Police Badge Icon" class="card-icon">
            <h3>Police Department</h3>
        </a>

        <!-- Card 3: EMS Department (with red hover effect) -->
        <a href="ems-form.html" class="app-card ems-card">
            <img src="https://img.icons8.com/?size=100&id=12336&format=png&color=FFFFFF" alt="Medical Cross Icon" class="card-icon">
            <h3>EMS Department</h3>
        </a>

        <!-- Card 4: Gang & Family (with red hover effect) -->
        <a href="gang-form.html" class="app-card gang-card">
            <img src="https://img.icons8.com/?size=100&id=118690&format=png&color=FFFFFF" alt="Gang Crest Icon" class="card-icon">
            <h3>Gang & Family</h3>
        </a>

    </div>

</body>
</html>
