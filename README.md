// first question
import java.util.ArrayList;
import java.util.Collections;
import java.util.Scanner;
import java.util.HashSet;

public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> array = new ArrayList<>();
        for (int i = 1; i <= 7; i++) {
            array.add(i);
        }
        Collections.shuffle(array);
        System.out.println("Shuffled Array: " + array);
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a Roman numeral: ");
        String romanNumeral = scanner.nextLine();
        int romanToIntegerResult = romanToInteger(romanNumeral);
        System.out.println("Roman to Integer: " + romanToIntegerResult);
        System.out.print("Enter a sentence: ");
        String inputSentence = scanner.nextLine().toLowerCase();
        boolean isPangram = isPangram(inputSentence);
        if (isPangram) {
            System.out.println("The input is a pangram.");
        } else {
            System.out.println("The input is not a pangram.");
        }
    }
    public static int romanToInteger(String s) {
        java.util.HashMap<Character, Integer> romanMap = new java.util.HashMap<>();
        romanMap.put('I', 1);
        romanMap.put('V', 5);
        romanMap.put('X', 10);
        romanMap.put('L', 50);
        romanMap.put('C', 100);
        romanMap.put('D', 500);
        romanMap.put('M', 1000);

        int result = 0;
        int prevValue = 0;

        for (int i = s.length() - 1; i >= 0; i--) {
            int value = romanMap.get(s.charAt(i));
            if (value < prevValue) {
                result -= value;
            } else {
                result += value;
            }
            prevValue = value;
        }
        return result;
    }
    public static boolean isPangram(String input) {
        HashSet<Character> alphabetSet = new HashSet<>();
        for (char c : input.toCharArray()) {
            if (Character.isLetter(c)) {
                alphabetSet.add(c);
            }
        }
        return alphabetSet.size() == 26;
    }
}
// second question
function reverseWords(sentence) {
  const words = sentence.split(' ');
  const reversedWords = words.map(word => {
    return word.split('').reverse().join('');
  });
  return reversedWords.join(' ');
}

const inputSentence = "This is a sunny day";
const reversedSentence = reverseWords(inputSentence);
console.log(reversedSentence);

const numbers = [5, 2, 9, 1, 5, 6];
numbers.sort((a, b) => b - a); // Sort in descending order
console.log(numbers);

// third question
<div id=”calcContainer”>
  <form name=”calculator”>
    <div class=”result-clear”>
      <input type=”text” class=”result” name=”answer” readonly />
      <input type=”button” class=”clear” value=” AC ” onclick=”calculator.answer.value = ”” />
    </div>
    <div class=”grid-buttons”>
      <input type=”button” value=”9″ onclick=”calculator.answer.value += ‘9’” />
      <input type=”button” value=”8″ onclick=”calculator.answer.value += ‘8’” />
      <input type=”button” value=”7″ onclick=”calculator.answer.value += ‘7’” />
      <input type=”button” value=”+” onclick=”calculator.answer.value += ‘+'” class=”math” />
      <br />
      <input type=”button” value=”4″ onclick=”calculator.answer.value += ‘4’” />
      <input type=”button” value=”5″ onclick=”calculator.answer.value += ‘5’” />
      <input type=”button” value=”6″ onclick=”calculator.answer.value += ‘6’” />
      <input type=”button” value=”&minus;” onclick=”calculator.answer.value += ‘-‘” class=”math” />
      <br />
      <input type=”button” value=”1″ onclick=”calculator.answer.value += ‘1’” />
      <input type=”button” value=”2″ onclick=”calculator.answer.value += ‘2’” />
      <input type=”button” value=”3″ onclick=”calculator.answer.value += ‘3’” />
      <input type=”button” value=”&#247;” onclick=”calculator.answer.value += ‘/'” class=”math” />
      <br />
      <input type=”button” value=”.” onclick=”calculator.answer.value += ‘.'” />
      <input type=”button” value=”0″ onclick=”calculator.answer.value += ‘0’” />
      <input type=”button” value=”=” onclick=”calculator.answer.value = eval(calculator.answer.value)” />
      <input type=”button” value=”&#215;” onclick=”calculator.answer.value += ‘*'” class=”math” />
    </div>
  </form>
</div>

@import url(‘https://fonts.googleapis.com/css?family=Roboto’);
body {
  background: #BDBDBD;
}
#calcContainer {
  width: 80%;
  height: auto;
  box-shadow: 0.5em 0.5em 1.2em rgba(0, 0, 0, 0.2);
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
  background: #ffffff;
}

.result-clear {
  display: flex;
  margin: 0;
  padding: 0;
}

.result-clear input[type=text].result {
  width: 72%;
  height: 60px;
  font-size: 1.4em;
  font-family: ‘Roboto’, sans-serif;
  display: block;
  border: 0;
  padding-top: 1%;
  padding-left: 5%;
}

.grid-buttons {
  margin: 0;
  justify-content: space-between;
  align-items: center;
  background: #212121;
  display: flex;
  flex-wrap: wrap;
}
input[type=button] {
  font-family: ‘Roboto’, sans-serif;
  font-size: 1.2em;
  font-weight: 500;
  color: #ffffff;
  background: #212121;
  border: 2px solid #212121;
  flex-grow: 1;
  width: 25%;
  height: auto;
  padding: 4%;
  border: 0;
  align-items: center;
  text-align: center;
}
input[type=button]:focus {
  outline: 0;
}
input[type=button].clear {
  background: #009688;
  border: 2px solid #009688;
  width: 25.5%;
  font-size: 20px;
}
.grid-buttons input[type=button].math {
  background: #757575;
  border: 2px solid #757575;
}

.grid-buttons input[type=button]:hover,
input[type=button].clear:hover {
  border: 2px solid #00BCD4;
  transition: 0.3s ease;
  background: #00BCD4;
}

// third question (B)

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="styles.css">
    <title>Coustomer Survey Form</title>
</head>
<body>
    <header>
        <div>
            <div class="form">
            <h1>Customer Survey Form</h1>
            </div>
        </div>
    </header>
    <div class="main-section">
        <div class="box">
            <form id="form">
                <div class="name">
                    <label>Name</label>
                    <input type="text" id="input" name="txt">
                </div>
                <br>
                <div class="email">
                    <label>Email</label>
                    <input type="text" name="ename">
                </div>
                <br>
                <div class="radio">
                    <label>Is this first time you are using our products & service?</label>
                    <br>
                    <label><input type="radio" name="r1" value="Yes">Yes</label>
                    <label><input type="radio" name="r1" value="No">No</label>
                </div>
                <br>
                <div class="radio">
                    <label>Would you suggestion to your friends and colleague?</label>
                    <br>
                    <label><input type="radio" name="r2" value="Yes">Yes</label>
                    <label><input type="radio" name="r2" value="No">No</label>
                </div>
                <br>
                <div class="radio">
                    <label>How satisfied are you with our company overall?</label>
                    <br>
                    <label><input type="radio" name="r3" value="satisfied">satisfied</label>
                    <label><input type="radio" name="r3" value="Undecided">Undecided</label>
                    <label><input type="radio" name="r3" value="Unsatisfied">Unsatisfied</label>
                </div>
                <br>
                <div class="suggestion">
                    <label>Do you have suggestion to improve our services?</label>
                    <textarea rows="6" cols="75"></textarea>
                </div>
                <br>
                <div class="submit">
                    <input type="submit" value="submit">
                </div>
            </form>
        </div>
    </div>
    <div class="popup" id="popup">
        <div class="popup-content" id="popupContent">
            <span class="close" onclick="closePopup()">&times;</span>
            <h2>Survey Form Data</h2>
            <div id="popupData"></div>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>

body{
    background-color: rgb(10, 151, 222);
}

.form h1{
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100px;
    width: 100%;
    font-size: 3rem;
    
}

.box{
    height: 600px;
    max-width: 600px;
    background-color: white;
    margin: 50px auto;
    padding: 30px 20px;
}

.name label{
    display: block;
    margin-bottom: 10px;
}
.email label{
    display: block;
    margin-bottom: 10px;
}
.radio input[type="radio"]{
    display: inline-block;
    width: auto;
}
.submit input{
    color: rgb(10, 151, 222);
}

body {
    font-family: Arial, sans-serif;
}


.popup {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    justify-content: center;
    align-items: center;
}

.popup-content {
    background-color: #fff;
    padding: 20px;
    border-radius: 5px;
    box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.5);
}

.close {
    float: right;
    cursor: pointer;
    font-size: 24px;
    font-weight: bold;
}

.close:hover {
    color: #ff0000;
}

function submitForm() {
    
    const Name = document.getElementById('Name').value;
    const email = document.getElementById('eName').value;
    const r1 = document.getElementById('r1').value;
    const r2 = document.getElementById('r2').value;
    const r3 = document.getElementById('r3').value;


   

   
    const popupContent = document.getElementById('popupData');
    popupContent.innerHTML = `
        <p><strong>Name:</strong> ${Name}</p>
        <p><strong>ename:</strong> ${ename}</p>
        <p><strong>Is this first time you are using our products & service?:</strong> ${r1}</p>
        <p><strong>Would you suggestion to your friends and colleague?</strong> ${r2}</p>
        <p><strong>How satisfied are you with our company overall?</strong> ${r3}</p>
        <p><strong>Do you have suggestion to improve our services?</strong> ${text}</p>
        
    `;

    
    const popup = document.getElementById('popup');
    popup.style.display = 'block';
}

function resetForm() {
    
    document.getElementById('surveyForm').reset();
}

function closePopup() {
    const popup = document.getElementById('popup');
    popup.style.display = 'none';
    resetForm();
}
