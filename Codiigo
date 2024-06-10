<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Micrositio con Chat</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/crypto-js/4.1.1/crypto-js.min.js"></script>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #5f8edf; /* Fondo gris claro */
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            width: 400px;
            padding: 20px;
            background-color: #fff; /* Contenedor blanco */
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        h1 {
            text-align: center;
            color: #333;
            margin-bottom: 20px;
        }

        #chat-box {
            border: 1px solid #ddd; /* Borde del chat más claro */
            padding: 10px;
            border-radius: 5px;
            margin-bottom: 20px;
            height: 300px;
            overflow-y: auto;
        }

        #message-input {
            width: calc(100% - 85px);
            padding: 8px;
            border: 1px solid #ddd; /* Borde del campo de entrada más claro */
            border-radius: 5px;
            font-size: 16px;
            outline: none;
        }

        #send-btn {
            padding: 8px 15px;
            background-color: #4CAF50; /* Botón de enviar verde claro */
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            transition: background-color 0.3s ease;
        }

        #send-btn:hover {
            background-color: #45a049; /* Color de fondo más oscuro al pasar el mouse */
        }

        .encrypted-message {
            font-style: italic; /* Estilo de fuente en cursiva */
            color: #999; /* Color de texto gris */
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Bienvenido al chat</h1>
        <div id="chat-box">
            <div id="chat"></div>
        </div>
        <input type="text" id="message-input" placeholder="Escribe tu mensaje...">
        <button id="send-btn">Enviar</button>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const chatBox = document.getElementById('chat');
            const messageInput = document.getElementById('message-input');
            const sendButton = document.getElementById('send-btn');

            sendButton.addEventListener('click', function() {
                const message = messageInput.value.trim();
                if (message !== '') {
                    const encryptedMessage = encryptMessage(message);
                    appendMessage('You', encryptedMessage);
                    messageInput.value = '';
                    // Aquí puedes agregar la lógica para enviar el mensaje al servidor o procesarlo de otra manera
                }
            });

            function encryptMessage(message) {
                // Clave de cifrado (debes mantener esto seguro y enviarla al destinatario de manera segura)
                const key = 'claveSuperSecreta123';
                // Cifrar el mensaje con AES utilizando la clave
                const encrypted = CryptoJS.AES.encrypt(message, key).toString();
                return encrypted;
            }

            function appendMessage(sender, message) {
                const messageElement = document.createElement('div');
                messageElement.innerHTML = `<strong>${sender}:</strong> <span class="encrypted-message">${message} (Mensaje cifrado)</span>`;
                chatBox.appendChild(messageElement);
                chatBox.scrollTop = chatBox.scrollHeight;
            }
        });
    </script>
</body>
</html>
