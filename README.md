<!DOCTYPE html>
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

        #proposal-container {
            padding: 50px;
            max-width: 600px;
            margin: auto;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        }

        #proposal-container img {
            max-width: 100%;
            border-radius: 5px;
            margin-bottom: 20px;
        }

        button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 10px;
            cursor: pointer;
            transition: all 0.3s ease;
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
        }
    </style>
</head>
<body>
    <div id="proposal-container">
        <img src="https://imgur.com/G4oqRYW" alt="You and Ayooyty" style="max-width: 300px;">
        <h1>Will You Be My Valentine?</h1>
        <p>Dear Ayooyty,</p>
        <p>On You better press yes (:...</p>
        <button id="yesButton" onclick="propose('Yes')">Yes</button>
        <button id="noButton" onclick="showCuteMessages()">No</button>
        <p id="response"></p>
        <div id="cute-messages">
            <p>No</p>
            <p>Are you sure?</p>
            <p>Really sure?</p>
            <p>Pookie please</p>
            <p>Don't do this to me</p>
            <p>I'm gonna cry…..</p>
            <p>You're breaking my heart ; (</p>
        </div>
        <iframe id="helloKittyGIF" src="https://tenor.com/view/hellokitty-dancing-cartoon-dance-excited-gif-16073211778928151831" width="300" height="300" frameborder="0" class="giphy-embed" allowfullscreen=""></iframe>
    </div>

    <script>
        let currentMessageIndex = 0;

        function propose(answer) {
            if (answer === 'Yes') {
                document.getElementById('response').innerHTML = 'Yes, I would love to be your Valentine!';
                // Display the GIF
                document.getElementById('helloKittyGIF').style.display = 'block';
            } else {
                showCuteMessages();
                document.getElementById('yesButton').style.fontSize = (16 + currentMessageIndex * 2) + 'px';
            }
        }

        function showCuteMessages() {
            const messages = document.getElementById('cute-messages').children;
            if (currentMessageIndex < messages.length) {
                messages[currentMessageIndex].style.display = 'block';
                currentMessageIndex++;
            }
        }
    </script>
</body>
</html>
