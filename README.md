# Musiс-
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <title>Музичні жанри</title>

    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: linear-gradient(135deg, #1d2671, #c33764);
            color: #fff;
        }

        .card {
            width: 450px;
            margin: 70px auto;
            background: #ffffff;
            color: #333;
            padding: 25px;
            border-radius: 15px;
            box-shadow: 0 15px 30px rgba(0,0,0,0.3);
        }

        h1 {
            text-align: center;
        }

        label {
            display: block;
            margin: 6px 0;
        }

        button {
            margin-top: 15px;
            width: 100%;
            padding: 10px;
            font-size: 16px;
            background: #1d2671;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
        }

        button:hover {
            background: #151c54;
        }

        .result {
            margin-top: 20px;
            display: none;
        }

        .bar {
            height: 18px;
            background: #c33764;
            border-radius: 5px;
            margin-bottom: 6px;
        }
    </style>
</head>
<body>

<div class="card">
    <h1>🎵 Обери жанри музики</h1>

    <form id="musicForm">
        <label><input type="checkbox" value="Поп"> Поп</label>
        <label><input type="checkbox" value="Рок"> Рок</label>
        <label><input type="checkbox" value="Хіп-хоп"> Хіп-хоп</label>
        <label><input type="checkbox" value="Реп"> Реп</label>
        <label><input type="checkbox" value="Електронна"> Електронна</label>
        <label><input type="checkbox" value="Техно"> Техно</label>
        <label><input type="checkbox" value="Джаз"> Джаз</label>
        <label><input type="checkbox" value="Класична"> Класична</label>

        <button type="button" onclick="showResult()">Зберегти відповідь</button>
    </form>

    <div class="result" id="result">
        <h3>📊 Результати</h3>
        <div id="stats"></div>
    </div>
</div>

<script>
    function showResult() {
        const checkboxes = document.querySelectorAll('input[type="checkbox"]');
        const statsDiv = document.getElementById("stats");
        const resultBlock = document.getElementById("result");

        statsDiv.innerHTML = "";
        resultBlock.style.display = "block";

        let selected = [];

        checkboxes.forEach(cb => {
            if (cb.checked) {
                selected.push(cb.value);
            }
        });

        if (selected.length === 0) {
            statsDiv.innerHTML = "❗ Ти нічого не обрав.";
            return;
        }

        selected.forEach(item => {
            let percent = Math.floor(Math.random() * 60) + 20; // імітація %

            statsDiv.innerHTML += `
                <strong>${item}</strong> — ${percent}%
                <div class="bar" style="width:${percent}%"></div>
            `;
        });
    }
</script>

</body>
</html>
