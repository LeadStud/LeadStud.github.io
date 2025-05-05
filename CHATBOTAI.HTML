<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1" />
<title>Realtime AI Chatbot</title>
<style>
  /* Reset and base style */
  * {
    box-sizing: border-box;
  }

  body {
    background: #121212;
    color: #e1e1e1;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
    padding: 0;
    height: 100vh;
    display: flex;
    flex-direction: column;
  }

  header {
    padding: 1rem;
    background: #1f1f1f;
    text-align: center;
    font-size: 1.5rem;
    font-weight: 700;
    color: #4ef1ff;
    letter-spacing: 1.2px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.7);
  }

  #chat-container {
    flex: 1;
    overflow-y: auto;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
    background: #181818;
  }

  .message {
    max-width: 80%;
    padding: 0.8rem 1rem;
    border-radius: 20px;
    font-size: 1rem;
    line-height: 1.4;
    white-space: pre-wrap;
  }

  .user-message {
    align-self: flex-end;
    background: #4ef1ff;
    color: #121212;
    border-bottom-right-radius: 4px;
  }

  .bot-message {
    align-self: flex-start;
    background: #333;
    color: #e1e1e1;
    border-bottom-left-radius: 4px;
    position: relative;
  }

  .bot-message.loading::after {
    content: '';
    display: inline-block;
    width: 16px;
    height: 16px;
    margin-left: 10px;
    border-radius: 50%;
    border: 3px solid #4ef1ff;
    border-top-color: transparent;
    animation: spin 1s linear infinite;
    vertical-align: middle;
  }

  @keyframes spin {
    0% { transform: rotate(0deg);}
    100% { transform: rotate(360deg);}
  }

  #input-area {
    display: flex;
    padding: 0.5rem 1rem;
    background: #1f1f1f;
    box-shadow: 0 -2px 10px rgba(0,0,0,0.7);
  }

  #input-area textarea {
    flex: 1;
    resize: none;
    border: none;
    border-radius: 20px;
    padding: 0.8rem 1rem;
    font-size: 1rem;
    outline: none;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }

  #input-area button {
    background: #4ef1ff;
    border: none;
    color: #121212;
    font-weight: 600;
    margin-left: 0.5rem;
    padding: 0 1.2rem;
    border-radius: 20px;
    cursor: pointer;
    font-size: 1rem;
    transition: background 0.3s ease;
  }

  #input-area button:disabled {
    opacity: 0.5;
    cursor: not-allowed;
  }

  #input-area button:hover:not(:disabled) {
    background: #22c2d6;
  }

  /* Scrollbar styling for webkit browsers */
  #chat-container::-webkit-scrollbar {
    width: 8px;
  }
  #chat-container::-webkit-scrollbar-track {
    background: #121212;
  }
  #chat-container::-webkit-scrollbar-thumb {
    background: #4ef1ff;
    border-radius: 4px;
  }

  /* Mobile responsiveness */
  @media (max-width: 600px) {
    #chat-container {
      padding: 0.75rem 0.5rem;
      max-height: 600px;
    }
    .message {
      max-width: 90%;
      font-size: 0.9rem;
    }
    #input-area textarea {
      font-size: 0.9rem;
    }
    #input-area button {
      padding: 0 1rem;
      font-size: 0.9rem;
    }
  }

</style>
</head>
<body>
<header>LeadStudAI</header>
<div id="chat-container" role="log" aria-live="polite" aria-relevant="additions"></div>
<form id="input-area" autocomplete="off" aria-label="Chat input form">
  <textarea id="user-input" rows="1" placeholder="Tanya apa saja..." aria-label="Input your question"></textarea>
  <button type="submit" id="send-button" disabled>Send</button>
</form>

<script>
(() => {
  "use strict";

  const chatContainer = document.getElementById('chat-container');
  const inputForm = document.getElementById('input-area');
  const userInput = document.getElementById('user-input');
  const sendButton = document.getElementById('send-button');

  // Replace 'YOUR_OPENAI_API_KEY' with your actual OpenAI API key
  const OPENAI_API_KEY = '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';

  // Helper function to append messages to chat container
  function appendMessage(text, isUser = false, loading = false) {
    const div = document.createElement('div');
    div.classList.add('message');
    if (isUser) {
      div.classList.add('user-message');
    } else {
      div.classList.add('bot-message');
      if (loading) {
        div.classList.add('loading');
      }
    }
    div.textContent = text;
    chatContainer.appendChild(div);
    chatContainer.scrollTop = chatContainer.scrollHeight;
    return div;
  }

  // Auto resize textarea height
  function autoResizeTextarea() {
    userInput.style.height = 'auto';
    userInput.style.height = userInput.scrollHeight + 'px';
  }

  // Enable send button when there's input
  userInput.addEventListener('input', () => {
    autoResizeTextarea();
    sendButton.disabled = userInput.value.trim().length === 0;
  });

  // Call OpenAI API to get AI response
  async function getAIResponse(question) {
    const endpoint = 'https://api.openai.com/v1/chat/completions';
    
    const headers = {
      'Content-Type': 'application/json',
      'Authorization': 'Bearer ' + OPENAI_API_KEY
    };

    const body = {
      model: 'gpt-3.5-turbo',
      messages: [
        { role: 'system', content: 'You are a helpful AI assistant that can answer all questions.' },
        { role: 'user', content: question }
      ],
      max_tokens: 1000,
      temperature: 0.7,
      n: 1,
      stream: false
    };

    try {
      const response = await fetch(endpoint, {
        method: 'POST',
        headers: headers,
        body: JSON.stringify(body)
      });

      if (!response.ok) {
        const errorData = await response.json();
        throw new Error(errorData.error.message || 'OpenAI API error');
      }

      const data = await response.json();
      const aiText = data.choices[0].message.content.trim();
      return aiText;
    } catch (error) {
      return 'Maaf, terjadi kesalahan pada server: ' + error.message;
    }
  }

  // Handle form submit event
  inputForm.addEventListener('submit', async (event) => {
    event.preventDefault();
    const question = userInput.value.trim();
    if (!question) return;

    // Append user message
    appendMessage(question, true);
    userInput.value = '';
    sendButton.disabled = true;
    autoResizeTextarea();

    // Append bot loading message
    const botMessageDiv = appendMessage('...', false, true);

    // Get AI response
    const aiResponse = await getAIResponse(question);

    // Remove loading style and update text
    botMessageDiv.classList.remove('loading');
    botMessageDiv.textContent = aiResponse;

    chatContainer.scrollTop = chatContainer.scrollHeight;
  });

  // Initial setup
  sendButton.disabled = true;
})();
</script>
</body>
</html>

