# guess_the_number
Certainly! Let's break down the provided HTML, CSS, and JavaScript code step by step:

### HTML:
```html
<h1>Guess the Number Challenge!</h1>
<h4>Enter any number from 1 to 10</h4>
<input type="text" id="num">
<button onclick="check()" id="myBtn"> Check</button>
<p id="result">You are Wrong/Right</p>
<br>
<p id="score">Score: 10</p>
```
- This section includes the basic structure of the webpage.
- It consists of a heading, an instruction, an input field for entering a number, a button to check the number, a paragraph for displaying the result (whether the guess is right or wrong), and another paragraph for displaying the score.

### JavaScript:
```javascript
var totalscore=10;

function check() {
    var inp = document.getElementById("num");
    var score = document.getElementById("score");
    var num = Number(inp.value);
    var randomNum = Math.floor(Math.random() * 10) + 1;
    var result = document.getElementById("result");
    
    if (randomNum === num) {
        result.textContent = "You are Right";
        document.getElementById("myBtn").disabled = true;
        alert("You Won!");
    } else {
        totalscore = totalscore - 1;
        score.textContent = "Score: " + totalscore;
        result.textContent = "You are Wrong";
    }

    if (totalscore === 0) {
        alert("End of Game....YOU LOST");
        document.getElementById("myBtn").disabled = true;
    }
}
```
- The JavaScript code defines a function `check()` which is called when the "Check" button is clicked.
- It retrieves the user input from the input field with the id `num`.
- It generates a random number between 1 and 10 using `Math.random()` and `Math.floor()` functions.
- It compares the user's input with the generated random number.
- If the guess is correct, it updates the result paragraph to "You are Right", disables the button, and alerts the user about winning.
- If the guess is incorrect, it decreases the score, updates the score paragraph, and updates the result paragraph to "You are Wrong".
- It also checks if the score has reached zero, in which case it alerts the user about the end of the game and disables the button.

### CSS:
```css
body {
    font-family: 'Arial', sans-serif;
    background-color: #f4f4f4;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
}

h1 {
    color: #333;
    text-align: center;
    margin-bottom: 20px;
}

#num {
    padding: 8px;
    font-size: 16px;
    margin-bottom: 10px;
}

#myBtn {
    padding: 10px 20px;
    font-size: 16px;
    background-color: #4caf50;
    color: white;
    border: none;
    cursor: pointer;
}

#result {
    font-size: 18px;
    text-align: center;
    color: #333;
    margin-top: 20px;
}

#score {
    font-size: 16px;
    text-align: center;
    color: #333;
    margin-top: 10px;
}
```
- This section contains the CSS styles to make the webpage visually appealing.
- It styles the body, headings, input field, button, and result and score paragraphs.
- It applies a flexbox layout to center the content vertically and horizontally on the page.
- It sets background color, font sizes, colors, and margins to achieve a neat appearance.

Overall, this code implements a simple guessing game where the user needs to guess a random number between 1 and 10. They get a score based on their guesses, and they win if they guess the correct number within the given attempts.
