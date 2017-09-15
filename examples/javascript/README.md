# SimpleMaskMoney Exemple Javascript
First, install it.
```shell
  npm i simple-mask-money --save
```
Then, use it as follows:
```html
  <body>
    <!-- 
      inner html you put type text and inputmode numeric to mobile show numeric keyboard
     -->
    <input inputmode="numeric" oninput="this.value = SimpleMaskMoney.format(this.value)" onkeyup="send()" value="0,00"><br>

    <script src="./node_modules/simple-mask-money/lib/simple-mask-money.js"></script>
    <script>
      // select the element 
      let input = document.getElementsByTagName('input')[0];

      // configuration  
      SimpleMaskMoney.args = {
        preffix: '',
        suffix: '',
        fixed: true,
        fractionDigits: 2,
        decimalSeparator: ',',
        thousandsSeparator: '.',
        autoCompleteDecimal: false
      };

      // Your send method 
      send = () => {

        // This method return value of your input in format number to save in your database
        SimpleMaskMoney.formatToNumber(input.value);
      }
    </script>
  </body>
```
