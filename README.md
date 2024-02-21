# Calculator
<!DOCTYPE html>

<html>
<head>
  <link rel="stylesheet" href="styles.css">
  <style>
    

*
{
  margin:0;
  padding:0;
  box-sizing: border-box;
}
body{
  
  height: 100%;
  width:100vh;
  justify-content: center;
  display:flex;
  align-items: center;
  background-color: #0a0a0a;
}
.calculator
{
  border: 1px solid #71337a;
  padding:20px;
  border-radius: 16px;
  background: transparent;
  box-shadow: 0 3px 15px rgba(113,115 119,0.5);
}
input{
  height:80px;
  width:320px;
  margin:10px;
  border:none;
  box-shadow: 0 3px 15px rgba(84,84,84,0.1);
  text-align: right;
  font-size: 40px;
  cursor:pointer;
  padding:24px;
  color:#ffffff;
  background: transparent;
  
}
input::placeholder
{
  color:#ffffff;
}
button
{
  height:60px;
  width:60px;
  border:none;
  color:#ffffff;
  cursor:pointer;
  border-radius: 50%;
  font-size: 20px;
  background: transparent;
  margin :10px;
  box-shadow: 8px 8px 15px rgba(255,255,255,0.1);
  
}
.ebtn
{
  background-color:#fb7c14;
}
.op
{
  color:#6dee0a;
}
  </style>
  <meta http-equiv="CONTENT-TYPE" content="text/html; charset=UTF-8">
  <title>Hello, World!</title>
</head>
<body>
  <div class="calculator">
    <input type="text" placeholder="0" id="inputbox">
    <div>
      <button class="op">AC</button>
      <button class="op">DEL</button>
      <button class="op">%</button>
      <button class="op">/</button>
    </div>
     <div>
      <button>7</button>
      <button>8</button>
      <button>9</button>
      <button class="op">*</button>
    </div>
     <div>
      <button>4</button>
      <button>5</button>
      <button>6</button>
      <button class="op">-</button>
    </div>
     <div>
      <button>1</button>
      <button>2</button>
      <button>3</button>
      <button class="op">+</button>
    </div>
    <div>
      <button class="op">+/-</button>
      <button>0</button>
      <button>.</button>
      <button class="ebtn">=</button>
    </div> 
  </div>
  
  <script>
  
let input = document.getElementById('inputbox');
let buttons = document.querySelectorAll('button');

let string = "";
let arr = Array.from(buttons);
arr.forEach(button => {
    button.addEventListener('click', (e) => {
        if (e.target.innerHTML == '=') {
            string = eval(string);
            input.value = string;
        } else if (e.target.innerHTML == 'AC') {
            string = "";
            input.value = string;
        } else if (e.target.innerHTML == 'DEL') {
            string = string.substring(0, string.length - 1);
            input.value = string;
        } else {
            string += e.target.innerHTML;
            input.value = string;
        }
    })
})

  </script>
</body>
</html>
