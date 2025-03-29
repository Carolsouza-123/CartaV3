
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aniversário Especial</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            background: linear-gradient(to right, #ff758c, #ff7eb3);
            padding: 50px;
            transition: all 0.8s ease-in-out;
        }
        .container {
            background: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
            max-width: 500px;
            margin: auto;
            opacity: 1;
            transform: scale(1);
            transition: all 0.5s ease-in-out;
        }
        .hidden { 
            opacity: 0; 
            transform: scale(0.9);
            pointer-events: none;
        }
        input, button {
            padding: 10px;
            margin-top: 15px;
            border-radius: 8px;
            border: none;
            font-size: 16px;
        }
        button {
            background-color: #ff6f61;
            color: white;
            cursor: pointer;
            transition: 0.3s;
        }
        button:hover {
            background-color: #e65b50;
        }
        .fireworks {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: black;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 24px;
            opacity: 0;
            pointer-events: none;
            transition: opacity 1s;
        }
    </style>
</head>
<body>
    <div class="container" id="telaInicial">
        <h2>Olha só quem tá fazendo aniversário hoje 😱</h2>
        <p>Essa é fácil pra você, data da primeira vez que saímos juntos para o bombar ? 🤔</p>
        <input type="password" id="senha" placeholder="DD/MM/AAAA">
        <button onclick="verificarSenha()">Entrar</button>
    </div>

    <div class="container hidden" id="telaMensagem">
        <h2>Visando sua saúde mental e a minha...</h2>
        <p>Essa foi a forma que encontrei de te prestigiar nessa data tão especial sem precisar te desbloquear de tudo heheh 🥳</p>
        <button onclick="mostrarCarta()">🎂</button>
    </div>

    <div class="container hidden" id="telaCarta">
        <p>Hoje é um dia especial, e, mesmo com tudo o que aconteceu, eu queria te lembrar o quanto você significa pra mim.</p>
        <p>Que você tenha um ano cheio de alegrias, conquistas e, acima de tudo, felicidade. Eu sempre vou guardar com carinho os momentos que passamos juntos.</p>
        <p>Com todo o meu afeto e gratidão por tudo o que vivemos. ❤️</p>
    </div>

    <div class="fireworks" id="fogos">🎆🎇 Feliz Aniversário! 🎇🎆</div>

    <script>
        function verificarSenha() {
            let senhaCorreta = "16/03/2024"; // Exemplo de senha
            let senhaDigitada = document.getElementById("senha").value;
            if (senhaDigitada === senhaCorreta) {
                transicao("telaInicial", "telaMensagem");
            } else {
                alert("Senha incorreta! Tente novamente.");
            }
        }

        function mostrarCarta() {
            transicao("telaMensagem", "telaCarta");
            setTimeout(iniciarFogos, 10000);
        }

        function transicao(esconder, mostrar) {
            document.getElementById(esconder).classList.add("hidden");
            setTimeout(() => {
                document.getElementById(mostrar).classList.remove("hidden");
            }, 500);
        }

        function iniciarFogos() {
            let fogos = document.getElementById("fogos");
            fogos.style.opacity = "1";
            fogos.style.pointerEvents = "auto";
        }
    </script>
</body>
</html>
