<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Giveaway Gamer Hub</title>
    <style>
        * {
            box-sizing: border-box;
        }
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #050206; /* Deep space black */
            
            /* CSS generated star and crimson dust layers */
            background-image: 
                radial-gradient(white, rgba(255,255,255,.2) 2px, transparent 40px),
                radial-gradient(rgba(255,0,0,0.85), rgba(255,0,0,0.15) 1.5px, transparent 30px),
                radial-gradient(rgba(255,0,60,0.6), rgba(255,0,60,0.1) 2.5px, transparent 40px);
            background-size: 550px 550px, 350px 350px, 250px 250px;
            background-position: 0 0, 40px 60px, 130px 270px;
            
            /* Particle animation engine */
            animation: spaceMove 90s linear infinite;
            
            color: #ffffff;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            min-height: 100vh;
            margin: 0;
            padding: 40px 20px 80px 20px;
            overflow-y: auto;
        }

        /* Seamless particle drifting animation loop */
        @keyframes spaceMove {
            from { background-position: 0 0, 40px 60px, 130px 270px; }
            to { background-position: 550px 1100px, 390px 760px, 680px 570px; }
        }

        /* Fully Expanded Modern Glassmorphic Container */
        .giveaway-card {
            background: rgba(15, 10, 20, 0.6);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 0, 60, 0.25);
            padding: 55px 40px;
            border-radius: 24px;
            box-shadow: 0 0 50px rgba(255, 0, 60, 0.2);
            text-align: center;
            max-width: 560px;
            width: 100%;
            z-index: 2;
            margin-top: auto;
            margin-bottom: auto;
            animation: cardFadeIn 0.8s ease-out;
            overflow: hidden;
        }

        @keyframes cardFadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Typography */
        h1 {
            font-size: 2.7rem;
            margin: 0 0 15px 0;
            background: linear-gradient(45deg, #ff2a2a, #ff0066, #9d00ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 25px rgba(255, 0, 66, 0.35);
            letter-spacing: 1px;
            font-weight: 800;
        }

        p.description {
            color: #b0b0cb;
            font-size: 1.15rem;
            line-height: 1.6;
            margin: 0 0 35px 0;
        }

        /* Animated Glowing Action Button */
        .enter-btn {
            display: block;
            background: linear-gradient(45deg, #ff0066, #6600cc);
            color: white;
            border: none;
            padding: 18px 40px;
            font-size: 1.25rem;
            font-weight: 800;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 6px 25px rgba(255, 0, 102, 0.4);
            transition: all 0.3s ease;
            width: 100%;
            text-transform: uppercase;
            letter-spacing: 1.5px;
        }

        .enter-btn:hover {
            transform: translateY(-3px) scale(1.02);
            box-shadow: 0 12px 30px rgba(255, 0, 102, 0.6);
        }

        /* Loading Spinner Element */
        .spinner {
            display: none;
            width: 45px;
            height: 45px;
            border: 4px solid rgba(255, 255, 255, 0.1);
            border-top: 4px solid #ff0066;
            border-radius: 50%;
            margin: 30px auto;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* View State Steps */
        .prank-container, .redirect-container {
            display: none;
            animation: fadeIn 0.4s ease-in-out;
        }

        /* Red Error Message Styling */
        .error-message {
            color: #ff4a4a;
            background: rgba(255, 74, 74, 0.08);
            border: 1px solid rgba(255, 74, 74, 0.25);
            padding: 24px;
            border-radius: 14px;
            font-size: 1.15rem;
            line-height: 1.6;
            text-shadow: 0 0 10px rgba(255, 74, 74, 0.2);
            margin-bottom: 35px;
        }

        .btn-group {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }

        .action-btn {
            padding: 16px 20px;
            font-size: 1.05rem;
            font-weight: 700;
            border-radius: 50px;
            cursor: pointer;
            border: none;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            transition: all 0.25s ease;
        }

        .proceed-btn {
            background: linear-gradient(45deg, #00ffcc, #0072ff);
            color: #050206;
            box-shadow: 0 4px 15px rgba(0, 255, 204, 0.25);
        }

        .proceed-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(0, 255, 204, 0.45);
        }

        .close-btn {
            background: rgba(255, 255, 255, 0.08);
            color: #ffffff;
            border: 1px solid rgba(255, 255, 255, 0.15);
        }

        .close-btn:hover {
            background: rgba(255, 255, 255, 0.15);
            transform: translateY(-2px);
        }

        /* --- Mock Redirect Screen Panel --- */
        .oauth-card {
            background: #191b20;
            border-radius: 12px;
            border: 1px solid #2f3136;
            text-align: center;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }
        
        .oauth-header {
            background: #111216;
            padding: 12px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid #23252a;
            font-size: 0.9rem;
            color: #b9bbbe;
            font-weight: 600;
        }

        .oauth-close-x {
            color: #72767d;
            cursor: pointer;
            font-size: 1.1rem;
        }

        .oauth-body {
            padding: 40px 30px;
        }

        .roblox-logo {
            font-family: 'Arial Black', Gadget, sans-serif;
            font-size: 2.2rem;
            font-weight: 900;
            color: #ffffff;
            letter-spacing: -1px;
            margin-bottom: 35px;
            text-transform: uppercase;
        }

        .redirect-title {
            font-size: 1.4rem;
            color: #ffffff;
            margin: 30px 0 40px 0;
            font-weight: 600;
            letter-spacing: 0.3px;
        }

        .blue-spinner {
            width: 32px;
            height: 32px;
            border: 3.5px solid rgba(0, 162, 255, 0.15);
            border-top: 3.5px solid #00a2ff;
            border-radius: 50%;
            margin: 40px auto;
            animation: spin 0.8s linear infinite;
        }

        .redirect-footer {
            color: #72767d;
            font-size: 0.85rem;
            line-height: 1.5;
            margin-top: 50px;
        }

        .redirect-footer span {
            color: #00a2ff;
            text-decoration: none;
            cursor: pointer;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.96); }
            to { opacity: 1; transform: scale(1); }
        }
    </style>
</head>
<body>

    <div class="giveaway-card">
        <!-- Main Hub View -->
        <div id="cardContent">
            <h1>Giveaway Gamer Hub</h1>
            <p class="description">READY TO WIN BIG? The massive global loot drop is officially active! Lock in your chance right now to walk away with premium gaming rewards!</p>
            
            <button class="enter-btn" id="enterBtn" onclick="startThinking()">Enter Giveaway</button>
        </div>

        <!-- 3 Second Loading Spinner -->
        <div class="spinner" id="loadingSpinner"></div>

        <!-- The Prank Note & Follow-up Actions -->
        <div class="prank-container" id="prankSection">
            <div class="error-message">
                Oops, your Bloxlink account isn't connected to your Roblox Account. Our website will mark you as a bot.
            </div>
            
            <div class="btn-group">
                <button class="action-btn proceed-btn" onclick="startRedirect()">Proceed</button>
                <button class="action-btn close-btn" onclick="stayOnPage()">Close</button>
            </div>
        </div>

        <!-- Mock Redirect Screen Panel -->
        <div class="redirect-container" id="redirectSection">
            <div class="oauth-card" style="padding-bottom: 40px;">
                <div class="oauth-header">
                    <span>Verify Your Account</span>
                    <span class="oauth-close-x" onclick="stayOnPage()">✕</span>
                </div>
                <div class="oauth-body">
                    <div class="roblox-logo">Roblox</div>
                    
                    <div class="redirect-title">Redirecting to roblox.com</div>
                    <div class="blue-spinner"></div>
                    
                    <div class="redirect-footer">
                        If you are not redirected back in a few seconds, <span onclick="stayOnPage()">cancel</span> and try again.
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        function startThinking() {
        
