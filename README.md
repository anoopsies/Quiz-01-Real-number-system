# Quiz-01-Real-number-system(by Anoop S V)
<html lang="en">
<head>
  <meta charset="UTF-8">
  <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
  <style>
    body { font-family: Arial, sans-serif; margin: 20px; }
    .question { margin-bottom: 20px; }
    button { padding: 10px; background: #007BFF; color: white; border: none; cursor: pointer; border-radius: 5px; }
    button:hover { background: #0056b3; }
    #result { margin-top: 20px; font-weight: bold; }
    .correct { color: green; }
    .incorrect { color: red; }
    .explanation { font-style: italic; color: #444; }
  </style>
</head>
<body>
  <form id="quizForm">

    <div class="question">
      <p>1. For every \(a,b \in \mathbb{R}\), we say that \(a < b \) if:</p>
      <label><input type="radio" name="q1" value="a"> \(b-a \in \mathbb{R}^+\)</label><br>
      <label><input type="radio" name="q1" value="b"> \(a-b \in \mathbb{R}^+\)</label><br>
      <label><input type="radio" name="q1" value="c"> \(a=b\)</label><br>
      <label><input type="radio" name="q1" value="d"> None of these</label>
    </div>

    <div class="question">
      <p>2. Which of the following is true?</p>
      <label><input type="radio" name="q2" value="a"> Every non-empty set of reals bounded above has a least upper bound</label><br>
      <label><input type="radio" name="q2" value="b"> Every bounded set has no upper bound</label><br>
      <label><input type="radio" name="q2" value="c"> Every bounded set is finite</label><br>
      <label><input type="radio" name="q2" value="d"> None of these</label>
    </div>

    <div class="question">
      <p>3. Which of the following is <b>not true</b>?</p>
      <label><input type="radio" name="q3" value="a"> If \(A \subseteq B\), then \(\sup A \leq \sup B\)</label><br>
      <label><input type="radio" name="q3" value="b"> Every finite set is bounded</label><br>
      <label><input type="radio" name="q3" value="c"> Every bounded set is finite</label><br>
      <label><input type="radio" name="q3" value="d"> Every non-empty finite set has both sup and inf</label>
    </div>

    <div class="question">
      <p>4. Which of the following ray is represented by \([2,\infty)\)?</p>
      <label><input type="radio" name="q4" value="a"> All \(x \in \mathbb{R} : x \geq 2\)</label><br>
      <label><input type="radio" name="q4" value="b"> All \(x \in \mathbb{R} : x \leq 2\)</label><br>
      <label><input type="radio" name="q4" value="c"> All \(x \in \mathbb{R} : x > 2\)</label><br>
      <label><input type="radio" name="q4" value="d"> All \(x \in \mathbb{R} : x < 2\)</label>
    </div>

    <div class="question">
      <p>5. Which of these is the supremum of the set \(\{1,2,3\}\)?</p>
      <label><input type="radio" name="q5" value="a"> 2</label><br>
      <label><input type="radio" name="q5" value="b"> 3</label><br>
      <label><input type="radio" name="q5" value="c"> 1</label><br>
      <label><input type="radio" name="q5" value="d"> None</label>
    </div>

    <div class="question">
      <p>6. Which of these is the infimum of the set \(\{2,4,6,8\}\)?</p>
      <label><input type="radio" name="q6" value="a"> 8</label><br>
      <label><input type="radio" name="q6" value="b"> 2</label><br>
      <label><input type="radio" name="q6" value="c"> 0</label><br>
      <label><input type="radio" name="q6" value="d"> None</label>
    </div>

    <div class="question">
      <p>7. Which of these is not an upper bound of the set \([0,3]\)?</p>
      <label><input type="radio" name="q7" value="a"> 3</label><br>
      <label><input type="radio" name="q7" value="b"> 2.5</label><br>
      <label><input type="radio" name="q7" value="c"> 3.5</label><br>
      <label><input type="radio" name="q7" value="d"> 4</label>
    </div>

    <div class="question">
      <p>8. Which of these is a lower bound of the interval \([-10,1]\)?</p>
      <label><input type="radio" name="q8" value="a"> -11</label><br>
      <label><input type="radio" name="q8" value="b"> -9</label><br>
      <label><input type="radio" name="q8" value="c"> 11</label><br>
      <label><input type="radio" name="q8" value="d"> 1</label>
    </div>

    <div class="question">
      <p>9. Which of these sets is bounded?</p>
      <label><input type="radio" name="q9" value="a"> \(\{x \in \mathbb{R}: x^2 < 25\}\)</label><br>
      <label><input type="radio" name="q9" value="b"> \(\{x \in \mathbb{R}: x > 0\}\)</label><br>
      <label><input type="radio" name="q9" value="c"> \(\{x \in \mathbb{R}: x < 0\}\)</label><br>
      <label><input type="radio" name="q9" value="d"> \(\mathbb{R}\)</label>
    </div>

    <div class="question">
      <p>10. Which of these sets is bounded below?</p>
      <label><input type="radio" name="q10" value="a"> \(\{x \in \mathbb{R}: x \geq 0\}\)</label><br>
      <label><input type="radio" name="q10" value="b"> \(\{x \in \mathbb{R}: x \leq 0\}\)</label><br>
      <label><input type="radio" name="q10" value="c"> \(\mathbb{R}\)</label><br>
      <label><input type="radio" name="q10" value="d"> None of these</label>
    </div>

    <button type="button" onclick="checkAnswers()">Submit</button>
  </form>

  <div id="result"></div>

  <script>
    const correctAnswers = {
      q1: {ans: "a", exp: "Because \(a<b \iff b-a > 0\), i.e., \(b-a\) is positive."},
      q2: {ans: "a", exp: "This is the least upper bound property of real numbers."},
      q3: {ans: "c", exp: "A bounded set can be infinite, e.g., the interval [0,1]."},
      q4: {ans: "a", exp: "[2,∞) means all real numbers greater than or equal to 2."},
      q5: {ans: "b", exp: "The largest element of {1,2,3} is 3, so sup = 3."},
      q6: {ans: "b", exp: "The smallest element of {2,4,6,8} is 2, so inf = 2."},
      q7: {ans: "b", exp: "2.5 is inside [0,3], so it cannot be an upper bound."},
      q8: {ans: "a", exp: "Any number ≤ -10 is a lower bound. -11 is one such number."},
      q9: {ans: "a", exp: "x²<25 means -5<x<5, which is bounded."},
      q10: {ans: "a", exp: "{x ≥ 0} has lower bound 0."}
    };

    function checkAnswers() {
      let score = 0;
      let resultHTML = "<h3>Results:</h3>";

      for (let q in correctAnswers) {
        let userAnswer = document.querySelector(`input[name="${q}"]:checked`);
        if (userAnswer) {
          if (userAnswer.value === correctAnswers[q].ans) {
            score++;
            resultHTML += `<p>Question ${q.substring(1)}: <span class="correct">Correct</span> — ${correctAnswers[q].exp}</p>`;
          } else {
            resultHTML += `<p>Question ${q.substring(1)}: <span class="incorrect">Incorrect</span>. Correct answer: <b>${correctAnswers[q].ans.toUpperCase()}</b>. ${correctAnswers[q].exp}</p>`;
          }
        } else {
          resultHTML += `<p>Question ${q.substring(1)}: <span class="incorrect">Not answered</span>. Correct answer: <b>${correctAnswers[q].ans.toUpperCase()}</b>. ${correctAnswers[q].exp}</p>`;
        }
      }

      resultHTML += `<p><strong>Total Score: ${score} / ${Object.keys(correctAnswers).length}</strong></p>`;
      document.getElementById("result").innerHTML = resultHTML;
    }
  </script>
</body>
</html>
