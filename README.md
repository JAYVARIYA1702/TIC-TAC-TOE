# TIC-TAC-TOE
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TIC TAC TOE</title>
    <link rel="stylesheet" href="css/style.css">
  <style>
    *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    text-decoration: none;
}

body{
    font-family: Arial, sans-serif;
    background-color: #000000;
    margin: 0;
    padding: 0;
}
.w-100{
    width: 100%;
}

.w-1140{
    width: 1140px;
    margin: auto;
}

h1{
    padding: 100px;
    color: white;
    text-align: center;
}

.main {
    display: flex;
    justify-content: center;
}

.main-box {
    width: 300px;
    height: 300px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5px;
}

.sub-box {
    display: flex;
    gap: 10px;
}

.box {
    height: 80px;
    width: 80px;
    font-size: 30px;
    font-weight: bold;
    background-color: antiquewhite;
    border: 2px solid black;
    border-radius: 10px;
    text-align: center;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
}

.box:hover {
    
    transform: scale(1.1);
    box-shadow: 0 4px 10px rgba(245, 231, 44, 0.784);
    transition: background-color 0.3s ease, transform 0.3s ease, box-shadow 0.3s ease;
    border-color: antiquewhite;
}
</style>
</head>
<body>
    <h1>TIC TAC TOE</h1>
    <div class="main">
        <div class="main-box">
            <div class="sub-box">
                <div class="box" onclick="xyz(this)"></div>
                <div class="box" onclick="xyz(this)"></div>
                <div class="box" onclick="xyz(this)"></div>
            </div>
            <div class="sub-box">
                <div class="box" onclick="xyz(this)"></div>
                <div class="box" onclick="xyz(this)"></div>
                <div class="box" onclick="xyz(this)"></div>
            </div>
            <div class="sub-box">
                <div class="box" onclick="xyz(this)"></div>
                <div class="box" onclick="xyz(this)"></div>
                <div class="box" onclick="xyz(this)"></div>
            </div>
        </div>
    </div>

    <script>
        let player = "X";
        function xyz(box) {
            if (box.innerHTML === "") {
                box.innerHTML = player;
                player = (player === "X") ? "O" : "X";
            }
            win()
        }
        function win() {
            const winPatterns = [
                [0, 1, 2],
                [3, 4, 5],
                [6, 7, 8],
                [0, 3, 6],
                [1, 4, 7],
                [2, 5, 8],
                [0, 4, 8],
                [2, 4, 6],
            ];
            for (let i = 0; i < winPatterns.length; i++) {
                const [a, b, c] = winPatterns[i];
                if (document.querySelectorAll(".box")[a].innerHTML === document.querySelectorAll(".box")[b].innerHTML
                    && document.querySelectorAll(".box")[b].innerHTML === document.querySelectorAll(".box")[c].innerHTML
                    && document.querySelectorAll(".box")[a].innerHTML !== "") {
                    alert("Player " + document.querySelectorAll(".box")[a].innerHTML + " wins!");

                }
            }
        }






    </script>

</body>
</html>
