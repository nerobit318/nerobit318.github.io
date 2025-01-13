<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Test Website</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            padding: 20px;
            background-color: #f5f5f5;
            color: #333;
        }
        h1 {
            text-align: center;
        }
        form {
            margin: 20px 0;
        }
        .question {
            margin-bottom: 15px;
        }
        .result {
            margin-top: 20px;
            font-weight: bold;
        }
        button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px 20px;
            cursor: pointer;
            border-radius: 5px;
        }
        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <h1>Test Your Knowledge</h1>
    <form id="testForm">
        <!-- Question 1 -->
        <div class="question">
            <p>1. What is the capital of France?</p>
            <label>
                <input type="radio" name="question1" value="Paris" required>
                A. Paris
            </label><br>
            <label>
                <input type="radio" name="question1" value="London">
                B. London
            </label><br>
            <label>
                <input type="radio" name="question1" value="Rome">
                C. Rome
            </label>
        </div>

        <!-- Question 2 -->
        <div class="question">
            <p>2. What is 5 + 3?</p>
            <label>
                <input type="radio" name="question2" value="7" required>
                A. 7
            </label><br>
            <label>
                <input type="radio" name="question2" value="8">
                B. 8
            </label><br>
            <label>
                <input type="radio" name="question2" value="9">
                C. 9
            </label>
        </div>

        <button type="button" onclick="checkAnswers()">Submit</button>
    </form>

    <div class="result" id="result"></div>

    <script>
        function checkAnswers() {
            const answers = {
                question1: "Paris",
                question2: "8"
            };
            const form = document.getElementById("testForm");
            const resultDiv = document.getElementById("result");
            let score = 0;

            // Check answers
            for (let question in answers) {
                const selectedOption = form.elements[question].value;
                if (selectedOption === answers[question]) {
                    score++;
                }
            }

            // Display result
            resultDiv.textContent = `You scored ${score} out of ${Object.keys(answers).length}.`;
        }
    </script>
</body>
</html>
