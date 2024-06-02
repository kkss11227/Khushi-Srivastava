<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WEATHER APP</title>
    <link rel="stylesheet" href="./style.css">
    <script src="https://cdn.jsdelivr.net/npm/axios@1.6.7/dist/axios.min.js"></script>

</head>
<body>
    <div class="center">

        <div class="logo">
            <img src="./App_Logo.png" alt="Weather Logo" class="app_logo">
        </div>

        <div class="form">
            <input type="text" name="loaction" placeholder="  Enter Location Here..." class="inp">
            <button type="submit" class="btn">Search</button>
            <!-- <form action="#" method="#">
                
            </form> -->
        </div>


        <div class="place"></div>
    </div>

    <ul class="weatherList"></ul>


    <script src="./script.js"></script>
</body>
</html>
