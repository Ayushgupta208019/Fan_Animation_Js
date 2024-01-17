<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fan Animation</title>
    <style>
        .fan{
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            
        }

        @keyframes fananimation {

            0%{
                transform: rotate(0deg);
            }
            100%{
                transform: rotate(360deg);
            }
            
        }



        img[data-fanblade="fan-blade"]{
            animation-name: fananimation;
            animation-duration: 0s;
            animation-iteration-count: infinite;
            animation-play-state: paused;
            animation-timing-function: linear;
            position: relative;
            height: 400px;
            width: 400px;
        }

        img[data-on-off="off-button"]{
            position: relative;
            height: 50px;
            width: 50px;
            margin-top: 50px;
            cursor: pointer;
            top: 25px;
        }
        button{
        height: 50px;
        width: 50px;
        margin-left: 5px;
        cursor: pointer;
        margin-top: 100px;
        margin-left: 20px;
        border-radius: 50%;
        background-color: greenyellow;
        font-size: 19px;
        font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
        color: red;
    }

    button:hover{
        background-color: gold;
    }
       #controls{
        display: flex;
        align-items: center;
        justify-content: center;
        margin-top: 100px;
        
       }

    </style>

    <script>
        function x(elem){
            return document.querySelector(elem);
        }

        function fan(value){
            if(value == 0){
                //alert("0 is pressed");
                x('[data-fanblade="fan-blade"]').style.animationPlayState= 'paused';
                x('[data-on-off="off-button"]').setAttribute('src','img/off.png');

            }
            else if(value == 1){
                //alert("1 is pressed"); testig of value 1 function result == Passed
                x('[data-fanblade="fan-blade"]').style.animationPlayState= 'running';
                x('[data-fanblade="fan-blade"]').style.animationDuration= '1s';
                x('[data-on-off="off-button"]').setAttribute('src','img/on.png');
            }
            else if(value == 2){
                //alert("2 is pressed"); testig of value 2 function result == Passed
                x('[data-fanblade="fan-blade"]').style.animationPlayState= 'running';
                x('[data-fanblade="fan-blade"]').style.animationDuration= '0.5s';
                x('[data-on-off="off-button"]').setAttribute('src','img/on.png');
            }
            else{
                //alert("3 is pressed"); testig of value 3 function result == Passed
                x('[data-fanblade="fan-blade"]').style.animationPlayState= 'running';
                x('[data-fanblade="fan-blade"]').style.animationDuration= '0.1s';
                x('[data-on-off="off-button"]').setAttribute('src','img/on.png');
            }
        }
    </script>
</head>
<body>
    <div class="fan">
        <img src="img/fan-blades-png.png" alt="" data-fanblade="fan-blade">
    </div>
    <div id="controls">
        <img src="img/off.png" data-on-off="off-button" onclick="fan(0)" id="onoff">
        <button onclick="fan(1)">1</button>
        <button onclick="fan(2)">2</button>
        <button onclick="fan(3)">3</button>
    </div>
</body>
</html>
