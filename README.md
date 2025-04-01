<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>그림체 마스터 퀴즈!</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            background-color: #f8f8f8;
            color: #333;
            margin: 0;
            padding: 0;
        }
        .container {
            max-width: 100%;
            margin: 0 auto;
            padding: 20px;
        }
        .quiz-title {
            font-size: 24px;
            font-weight: bold;
            text-align: center;
            margin-bottom: 30px;
        }
        .quiz-question {
            font-size: 18px;
            margin-bottom: 15px;
        }
        .quiz-options {
            list-style-type: none;
            padding: 0;
        }
        .quiz-option {
            margin-bottom: 10px;
            font-size: 16px;
            background-color: #fff;
            padding: 10px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        .quiz-option:hover {
            background-color: #e2e2e2;
        }
        .quiz-image {
            width: 100%;
            max-width: 300px;
            height: auto;
            margin-bottom: 20px;
        }
        .result {
            margin-top: 20px;
            font-size: 18px;
            color: #006400;
        }
        .feedback {
            margin-top: 15px;
            font-size: 16px;
            color: #ff6347;
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="quiz-title">그림체 마스터 퀴즈!</div>

        <div class="quiz-question">
            <p>문제 1: 아래 그림체에 맞는 애니메이션을 고르세요!</p>
            <img src="https://via.placeholder.com/300" class="quiz-image" alt="문제 1 이미지">
            <ul class="quiz-options">
                <li class="quiz-option" onclick="checkAnswer(1, 'A')">A) 심슨</li>
                <li class="quiz-option" onclick="checkAnswer(1, 'B')">B) 짱구는 못말려</li>
                <li class="quiz-option" onclick="checkAnswer(1, 'C')">C) 진격의 거인</li>
                <li class="quiz-option" onclick="checkAnswer(1, 'D')">D) 귀멸의 칼날</li>
            </ul>
        </div>

        <div class="quiz-question">
            <p>문제 2: 아래 그림체에 맞는 애니메이션을 고르세요!</p>
            <img src="https://via.placeholder.com/300" class="quiz-image" alt="문제 2 이미지">
            <ul class="quiz-options">
                <li class="quiz-option" onclick="checkAnswer(2, 'A')">A) 심슨</li>
                <li class="quiz-option" onclick="checkAnswer(2, 'B')">B) 짱구는 못말려</li>
                <li class="quiz-option" onclick="checkAnswer(2, 'C')">C) 진격의 거인</li>
                <li class="quiz-option" onclick="checkAnswer(2, 'D')">D) 귀멸의 칼날</li>
            </ul>
        </div>

        <div class="quiz-question">
            <p>문제 3: 아래 그림체에 맞는 애니메이션을 고르세요!</p>
            <img src="https://via.placeholder.com/300" class="quiz-image" alt="문제 3 이미지">
            <ul class="quiz-options">
                <li class="quiz-option" onclick="checkAnswer(3, 'A')">A) 심슨</li>
                <li class="quiz-option" onclick="checkAnswer(3, 'B')">B) 짱구는 못말려</li>
                <li class="quiz-option" onclick="checkAnswer(3, 'C')">C) 진격의 거인</li>
                <li class="quiz-option" onclick="checkAnswer(3, 'D')">D) 귀멸의 칼날</li>
            </ul>
        </div>

        <div class="quiz-question">
            <p>문제 4: 아래 그림체에 맞는 애니메이션을 고르세요!</p>
            <img src="https://via.placeholder.com/300" class="quiz-image" alt="문제 4 이미지">
            <ul class="quiz-options">
                <li class="quiz-option" onclick="checkAnswer(4, 'A')">A) 심슨</li>
                <li class="quiz-option" onclick="checkAnswer(4, 'B')">B) 짱구는 못말려</li>
                <li class="quiz-option" onclick="checkAnswer(4, 'C')">C) 진격의 거인</li>
                <li class="quiz-option" onclick="checkAnswer(4, 'D')">D) 귀멸의 칼날</li>
            </ul>
        </div>

        <div id="feedback" class="feedback"></div>
        <div id="result" class="result"></div>
    </div>

    <script>
        let correctAnswers = ['A', 'B', 'C', 'D'];
        let userAnswers = [];
        let score = 0;

        function checkAnswer(question, answer) {
            let feedback = '';
            if (answer === correctAnswers[question - 1]) {
                score++;
                feedback = '정답! ' + getAnimeFeedback(question);
            } else {
                feedback = '오답! ' + getAnimeFeedback(question);
            }
            userAnswers.push({question, answer});
            document.getElementById('feedback').innerText = feedback;
            if (question === 4) {
                showResult();
            }
        }

        function getAnimeFeedback(question) {
            const animeFeedbacks = {
                1: "심슨! 'D'라고 외쳤지?",
                2: "짱구는 못말려! '자~나와라!' 라고 했어!",
                3: "진격의 거인! '난 그들을 죽일 수밖에 없어!'라며!",
                4: "귀멸의 칼날! '이곳에서 죽을 수 없다!' 라고 외쳐봤지?"
            };
            return animeFeedbacks[question] || '';
        }

        function showResult() {
            let nickname = '';
            if (score === 4) {
                nickname = '애니마스터';
            } else if (score === 3) {
                nickname = '애니메이션 고수';
            } else if (score === 2) {
                nickname = '애니메이션 초보';
            } else {
                nickname = '애니메이션 팬';
            }
            document.getElementById('result').innerText = `결과: ${score}/4! 너는 ${nickname}야!`;
        }
    </script>
</body>
</html>
