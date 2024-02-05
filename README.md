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

        #password-container {
            padding: 50px;
            width: 100vw;
            height: 100vh;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        #password-input {
            margin-bottom: 10px;
        }

        #password-submit {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            background-color: green;
            color: white;
            border: none;
            border-radius: 5px;
            transition: all 0.3s ease;
        }

        #response {
            font-weight: bold;
            margin-top: 20px;
            display: none;
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

        #content-container {
            display: none;
        }
    </style>
</head>

<body>
    <div id="password-container">
        <p>This website is only for Aya. If you are the real one, enter our anniversary:</p>
        <input type="password" id="password-input" placeholder="Enter Anniversary Date (e.g., 12/6/2022)">
        <button id="password-submit" onclick="checkPassword()">Submit</button>
        <p id="response"></p>
    </div>

    <div id="content-container">
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

    <script>
        function checkPassword() {
            const enteredPassword = document.getElementById('password-input').value;
            const correctPassword = '12/6/2022';

            if (enteredPassword === correctPassword) {
                // Correct password, hide password container and show content
                document.getElementById('password-container').style.display = 'none';
                document.getElementById('content-container').style.display = 'block';
            } else {
                // Incorrect password, show alternative message
                document.getElementById('response').style.display = 'block';
                document.getElementById('response').innerHTML = 'You are not my Aya. Get out of here!';
            }
        }

        function propose(answer) {
            // Your propose function logic here
        }
    </script>
</body>

</html>
