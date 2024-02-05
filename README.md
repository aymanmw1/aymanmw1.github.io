
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            background-color: #f7e1ea;
            margin: 0;
            padding: 0;
        }

        #password-container {
            padding: 50px;
            width: 100vw;
            height: 100vh;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        #passwordInput {
            padding: 10px;
            font-size: 16px;
        }

        #proposal-container {
            display: none;
            padding: 50px;
            width: 100vw;
            height: 100vh;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        #proposal-container img {
            max-width: 100%;
            border-radius: 5px;
            margin-bottom: 20px;
        }

        #yesButton {
            background-color: green;
            color: white;
        }

        #noButton {
            background-color: red;
            color: white;
        }

        #response {
            font-weight: bold;
            margin-top: 20px;
        }

        #cute-messages {
            display: none;
            margin-top: 20px;
        }

        #helloKittyGIF {
            display: none;
            margin: 0 auto; /* Center horizontally */
        }

        #valentine-sentence {
            background-color: pink;
            padding: 10px;
            border-radius: 5px;
        }
    </style>
</head>

<body>
    <script>
        function checkPassword() {
            // Check for the correct password
            var enteredPassword = prompt("This website is only for Ayooyty. Enter our anniversary day to access:\n\nEnter the password (format: MM/DD/YYYY):");
            var correctPassword = "12/06/2022";

            if (enteredPassword !== correctPassword) {
                alert("YOU ARE NOT MY AYOYTY. Access denied.");
            } else {
                // Hide password container and display proposal content
                document.getElementById('password-container').style.display = 'none';
                document.getElementById('proposal-container').style.display = 'block';
            }
        }

        let currentMessageIndex = 0;

        function propose(answer) {
            // Hide unnecessary elements
            document.getElementById('valentine-sentence').style.display = 'none';
            document.getElementById('proposal-container').style.padding = '20px';
            document.getElementById('proposal-container').style.height = 'auto';

            if (answer === 'Yes') {
                // Display the result and GIF
                document.getElementById('response').innerHTML = 'YAYYYY❗❗';
                document.getElementById('helloKittyGIF').style.display = 'block';

                // Hide other buttons and messages
                document.getElementById('yesButton').style.display = 'none';
                document.getElementById('noButton').style.display = 'none';
                document.getElementById('cute-messages').style.display = 'none';
            } else if (answer === 'No') {
                // Show cute messages
                showCuteMessages();
                document.getElementById('yesButton').style.fontSize = (16 + currentMessageIndex * 2) + 'px';
                document.getElementById('noButton').style.fontSize = (16 - currentMessageIndex * 2) + 'px';
            }
        }

        function showCuteMessages() {
            const messages = document.getElementById('cute-messages').children;
            if (currentMessageIndex < messages.length) {
                messages[currentMessageIndex].style.display = 'block';
                document.getElementById('noButton').innerHTML = messages[currentMessageIndex].innerText;
                currentMessageIndex++;
            } else {
                // If all messages shown, hide unnecessary elements
                document.getElementById('valentine-sentence').style.display = 'none';
                document.getElementById('proposal-container').style.padding = '20px';
                document.getElementById('proposal-container').style.height = 'auto';
                document.getElementById('yesButton').style.display = 'none';
                document.getElementById('noButton').style.display = 'none';
                document.getElementById('cute-messages').style.display = 'none';
            }
        }
    </script>

    <div id="password-container">
        <button onclick="checkPassword()">Enter</button>
    </div>

    <div id="proposal-container">
        <img src="https://i.imgur.com/G4oqRYW.jpg" alt="My baby" style="max-width: 300px;">
        <div id="valentine-sentence">
            <h1>Will You Be My Valentine?</h1>
        </div>
        <p>Dear Ayooyty,</p>
        <p>You better say yes ( ˘ ³˘)♥︎ </p>
        <button id="yesButton" onclick="propose('Yes')">Yes</button>
        <button id="noButton" onclick="propose('No')">No</button>
        <p id="response"></p>
        <div id="cute-messages">
            <p>Are you sure?</p>
            <p>Really sure?</p>
            <p>Pookie please</p>
            <p>Don't do this to me</p>
            <p>I'm gonna cry…..</p>
            <p>You're breaking my heart ; (</p>
        </div>
        <img id="helloKittyGIF" src="https://media1.tenor.com/m/i7Sa8ZBIJn4AAAAC/love-you.gif" alt="Hello Kitty GIF">
    </div>

</body>

</html>
