# calculator
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculator</title>
    <style>
        *{
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'poppins',sans-serif;
        }
        body{
            background-color:  #22085d;
            overflow-y: hidden;

        }
        .container{
            background-color: hsl(0, 0%, 12%);
            margin: 30px auto;
            width: 500px;
            padding: 20px;
            border: none;
            border-radius: 10px;
            box-shadow: 10px 10px 10px 0px rgb(152, 62, 62) ;
            
        }
        input{
            text-align: right;
            width: 100%;
            padding: 10px;
            margin-bottom: 20px;
            height: 70px;
            background-color: #00430a43;
            font-size: 50px;
            color: whitesmoke;
            border: none;
            border-radius: 10px;
        }
        .button.clear{
            height: 60px;
            width: 60px;
            border: none;
            border-radius: 50px;
            background-color: hsl(0, 100%, 58%);
            font-weight: bolder;
            font-size: xx-large;
            color: white;
            margin: 20px;
            box-shadow: -4px -2px 10px    rgb(251, 82, 82) ;
            margin-right: 30px;
            cursor: pointer;
            opacity: 1;
        }
        .button.operator{
            height: 60px;
            width: 60px;
            border: none;
            border-radius: 50px;
            background-color: hsl(0, 0%, 30%);
            font-weight: 600;
            font-size:xx-large ;
            color: rgb(255, 251, 15);
            margin: 20px;
            box-shadow: -4px -2px 10px     hsl(0, 81%, 71%); 
            margin-right: 30px;
            cursor: pointer;
        } 
        .float1{
            float: right;
            height: 160px;
            width: 60px;
            border: none;
            border-radius: 20px;
            background-color: hsl(0, 0%, 30%);
            font-weight: bolder;
            font-size: xx-large;
            color: rgb(255, 251, 15);
            margin-right: 37px;
            margin-top: 20px;
            box-shadow: -4px -2px 10px     hsl(0, 81%, 71%); 
            cursor: pointer;
        }
        .float2{
            float: right;
            height: 160px;
            width: 60px;
            border: none;
            border-radius: 20px;
            background-color: hsl(100, 75%, 44%);
            font-weight: bolder;
            font-size: xx-large;
            color: rgb(249, 249, 249);
            margin-right: 37px;
            margin-top: 20px;
            box-shadow: -4px -2px 10px     hsla(109, 50%, 48%, 0.601); 
            cursor: pointer;
        }
        .button.number{
            height: 60px;
            width: 60px;
            border: none;
            border-radius: 50px;
            background-color: hsl(0, 0%, 30%);
            font-weight: 600;
            font-size:xx-large ;
            color: whitesmoke;
            margin: 20px;
            box-shadow: -4px -2px 10px     hsl(0, 81%, 71%); 
            margin-right: 30px;
            cursor: pointer;
        }
        .button.zero{
            height: 60px;
            width: 173px;
            border: none;
            border-radius: 20px;
            background-color: hsl(0, 0%, 30%);
            font-weight: 600;
            font-size:xx-large ;
            color: whitesmoke;
            margin: 20px;
            box-shadow: -4px -2px 10px     hsl(0, 81%, 71%); 
            margin-right: 30px;
            cursor: pointer;
        }
        .button.clear:hover{
            opacity: 0.8;
        }
        .button.clear:active{
            background-color: rgb(148, 11, 11);
        }
        .button.number:hover, .button.operator:hover, .button.zero:hover, .float1:hover{
            background-color: hsl(0, 0%, 40%);
        }
        .button.number:active, .button.operator:active,.button.zero:active, .float1:active{
            background-color: hsl(0, 57%, 17%);
        }
        .float2:hover{
            background-color: rgb(52, 223, 69);
        }
        .float2:active{
            background-color: rgb(56, 215, 128);
        }
        h2{
            font-family: "Rock Salt", cursive;
            color: rgb(90, 143, 125);
            margin-top: -15px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>AJ</h2>
            <div>
                <input id="display"  disabled placeholder="0">
            </div>
            <div>
                <button onclick="clearDisplay('')" class="button clear">C</button>
                <button onclick="addToDisplay('/')" class="button operator">/</button>
                <button onclick="addToDisplay('*')" class="button operator">*</button>
                <button onclick="addToDisplay('-')" class="button operator">-</button>
            </div>
            <div >
                <button onclick="addToDisplay('+')" class="button float1">+</button>
                <button onclick="addToDisplay('7')" class="button number">7</button>
                <button onclick="addToDisplay('8')" class="button number">8</button>
                <button onclick="addToDisplay('9')" class="button number">9</button>
                <br>
                <button onclick="addToDisplay('4')" class="button number">4</button>
                <button onclick="addToDisplay('5')" class="button number">5</button>
                <button onclick="addToDisplay('6')" class="button number">6</button>
            </div>
            <div >
                <button onclick="Result('=')"       class="button float2">=</button>
                <button onclick="addToDisplay('1')" class="button number">1</button>
                <button onclick="addToDisplay('2')" class="button number">2</button>
                <button onclick="addToDisplay('3')" class="button number">3</button>
                <br>
                <button onclick="addToDisplay('0')" class="button zero">0</button>
                <button onclick="addToDisplay('.')" class="button number">.</button>
               
            </div>
        </div>
        <script>
            const display = document.getElementById('display');
            let resultDisplayed = true;


            function addToDisplay(input){
                if (resultDisplayed) {
                clearDisplay();
                resultDisplayed = false;
                }
                display.value +=input;
            }
            
            function clearDisplay(){
                display.value = "";
            }

            function Result(){
                try{
                    display.value = eval(display.value);
                    resultDisplayed = true;
                }
                catch(error){
                    display.value = 'Error';
                }
            }
        </script>
</body>
</html>
