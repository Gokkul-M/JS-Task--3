# JS-Task--3


Task 0: Duplicate a HTML Div Container

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Duplicate Div Container</title>
</head>
<body>

    <div id="container">
        <p>This is the original div container.</p>
    </div>
    <button onclick="duplicateDiv()">Duplicate Div</button>

    <script>
        function duplicateDiv() {
            let container = document.getElementById("container");
            let duplicate = container.cloneNode(true);
            document.body.appendChild(duplicate);
        }
    </script>

</body>
</html>

Result :

![Screenshot 2024-11-12 092614](https://github.com/user-attachments/assets/b1412de3-1310-42e5-85cb-e0c51639379d)


Task 1: Create a Table with User-Defined Rows and Columns


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Create Table</title>
    <style>
        /* Style for the table */
        table {
            border-collapse: collapse;
            width: 100%;
            margin-top: 10px;
        }

        /* Style for table cells */
        td {
            border: 1px solid #333;
            padding: 8px;
            text-align: center;
        }

        /* Optional styling for inputs and button */
        input, button {
            margin: 5px;
            padding: 5px;
            font-size: 16px;
        }
    </style>
</head>
<body>

    <h3>Build a Table</h3>
    <input type="number" id="rows" placeholder="Number of Rows">
    <input type="number" id="columns" placeholder="Number of Columns">
    <button onclick="buildTable()">Create Table</button>
    <div id="tableContainer"></div>

    <script>
        function buildTable() {
            let rows = document.getElementById("rows").value;
            let columns = document.getElementById("columns").value;
            let tableContainer = document.getElementById("tableContainer");
            tableContainer.innerHTML = "";  // Clear previous table

            let table = document.createElement("table");
            for (let i = 0; i < rows; i++) {
                let row = document.createElement("tr");
                for (let j = 0; j < columns; j++) {
                    let cell = document.createElement("td");
                    cell.innerText = `Row ${i + 1}, Col ${j + 1}`;
                    row.appendChild(cell);
                }
                table.appendChild(row);
            }
            tableContainer.appendChild(table);
        }
    </script>

</body>
</html>

Result :

![Screenshot 2024-11-12 093731](https://github.com/user-attachments/assets/2e09794a-21fb-421b-afb7-6ba3dd1f32dc)


Task 2: Rotate a String


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Rotate String</title>
    <style>
        /* Add some styling to make it visually better */
        input, button {
            margin: 5px;
            padding: 5px;
            font-size: 16px;
        }
        #rotateResult {
            margin-top: 10px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <h3>Rotate a String</h3>
    <input type="text" id="rotateString" placeholder="Enter a String">
    <button onclick="rotateString()">Rotate String</button>
    <div id="rotateResult"></div>

    <script>
        function rotateString() {
            let str = document.getElementById("rotateString").value;
           
            if (str.length === 0) {
                document.getElementById("rotateResult").innerText = "Please enter a string.";
                return;
            }
           
            let rotations = [];
            let rotatedStr = str;
           
            for (let i = 0; i < str.length; i++) {
                rotatedStr = rotatedStr.slice(1) + rotatedStr[0];  
                rotations.push(rotatedStr);
           
            document.getElementById("rotateResult").innerText = "Rotations: " + rotations.join(", ");
        }
    }
    </script>

</body>
</html>

Result :
![Screenshot 2024-11-12 094143](https://github.com/user-attachments/assets/6b39d2e8-e1fe-4003-9edc-23e8f97c7316)



Task 3: Remove a Character at a Specified Position


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Remove Character from Position</title>
</head>
<body>

    <h3>Remove Character at Specified Position</h3>
    <input type="text" id="removeString" placeholder="Enter a String">
    <input type="number" id="removePosition" placeholder="Position to Remove">
    <button onclick="removeCharacter()">Remove Character</button>
    <div id="removeResult"></div>

    <script>
        function removeCharacter() {
            let str = document.getElementById("removeString").value;
            let position = parseInt(document.getElementById("removePosition").value);
            if (position >= 0 && position < str.length) {
                let newString = str.slice(0, position) + str.slice(position + 1);
                document.getElementById("removeResult").innerText = newString;
            } else {
                document.getElementById("removeResult").innerText = "Invalid position";
            }
        }
    </script>

</body>
</html>

Result: 

![Screenshot 2024-11-12 094336](https://github.com/user-attachments/assets/5cc5b93c-3967-4163-a628-a3eb71ae626c)


Task 4: Count the Number of Vowels in a String


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Count Vowels</title>
</head>
<body>

    <h3>Count Vowels</h3>
    <input type="text" id="vowelString" placeholder="Enter a String">
    <button onclick="countVowels()">Count Vowels</button>
    <div id="vowelResult"></div>

    <script>
        function countVowels() {
            let str = document.getElementById("vowelString").value.toLowerCase();
            let count = str.match(/[aeiou]/g)?.length || 0;
            document.getElementById("vowelResult").innerText = `Number of vowels: ${count}`;
        }
    </script>

</body>
</html>

Result:
![Screenshot 2024-11-12 094912](https://github.com/user-attachments/assets/5c12ef8f-a7ee-4b60-979b-21af7e701b2d)



Task 5: Swap the First and Last Elements of an Array


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Swap Array Elements</title>
</head>
<body>

    <h3>Swap First and Last Elements of Array</h3>
    <input type="text" id="arrayInput" placeholder="Enter array elements separated by commas">
    <button onclick="swapElements()">Swap Elements</button>
    <div id="swapResult"></div>

    <script>
        function swapElements() {
            let arrayInput = document.getElementById("arrayInput").value;
            let array = arrayInput.split(',').map(Number);
            if (array.length > 1) {
                let temp = array[0];
                array[0] = array[array.length - 1];
                array[array.length - 1] = temp;
            }
            document.getElementById("swapResult").innerText = `Swapped Array: ${array.join(", ")}`;
        }
    </script>

</body>
</html>


Result :
![Screenshot 2024-11-12 100059](https://github.com/user-attachments/assets/a10b0508-1fc6-4d8a-88da-be04419a6a31)


Task 6) Calculate the Sum of Series: 
n
+
n
2
+
n
4
+
n
8
+
…
n+2n​+4n​+8n​+…


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Sum of Series</title>
</head>
<body>

    <h3>Sum of Series</h3>
    <input type="number" id="number" placeholder="Enter a number">
    <button onclick="sumSeries()">Calculate Sum</button>
    <div id="seriesResult"></div>

    <script>
        function sumSeries() {
            let n = parseFloat(document.getElementById("number").value);
            let sum = 0;
            while (n >= 1) {
                sum += n;
                n = Math.floor(n / 2);
            }
            document.getElementById("seriesResult").innerText = `Sum of Series: ${sum}`;
        }
    </script>

</body>
</html>

Result :

![Screenshot 2024-11-12 101401](https://github.com/user-attachments/assets/e04074a4-28a8-4238-91d7-8138e233eb3a)


Task 7) Find the Longest String from an Array 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Longest String</title>
</head>
<body>

    <h3>Find Longest String</h3>
    <input type="text" id="stringArray" placeholder="Enter strings separated by commas">
    <button onclick="findLongestString()">Find Longest String</button>
    <div id="longestStringResult"></div>

    <script>
        function findLongestString() {
            let array = document.getElementById("stringArray").value.split(',');
            let longest = array.reduce((a, b) => a.length > b.length ? a : b, "");
            document.getElementById("longestStringResult").innerText = `Longest String: ${longest.trim()}`;
        }
    </script>

</body>
</html>

Result :
![Screenshot 2024-11-12 101547](https://github.com/user-attachments/assets/d32db231-0a2c-452c-8aa8-c686343b6cc9)


Task 8) Palindrome Check :


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Palindrome Check</title>
</head>
<body>

    <h3>Check Palindrome</h3>
    <input type="text" id="palindromeInput" placeholder="Enter a string">
    <button onclick="checkPalindrome()">Check Palindrome</button>
    <div id="palindromeResult"></div>

    <script>
        function checkPalindrome() {
            let str = document.getElementById("palindromeInput").value;
            let reversed = str.split('').reverse().join('');
            document.getElementById("palindromeResult").innerText = str === reversed ? "It's a Palindrome" : "Not a Palindrome";
        }
    </script>

</body>
</html>

Result :

![Screenshot 2024-11-12 101744](https://github.com/user-attachments/assets/2263c138-6bf9-4a69-a2ec-1c79db532dc2)


Task 9) Prime Number Check


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Prime Check</title>
</head>
<body>

    <h3>Check Prime Number</h3>
    <input type="number" id="primeInput" placeholder="Enter a number">
    <button onclick="checkPrime()">Check Prime</button>
    <div id="primeResult"></div>

    <script>
        function checkPrime() {
            let num = parseInt(document.getElementById("primeInput").value);
            if (num < 2) {
                document.getElementById("primeResult").innerText = "Not a Prime";
                return;
            }
            for (let i = 2; i <= Math.sqrt(num); i++) {
                if (num % i === 0) {
                    document.getElementById("primeResult").innerText = "Not a Prime";
                    return;
                }
            }
            document.getElementById("primeResult").innerText = "It's a Prime Number";
        }
    </script>

</body>
</html>

Result :

![Screenshot 2024-11-12 102032](https://github.com/user-attachments/assets/b61f35cf-83a0-47a3-b676-a82243a5fd6f)


Task 10) Fibonacci Series

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Fibonacci Series</title>
</head>
<body>

    <h3>Fibonacci Series</h3>
    <input type="number" id="fibonacciInput" placeholder="Enter the number of terms">
    <button onclick="generateFibonacci()">Generate Series</button>
    <div id="fibonacciResult"></div>

    <script>
        function generateFibonacci() {
            let n = parseInt(document.getElementById("fibonacciInput").value);
            let fib = [0, 1];
            for (let i = 2; i < n; i++) {
                fib.push(fib[i - 1] + fib[i - 2]);
            }
            document.getElementById("fibonacciResult").innerText = `Fibonacci Series: ${fib.slice(0, n).join(", ")}`;
        }
    </script>

</body>
</html>

Result :


Task 11) Factorial of a Number :


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Factorial</title>
</head>
<body>

    <h3>Calculate Factorial</h3>
    <input type="number" id="factorialInput" placeholder="Enter a number">
    <button onclick="calculateFactorial()">Calculate Factorial</button>
    <div id="factorialResult"></div>

    <script>
        function calculateFactorial() {
            let num = parseInt(document.getElementById("factorialInput").value);
            let factorial = 1;
            for (let i = 2; i <= num; i++) {
                factorial *= i;
            }
            document.getElementById("factorialResult").innerText = `Factorial: ${factorial}`;
        }
    </script>

</body>
</html>

Result :

![Screenshot 2024-11-12 102216](https://github.com/user-attachments/assets/0b8cec05-9ddf-4274-b515-799bd0c56147)


Task 12) Construct a Pattern


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Pattern Construction</title>
</head>
<body>
    <h3>Construct a Pattern</h3>
    <input type="number" id="patternRows" placeholder="Enter number of rows">
    <button onclick="constructPattern()">Generate Pattern</button>
    <pre id="patternOutput"></pre>

    <script>
        function constructPattern() {
            let rows = document.getElementById("patternRows").value;
            let output = "";
            for (let i = 1; i <= rows; i++) {
                output += "^".repeat(i) + "\n";
            }
            document.getElementById("patternOutput").innerText = output;
        }
    </script>
</body>
</html>

Result :

![Screenshot 2024-11-12 102408](https://github.com/user-attachments/assets/42047fab-94ac-457e-870d-0d2497216766)


Task 13) Pyramid Pattern :


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Pyramid Pattern</title>
</head>
<body>
    <h3>Pyramid Pattern</h3>
    <input type="number" id="pyramidRows" placeholder="Enter number of rows">
    <button onclick="constructPyramid()">Generate Pyramid</button>
    <pre id="pyramidOutput"></pre>

    <script>
        function constructPyramid() {
            let rows = document.getElementById("pyramidRows").value;
            let output = "";
            for (let i = 1; i <= rows; i++) {
                output += " ".repeat(rows - i) + "*".repeat(2 * i - 1) + "\n";
            }
            for (let i = rows - 1; i > 0; i--) {
                output += " ".repeat(rows - i) + "*".repeat(2 * i - 1) + "\n";
            }
            document.getElementById("pyramidOutput").innerText = output;
        }
    </script>
</body>
</html>


Result :

![Screenshot 2024-11-12 102641](https://github.com/user-attachments/assets/0633f5f0-c32a-4714-9bf7-e8db1574443a)


Task 14) Form Validations :


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Form Validation</title>
</head>
<body>
    <h3>Form with Validations</h3>
    <form onsubmit="return validateForm()">
        <input type="text" id="username" placeholder="Username"><br>
        <input type="email" id="email" placeholder="Email"><br>
        <input type="password" id="password" placeholder="Password"><br>
        <button type="submit">Submit</button>
    </form>
    <div id="validationMessage"></div>

    <script>
        function validateForm() {
            let username = document.getElementById("username").value;
            let email = document.getElementById("email").value;
            let password = document.getElementById("password").value;
            if (!username) {
                alert("Username is required.");
                return false;
            }
            if (!email.includes("@")) {
                alert("Please enter a valid email.");
                return false;
            }
            if (password.length < 6) {
                alert("Password must be at least 6 characters.");
                return false;
            }
            alert("Form submitted successfully!");
            return true;
        }
    </script>
</body>
</html>

Result :

![Screenshot 2024-11-12 103407](https://github.com/user-attachments/assets/3595cfe1-b54b-4cde-aa85-68d6cdd58117)


Task 15) JavaScript Calculator


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>JavaScript Calculator</title>
</head>
<body>
    <h3>Calculator</h3>
    <input type="text" id="calcInput" placeholder="Enter calculation">
    <button onclick="calculate()">Calculate</button>
    <div id="calcResult"></div>

    <script>
        function calculate() {
            let expression = document.getElementById("calcInput").value;
            try {
                let result = eval(expression);
                document.getElementById("calcResult").innerText = `Result: ${result}`;
            } catch {
                document.getElementById("calcResult").innerText = "Invalid Expression";
            }
        }
    </script>
</body>
</html>

Result :

![Screenshot 2024-11-12 103653](https://github.com/user-attachments/assets/e81750dd-7ee3-42bc-99c0-60a7620a4340)


Task 16) Task List (Add, Delete) :


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Task List</title>
</head>
<body>
    <h3>Task List</h3>
    <input type="text" id="taskInput" placeholder="Enter task">
    <button onclick="addTask()">Add Task</button>
    <ul id="taskList"></ul>

    <script>
        function addTask() {
            let taskText = document.getElementById("taskInput").value;
            let li = document.createElement("li");
            li.innerText = taskText;
            li.onclick = () => li.remove(); // Click to delete task
            document.getElementById("taskList").appendChild(li);
        }
    </script>
</body>
</html>

Result :

![Screenshot 2024-11-12 104114](https://github.com/user-attachments/assets/f3fff3c5-1b75-443c-ae64-13de09ad14cd)


Task 17) Progress Bar : 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Progress Bar</title>
</head>
<body>
    <h3>Progress Bar</h3>
    <button onclick="increaseProgress()">Increase Progress</button>
    <div style="width: 100%; background-color: lightgray;">
        <div id="progress" style="width: 0; height: 20px; background-color: green;"></div>
    </div>

    <script>
        let progressValue = 0;
        function increaseProgress() {
            if (progressValue < 100) {
                progressValue += 10;
                document.getElementById("progress").style.width = progressValue + "%";
            }
        }
    </script>
</body>
</html>

Result :

![Screenshot 2024-11-12 104216](https://github.com/user-attachments/assets/06172900-1205-4414-b3ab-400627a9c378)


Task 18) Collapsible Container with Content :


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Collapsible Container</title>
</head>
<body>
    <h3>Collapsible Content</h3>
    <button onclick="toggleContent()">Toggle Content</button>
    <div id="collapsibleContent" style="display: none;">
        <p>This is the collapsible content.</p>
    </div>

    <script>
        function toggleContent() {
            let content = document.getElementById("collapsibleContent");
            content.style.display = content.style.display === "none" ? "block" : "none";
        }
    </script>
</body>
</html>

Result :
![Screenshot 2024-11-12 104309](https://github.com/user-attachments/assets/c082e517-897d-4e1f-bf13-775b0c0483cc)

