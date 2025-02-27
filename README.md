# Sukiyaki
Chat about Math

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Math Study Helper</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; padding: 20px; }
        .container { max-width: 500px; margin: auto; }
        .hidden { display: none; }
        textarea { width: 100%; height: 100px; }
    </style>
</head>
<body>
    <div class="container">
        <h1>Math Study Helper</h1>
        <p>Enter a number to generate a math problem:</p>
        <input type="number" id="numberInput" placeholder="Enter a number">
        <button onclick="generateProblem()">Generate</button>
        <p id="problemOutput"></p>
        
        <h2>Study Notes</h2>
        <textarea id="notes" placeholder="Type your notes here..."></textarea>
        
        <button onclick="toggleChat()">Private Notes</button>
        <div id="chatBox" class="hidden">
            <h3>Private Messages</h3>
            <textarea id="messageInput" placeholder="Type a message..."></textarea>
            <button onclick="sendMessage()">Send</button>
            <div id="messageLog"></div>
        </div>
    </div>

    <script>
        function generateProblem() {
            let number = document.getElementById("numberInput").value;
            if (number) {
                document.getElementById("problemOutput").innerText = `Solve: ${number} × ${Math.floor(Math.random() * 10) + 1}`;
            }
        }

        function toggleChat() {
            let chatBox = document.getElementById("chatBox");
            chatBox.classList.toggle("hidden");
        }

        function sendMessage() {
            let message = document.getElementById("messageInput").value;
            if (message) {
                let log = document.getElementById("messageLog");
                let newMessage = document.createElement("p");
                newMessage.innerText = `You: ${message}`;
                log.appendChild(newMessage);
                document.getElementById("messageInput").value = "";
            }
        }
    </script>
</body>
</html>
