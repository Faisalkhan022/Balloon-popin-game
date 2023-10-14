# Balloon-popin-game
The game you are referring to is called "Balloon Pop." In this game, you need to pop balloons by clicking on them with the mouse cursor. To start the game, you will be required to enter your name.
<!DOCTYPE html>
<html>

<head>
    <title>Balloon Popping</title>
    <style>
        body {
            background-image: url("download\ \(1\).jpeg");
            background-repeat: no-repeat;
            background-position: center;
            background-size: 1500px;
            background-color: black;
            image-resolution: auto;
            color: black;
            text-align: center;
        }

        .container {
            margin-top: 100px;
        }

        .balloon {
            display: inline-block;
            margin: 10px;
            width: 100px;
            height: 150px;
            border-radius: 100%;
            cursor: pointer;
            transition: transform 0.2s ease;
            display: flexbox;
            justify-content: center;
            align-items: center;
            font-size: 20px;
            font-weight: bold;
            color: black;
        }

        /* Define different colors for balloons */
        .balloon:nth-child(1) {
            background-color: rgb(255, 0, 0); 
        }

        .balloon:nth-child(2) {
            background-color: rgb(255, 187, 0); 
        }
        .balloon:nth-child(3) {
            background-color: rgb(30, 255, 0);
        }
        .balloon:nth-child(4) {
            background-color: rgb(0, 255, 187);
        }
        .balloon:nth-child(5) {
            background-color: rgb(0, 34, 255);
        }
        .balloon:nth-child(6) {
            background-color: rgb(166, 0, 255);
        }
        .balloon:nth-child(7) {
            background-color: rgb(255, 0, 89);
        }
        .balloon:nth-child(8) {
            background-color: rgb(64, 0, 23);
        }
        .balloon:nth-child(9) {
            background-color: rgb(241, 118, 118); 
        }
        .balloon:nth-child(10) {
            background-color: rgb(90, 0, 0); 
        }
        .balloon:nth-child(11) {
            background-color: rgb(179, 218, 25); 
        }
        .balloon:nth-child(12) {
            background-color: rgb(65, 27, 126); 
        }
        .balloon:nth-child(13) {
            background-color: rgb(15, 206, 101); 
        }
        .balloon:nth-child(14) {
            background-color: rgb(140, 255, 0); 
        }
        .balloon:nth-child(15) {
            background-color: rgb(213, 134, 163); 
        }
        .balloon:nth-child(16) {
            background-color: rgb(212, 113, 20); 
        }
        .balloon:nth-child(17) {
            background-color: rgb(67, 25, 41); 
        }
        .balloon:nth-child(18) {
            background-color: rgb(23, 34, 140); 
        }
        .balloon:nth-child(19) {
            background-color: rgba(208, 255, 0, 0.478); 
        }
        .balloon:nth-child(20) {
            background-color: rgb(183, 7, 72); 
        }

        .balloon:hover {
            transform: scale(1.6);
        }

        #Message {
            font-size: 24px;
            font-weight: bold;
            color: rgb(0, 30, 255);
            margin-top: 20px;
        }

        #nameInput {
            font-size: 16px;
            margin-bottom: 10px;
        }
    </style>
</head>

<body>
    <div>
        <h1>Welcome to Balloon Pop!</h1><br>
       </div>
       <div> <h2> Instructions:
        - Click on the balloons with your mouse cursor to pop them.
        - Enter your name to start the game.
        
        Enjoy the game!</h2></div> 
       
    <div>
        <h1>popBalloon</h1><br>
        <H2>WELCOME</H2>
    </div>

    <div id="nameInput">
        <label for="name"><h4>Enter your name: </h4></label>
        <input type="text" id="name" placeholder="Your Name">
        <button onclick="startGame()">Start Game</button>
    </div>

    <div class="container" id="gameContainer" style="display:none;">
        <div class="balloon">1</div>
        <div class="balloon">2</div>
        <div class="balloon">3</div>
        <div class="balloon">4</div>
        <div class="balloon">5</div>
        <div class="balloon">6</div>
        <div class="balloon">7</div>
        <div class="balloon">8</div>
        <div class="balloon">9</div>
        <div class="balloon">10</div>
        <div class="balloon">11</div>
        <div class="balloon">12</div>
        <div class="balloon">13</div>
        <div class="balloon">14</div>
        <div class="balloon">15</div>
        <div class="balloon">16</div>
        <div class="balloon">17</div>
        <div class="balloon">18</div>
        <div class="balloon">19</div>
        <div class="balloon">20</div>
    </div>
    <div id="Message"></div>

    <script>
        var balloons = document.getElementsByClassName("balloon");
        var nextNumber = 1;

        function popBalloon() {
            this.style.backgroundColor = "#f1f1f1";
            this.style.border = "none";
            this.innerHTML = "";
            this.removeEventListener("click", popBalloon);
            this.textContent = nextNumber++;

            // Check if all balloons have been popped
            var allPopped = true;
            for (var i = 0; i < balloons.length; i++) {
                if (balloons[i].textContent !== "") {
                    allPopped = false;
                    break;
                }
            }

            if (allPopped) {
                document.getElementById("Message").textContent = "Well played!";
            }
        }

        for (var i = 0; i < balloons.length; i++) {
            balloons[i].addEventListener("click", popBalloon);
        }

        function startGame() {
            var name = document.getElementById("name").value;
            if (name) {
                document.getElementById("nameInput").style.display = "none";
                document.getElementById("gameContainer").style.display = "block";
                document.getElementById("Message").textContent = "Welcome, " + name + "! Let's pop some balloons!";
            } else {
                alert("Please enter your name to start the game.");
            }
        }
    </script>
</body>

</html>
