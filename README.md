# Yeah-boy
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My AI Website</title>
    <style>
        /* CSS will go here to style your website */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
        }
        header {
            background-color: #333;
            color: #fff;
            padding: 1rem 0;
            text-align: center;
        }
        main {
            flex: 1;
            padding: 20px;
            text-align: center;
        }
        .ai-interaction-box {
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
            padding: 30px;
            margin: 30px auto;
            max-width: 600px;
        }
        input[type="text"] {
            width: calc(100% - 22px);
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 1rem;
        }
        button {
            background-color: #007bff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 1rem;
            transition: background-color 0.3s ease;
        }
        button:hover {
            background-color: #0056b3;
        }
        #response {
            margin-top: 20px;
            text-align: left;
            white-space: pre-wrap; /* Preserves whitespace and line breaks */
            border-top: 1px solid #eee;
            padding-top: 15px;
            color: #555;
        }
        footer {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 1rem 0;
            margin-top: auto;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to My AI Helper!</h1>
    </header>

    <main>
        <div class="ai-interaction-box">
            <h2>Ask me anything!</h2>
            <input type="text" id="userInput" placeholder="Type your question or request here...">
            <button onclick="sendToAI()">Generate Response</button>
            <div id="response">
                <!-- AI's response will appear here -->
                <p>Hello! I'm Dola, your AI assistant. How can I help you today?</p>
            </div>
        </div>
    </main>

    <footer>
        <p>&copy; 2026 My AI Website</p>
    </footer>

    <script>
        // JavaScript will go here to make your website interactive
        async function sendToAI() {
            const userInput = document.getElementById('userInput').value;
            const responseDiv = document.getElementById('response');

            if (!userInput.trim()) {
                responseDiv.innerHTML = '<p style="color: red;">Please type something first!</p>';
                return;
            }

            responseDiv.innerHTML = '<p>Thinking...</p>'; // Show a loading message

            // --- THIS IS WHERE YOU WOULD CONNECT TO YOUR ACTUAL AI ---
            // For now, let's simulate a response.
            // In a real application, you would send 'userInput' to a backend server
            // that then communicates with an AI model (like Google's Gemini API).
            // Example of what a real fetch might look like (this won't work without a backend):
            /*
            try {
                const apiResponse = await fetch('/api/ai-chat', {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json'
                    },
                    body: JSON.stringify({ message: userInput })
                });
                const data = await apiResponse.json();
                responseDiv.innerHTML = '<p>' + data.aiResponse + '</p>';
            } catch (error) {
                console.error('Error fetching AI response:', error);
                responseDiv.innerHTML = '<p style="color: red;">Oops! Something went wrong.</p>';
            }
            */

            // SIMULATED RESPONSE (REMOVE THIS WHEN YOU ADD REAL AI INTEGRATION)
            setTimeout(() => {
                const simulatedResponses = [
                    "That's a great question! Let me think...",
                    "I'm still learning, but I can try to help with that.",
                    "Interesting! Could you elaborate a bit more?",
                    "Processing your request...",
                    "Here's what I found:"
                ];
                const randomResponse = simulatedResponses[Math.floor(Math.random() * simulatedResponses.length)];
                responseDiv.innerHTML = `<p>You asked: "${userInput}"</p><p>AI says: ${randomResponse} (This is a simulated response. You'll replace this with real AI later!)</p>`;
            }, 1500); // Simulate network delay
            // END SIMULATED RESPONSE
        }
    </script>
</body>
</html>
