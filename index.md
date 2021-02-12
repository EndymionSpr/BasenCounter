<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>JSON Test</title>
</head>
<body>
    <div id="myData"></div>
    <script>
        fetch('https://panel.sremskisport.pl:444/tt-webAPI/crud/zone/occupancy')
            .then(function (response) {
                return response.json();
            })
            .then(function (data) {
                appendData(data);
            })
            .catch(function (err) {
                console.log('error: ' + err);
            });
        function appendData(data) {
            data = data.result;
            var mainContainer = document.getElementById("myData");
            for (var i = 0; i < data.length; i++) {
                var div = document.createElement("div");
                div.innerHTML = 'Name: ' + data[i].name + ' ' + data[i].qnt;
                mainContainer.appendChild(div);
            }
        }
    </script>
</body>
</html>
