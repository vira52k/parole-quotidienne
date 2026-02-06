<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Parole Quotidienne</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            margin: 0;
            padding: 20px;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .container {
            background: white;
            max-width: 700px;
            width: 100%;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.2);
            text-align: center;
        }
        h1 {
            color: #2c3e50;
            margin-bottom: 25px;
        }
        .verse-box {
            background: #f8f9fa;
            border-radius: 10px;
            padding: 30px;
            margin: 25px 0;
            border-left: 5px solid #3498db;
            min-height: 200px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        .verse {
            font-size: 22px;
            color: #2c3e50;
            line-height: 1.6;
            font-style: italic;
            margin-bottom: 20px;
        }
        .reference {
            color: #2980b9;
            font-size: 20px;
            font-weight: bold;
            font-style: italic;
        }
        button {
            background: #3498db;
            color: white;
            border: none;
            padding: 15px 40px;
            font-size: 18px;
            border-radius: 50px;
            cursor: pointer;
            margin-top: 20px;
        }
        button:hover {
            background: #2980b9;
        }
        .info {
            margin-top: 25px;
            color: #7f8c8d;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>📖 Parole Quotidienne</h1>
        
        <div class="verse-box">
            <div class="verse" id="verse">
                Car Dieu a tant aimé le monde qu'il a donné son Fils unique, afin que quiconque croit en lui ne périsse point, mais qu'il ait la vie éternelle.
            </div>
            <div class="reference" id="reference">— Jean 3:16</div>
        </div>
        
        <button onclick="changeVerse()">Nouveau Verset</button>
        
        <div class="info">
            <p>Clique sur le bouton pour un nouveau verset</p>
        </div>
    </div>

    <script>
        const verses = [
            {text: "Car Dieu a tant aimé le monde qu'il a donné son Fils unique, afin que quiconque croit en lui ne périsse point, mais qu'il ait la vie éternelle.", ref: "Jean 3:16"},
            {text: "Je puis tout par celui qui me fortifie.", ref: "Philippiens 4:13"},
            {text: "L'Éternel est mon berger: je ne manquerai de rien.", ref: "Psaume 23:1"},
            {text: "Ne crains point, car je suis avec toi.", ref: "Ésaïe 41:10"},
            {text: "Venez à moi, vous tous qui êtes fatigués et chargés, et je vous donnerai du repos.", ref: "Matthieu 11:28"}
        ];
        
        function changeVerse() {
            const v = verses[Math.floor(Math.random() * verses.length)];
            document.getElementById('verse').textContent = v.text;
            document.getElementById('reference').textContent = "— " + v.ref;
            
            const btn = document.querySelector('button');
            btn.textContent = "✓ Verset changé";
            btn.style.background = "#27ae60";
            
            setTimeout(() => {
                btn.textContent = "Nouveau Verset";
                btn.style.background = "#3498db";
            }, 500);
        }
        
        // Touche ESPACE
        document.addEventListener('keydown', (e) => {
            if (e.code === 'Space') {
                e.preventDefault();
                changeVerse();
            }
        });
    </script>
</body>
</html>
