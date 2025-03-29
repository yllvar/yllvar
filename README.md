<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quant Developer Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #6e48aa;
            --secondary: #9d50bb;
            --dark: #1a1a2e;
            --light: #f8f9fa;
            --success: #28a745;
            --danger: #dc3545;
            --warning: #ffc107;
            --info: #17a2b8;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, var(--dark), #16213e);
            color: var(--light);
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }
        
        header {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
            overflow: hidden;
            padding: 2rem;
            border-radius: 15px;
            background: rgba(26, 26, 46, 0.7);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            animation: fadeIn 1s ease-out;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }
        
        .particle {
            position: absolute;
            background: rgba(255, 255, 255, 0.5);
            border-radius: 50%;
            animation: float 15s infinite linear;
        }
        
        @keyframes float {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            100% { transform: translateY(-1000px) rotate(720deg); opacity: 0; }
        }
        
        h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            display: inline-block;
        }
        
        .tagline {
            font-size: 1.5rem;
            margin-bottom: 1.5rem;
            color: #ccc;
        }
        
        .intro {
            font-size: 1.1rem;
            line-height: 1.6;
            margin-bottom: 2rem;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }
        
        .section {
            background: rgba(26, 26, 46, 0.7);
            border-radius: 15px;
            padding: 2rem;
            margin-bottom: 2rem;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            animation: slideIn 0.8s ease-out;
        }
        
        @keyframes slideIn {
            from { opacity: 0; transform: translateX(-20px); }
            to { opacity: 1; transform: translateX(0); }
        }
        
        h2 {
            font-size: 2rem;
            margin-bottom: 1.5rem;
            color: var(--primary);
            position: relative;
            display: inline-block;
        }
        
        h2::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(to right, var(--primary), var(--secondary));
            border-radius: 3px;
        }
        
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 1.5rem;
        }
        
        .skill-category {
            background: rgba(30, 30, 60, 0.7);
            border-radius: 10px;
            padding: 1.5rem;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .skill-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }
        
        h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--secondary);
        }
        
        .badge-container {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }
        
        .badge {
            display: inline-block;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: bold;
            background: rgba(109, 72, 170, 0.2);
            border: 1px solid var(--primary);
            color: #ddd;
            transition: all 0.3s ease;
        }
        
        .badge:hover {
            background: var(--primary);
            color: white;
            transform: scale(1.05);
        }
        
        .game-container {
            background: rgba(20, 20, 40, 0.8);
            border-radius: 15px;
            padding: 2rem;
            margin-top: 3rem;
            text-align: center;
            animation: pulse 2s infinite alternate;
        }
        
        @keyframes pulse {
            from { box-shadow: 0 0 10px rgba(157, 80, 187, 0.5); }
            to { box-shadow: 0 0 20px rgba(157, 80, 187, 0.8); }
        }
        
        .game-title {
            font-size: 1.8rem;
            margin-bottom: 1.5rem;
            color: var(--warning);
        }
        
        .game-description {
            margin-bottom: 1.5rem;
            color: #ccc;
        }
        
        .game-stats {
            display: flex;
            justify-content: space-around;
            margin-bottom: 1.5rem;
            font-size: 1.2rem;
        }
        
        .stat {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        .stat-value {
            font-weight: bold;
            font-size: 1.5rem;
            color: var(--success);
        }
        
        .crypto-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 1rem;
            margin-bottom: 2rem;
        }
        
        .crypto-card {
            background: rgba(40, 40, 80, 0.7);
            border-radius: 10px;
            padding: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }
        
        .crypto-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        }
        
        .crypto-card.selected {
            background: rgba(40, 167, 69, 0.2);
            border: 2px solid var(--success);
        }
        
        .crypto-name {
            font-weight: bold;
            margin-bottom: 0.5rem;
        }
        
        .crypto-price {
            font-size: 1.2rem;
            color: var(--success);
        }
        
        .crypto-change {
            font-size: 0.9rem;
        }
        
        .positive {
            color: var(--success);
        }
        
        .negative {
            color: var(--danger);
        }
        
        .game-controls {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }
        
        .btn {
            padding: 0.8rem 1.5rem;
            border-radius: 30px;
            border: none;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
        }
        
        .btn-primary {
            background: linear-gradient(to right, var(--primary), var(--secondary));
            color: white;
        }
        
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(157, 80, 187, 0.4);
        }
        
        .btn-secondary {
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.2);
        }
        
        .game-log {
            height: 150px;
            overflow-y: auto;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 10px;
            padding: 1rem;
            text-align: left;
            margin-bottom: 1.5rem;
        }
        
        .log-entry {
            margin-bottom: 0.5rem;
            font-size: 0.9rem;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
            padding-bottom: 0.5rem;
        }
        
        .log-time {
            color: #aaa;
            margin-right: 0.5rem;
        }
        
        .log-message {
            color: #ddd;
        }
        
        .log-profit {
            color: var(--success);
        }
        
        .log-loss {
            color: var(--danger);
        }
        
        .typing-effect {
            display: inline-block;
            overflow: hidden;
            border-right: 0.15em solid var(--primary);
            white-space: nowrap;
            margin: 0 auto;
            letter-spacing: 0.15em;
            animation:
</html>
