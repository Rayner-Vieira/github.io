<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Apresentação</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #ffffff; /* Fundo branco */
            display: flex;
            flex-direction: column;
            align-items: center;
            height: 100vh;
        }
        .container {
            display: flex;
            width: 100%;
            height: 13%; /* Ocupa apenas 15% da altura da tela */
            margin-top: 16px;
        }
        .box {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            background-color: #ff0000;
            border-radius: 15px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            color: #ffffff;
            font-size: 38px;
            text-align: center;
            margin: 10px;
            position: relative; /* Adicionado para posicionamento relativo */
        }
        .logo {
            position: absolute;
            top: 0;
            left: 0;
            height: 100px;
            width: auto;
        }
        .image-container {
            display: flex;
            width: 100%;
            height: 83%; /* Ocupa o restante da altura da tela */
        }
        .image-column {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: flex-start;
            margin: 5px;
            position: relative;
        }
        .image-box {
            width: 50%;
            height: 60%;
            display: flex;
            justify-content: center;
            align-items: center;
            border: 2px solid #ccc;
            margin: 5px;
            overflow: hidden;
            position: absolute;
            cursor: pointer;
        }
        .image-box.top {
            left: 0; /* Imagem superior mais à esquerda */
        }
        .image-box.bottom {
            right: 0; /* Imagem inferior mais à direita */
            top: 40%; /* Ajuste a posição vertical */
        }
        .image-box input {
            display: none;
        }
        .image-box label {
            display: block;
            width: 100%;
            height: 100%;
            text-align: center;
            line-height: 22.5vh; /* Ajuste a linha de base vertical */
            cursor: pointer;
            background-color: #eee;
        }
        .image-box img {
            width: 100%;
            height: 100%;
            object-fit: fill; /* Ajusta a imagem para caber totalmente na área */
            position: absolute;
        }
        .smaller-image {
            width: 62%;
            height: 85%;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%); /* Centraliza vertical e horizontalmente */
            border: 2px solid #ccc;
            overflow: hidden;
            position: absolute;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="box">
            <h1>Destaques</h1>
        </div>
        <div class="box">
            <h1>Aniversariantes do mês</h1>
        </div>
    </div>
    <div class="image-container">
        <div class="image-column">
            <div class="image-box top" onclick="document.getElementById('image1').click()">
                <input type="file" id="image1" accept="image/*" onchange="loadImage(event, 'img1')">
                <label for="image1">Escolha a foto do colaborador destaque do ensaque</label>
                <img id="img1" src="">
            </div>
            <div class="image-box bottom" onclick="document.getElementById('image2').click()">
                <input type="file" id="image2" accept="image/*" onchange="loadImage(event, 'img2')">
                <label for="image2">Escolha a foto do colaborador destaque da manutenção</label>
                <img id="img2" src="">
            </div>
        </div>
        <div class="image-column" style="flex: 1;">
            <div class="image-box smaller-image" onclick="document.getElementById('image3').click()">
                <input type="file" id="image3" accept="image/*" onchange="loadImage(event, 'img3')">
                <label for="image3">Escolha uma imagem</label>
                <img id="img3" src="">
            </div>
        </div>
    </div>

    <script>
        function loadImage(event, imgId) {
            var output = document.getElementById(imgId);
            var reader = new FileReader();
            reader.onload = function(){
                output.src = reader.result;
            };
            reader.readAsDataURL(event.target.files[0]);
        }
    </script>
</body>
</html>
