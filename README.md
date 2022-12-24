<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Digital clock</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        body {
            display: flex;
            height: 100vh;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            background: url(https://plus.unsplash.com/premium_photo-1671111151055-da84c16500c4?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHx0b3BpYy1mZWVkfDEyfGJvOGpRS1RhRTBZfHxlbnwwfHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60);
            background-size: cover;
            overflow: hidden;
        }

        h2 {
            text-transform: uppercase;
            letter-spacing: 4px;
            font-size: 30px;
            text-align: center;
            margin-bottom: 10px;
        }

        .clock {
            display: flex;
            position: relative;
        }

        .clock div {
            margin: 5px;


        }

        .clock span {

            width: 130px;
            height: 80px;
            background-color: aqua;
            display: flex;
            justify-content: center;
            font-size: 60px;
            align-items: center;
            font-weight: bolder;
        }

        .clock .text {

            font-size: 20px;
            background-color: blue;
            height: 30px;
            color: white;
        } 
    </style>

</head>

<body>
    <h2>Digital clock</h2>
    <div class="clock">
        <div>
            <span id="hours">00</span>
            <span class="text">hours</span>
        </div>
        <div>
            <span id="minutes">00</span>
            <span class="text">minutes</span>
        </div>
        <div>
            <span id="seconds">00</span>
            <span class="text">seconds</span>
        </div>
        <div>
            <span id="ampm">AM</span>
        </div>
    </div>
    <script>
        const hourEl = document.getElementById("hours");
        const minutEl = document.getElementById("minutes");
        const secondEl = document.getElementById("seconds");
        const ampmel = document.getElementById("ampm");

        function updateClock() {
            let h = new Date().getHours();
            let m = new Date().getMinutes();
            let s = new Date().getSeconds();
            let ampm = "AM";

            if (h > 12) {
                h = h - 12;
                ampm = "PM"
            }
            h = h < 10 ? "0" + h : h;
            m = m < 10 ? "0" + m : m;
            s = s < 10 ? "0" + s : s;
            hourEl.innerText = h;
            minutEl.innerText = m;
            secondEl.innerText = s;
            ampmel, (innerText = ampm);

            setTimeout(() => {
                updateClock()
            }, 1000)
        }
        updateClock();

    </script>
</body>

</html>
