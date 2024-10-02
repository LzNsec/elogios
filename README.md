# rayssa.github.io





<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Terminal Romântico</title>
    <style>
        body {
            background-color: #1e1e1e;
            color: #00ff00;
            font-family: monospace;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .terminal {
            width: 60%;
            padding: 20px;
            background-color: #000;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
        }
        #output {
            white-space: pre-line;
            margin-bottom: 20px;
        }
        input {
            width: 100%;
            padding: 10px;
            background-color: #333;
            color: #00ff00;
            border: none;
            border-radius: 4px;
            font-family: monospace;
        }
        input:focus {
            outline: none;
        }
    </style>
</head>
<body>
    <div class="terminal">
        <div id="output">Olá, você. Sim, você mesmo... Desde o primeiro momento em que te vi, algo mudou...</div>
        <input type="text" id="input" placeholder="Digite 's' para continuar ou 'n' para sair">
    </div>

    <script>
        const input = document.getElementById("input");
        const output = document.getElementById("output");

        const mensagens = [
            "Desde o primeiro momento em que te vi, algo mudou. Não sei se foi o brilho nos seus olhos ou a suavidade do seu sorriso...",
            "Você é como um pôr do sol em uma tarde calma de verão. A sua presença traz uma paz inexplicável...",
            "Cada palavra que você diz parece uma melodia suave, que ressoa no meu coração...",
            "Se essas palavras tocaram seu coração, envie uma mensagem para mim no Instagram. Apenas escreva a palavra 'Civic'..."
        ];

        let index = 0;

        input.addEventListener("keypress", function(event) {
            if (event.key === "Enter") {
                const resposta = input.value.toLowerCase();
                input.value = ""; // Limpar a entrada

                if (resposta === 's' && index < mensagens.length) {
                    output.innerHTML += `\n${mensagens[index]}`;
                    index++;
                } else if (resposta === 'n') {
                    output.innerHTML += "\nTudo bem, talvez em outro momento você esteja mais disposta a ouvir...";
                    input.disabled = true; // Desativa a entrada
                } else if (index >= mensagens.length) {
                    output.innerHTML += "\nObrigado por ler até aqui!";
                    input.disabled = true; // Desativa a entrada
                } else {
                    output.innerHTML += "\nResposta inválida. Tente novamente.";
                }

                // Rolar para o fim do terminal
                output.scrollTop = output.scrollHeight;
            }
        });
    </script>
</body>
</html>
