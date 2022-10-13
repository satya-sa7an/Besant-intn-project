# My-project - clock
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Clock</title>
    <style>
        body{
            background: black;
            font-family: system-ui;
            text-align: center;
            color: greenyellow;
        }
    </style>
</head>
<body>
    <div id="clock" onload="currentTime()"></div>


    <script >
        function currentTime(){
            let date = new Date();
            let hh = date.getHours();
            let mm = date.getMinutes();
            let ss = date.getSeconds();
            let session = "AM";


            if (hh === 0){
                hh = 12;    
            }
            if (hh > 12){
                (hh - 12) = hh;
                session = "PM";
            }

            hh = (hh < 10) ? "0" + hh : hh;
            mm = (mm < 10) ? "0" + mm : mm;
            ss = (ss < 10) ? "0" + ss : ss;

            let time = hh + ":" + mm + ":" + ss + " " + session;

            document.getElementById("clock").innerText = time;
            let t = setTimeout(function(){currentTime()},1000);

        }

        currentTime();
    </script>
</body>
</html>
