<!DOCTYPE html>
<html>
<head>
  <title>Chatbot</title>
  <style>
    .chat-container {
      height: 400px;
      border: 1px solid #ccc;
      padding: 10px;
      overflow-y: scroll;
    }
    .user-message {
      color: blue;
    }
    .bot-message {
      color: green;
    }
  </style>
</head>
<body>
  <div class="chat-container" id="chatContainer"></div>
  <input type="text" id="userInput" placeholder="Type your message..." />
  <button onclick="sendMessage()">Send</button>

  <script>
    const chatContainer = document.getElementById('chatContainer');
    const userInput = document.getElementById('userInput');

    function sendMessage() {
      const userMessage = userInput.value;
      appendMessage(userMessage, 'user-message');
      processMessage(userMessage);
      userInput.value = '';
    }

    function appendMessage(message, className) {
      const messageElement = document.createElement('div');
      messageElement.classList.add(className);
      messageElement.innerText = message;
      chatContainer.appendChild(messageElement);
      chatContainer.scrollTop = chatContainer.scrollHeight;
    }

    function processMessage(message) {
      const botMessage = getBotResponse(message);
      appendMessage(botMessage, 'bot-message');
    }

    function getBotResponse(message) {
      // Your logic for generating bot response goes here
      // This is just a sample response
      if (message.includes('hi') || message.includes('hello')) {
        return 'Hello! How can I assist you?';
      } else {
        return 'I'm sorry, I didn't understand that.';
      }
    }
  </script>
</body>
</html>
