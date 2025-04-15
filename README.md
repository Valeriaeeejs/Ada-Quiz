# Ada Quiz
# Save the current HTML content as a downloadable file
html_content = """<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>What's Your Tech Persona?</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      background: #f2f2f2;
      padding: 2rem;
      max-width: 700px;
      margin: auto;
    }
    h1 {
      text-align: center;
      color: #333;
    }
    .question {
      margin-bottom: 1.5rem;
    }
    .question h3 {
      margin-bottom: 0.5rem;
    }
    label {
      display: block;
      margin-bottom: 0.3rem;
    }
    button {
      display: block;
      margin: 2rem auto;
      padding: 0.5rem 1.5rem;
      background-color: #007bff;
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 1rem;
      cursor: pointer;
    }
    #result {
      font-size: 1.2rem;
      text-align: center;
      font-weight: bold;
      color: #2c3e50;
    }
  </style>
</head>
<body>
  <h1>🧠 What’s Your Tech Persona?</h1>

  <form id="quizForm">
    <div class="question">
      <h3>1. What excites you most about the future of technology?</h3>
      <label><input type="radio" name="q1" value="creator"> A) Making things that look awesome and tell stories in new ways</label>
      <label><input type="radio" name="q1" value="innovator"> B) Creating tech that changes how businesses work</label>
      <label><input type="radio" name="q1" value="pioneer"> C) Solving tough problems with smart code and clever logic</label>
    </div>

    <div class="question">
      <h3>2. Your teacher asks you to make a presentation. You…</h3>
      <label><input type="radio" name="q2" value="creator"> A) Design eye-catching slides and maybe even add animations</label>
      <label><input type="radio" name="q2" value="innovator"> B) Focus on stats and how your idea could grow or earn money</label>
      <label><input type="radio" name="q2" value="pioneer"> C) Write a cool script that makes your presentation interactive</label>
    </div>

    <div class="question">
      <h3>3. Your dream project would be...</h3>
      <label><input type="radio" name="q3" value="creator"> A) Designing a video game or animating a short film</label>
      <label><input type="radio" name="q3" value="innovator"> B) Starting a tech start-up with your friends</label>
      <label><input type="radio" name="q3" value="pioneer"> C) Building an app that fixes a real-world problem</label>
    </div>

    <div class="question">
      <h3>4. You’ve got one free afternoon. What do you do?</h3>
      <label><input type="radio" name="q4" value="creator"> A) Edit a video, draw digital art, or play with music software</label>
      <label><input type="radio" name="q4" value="innovator"> B) Sell something online, plan a business idea, or look at trends</label>
      <label><input type="radio" name="q4" value="pioneer"> C) Try a coding challenge or watch a hacking/tech doc</label>
    </div>

    <div class="question">
      <h3>5. Which quote speaks to you the most?</h3>
      <label><input type="radio" name="q5" value="creator"> A) “Creativity is intelligence having fun.”</label>
      <label><input type="radio" name="q5" value="innovator"> B) “Opportunities don’t happen. You create them.”</label>
      <label><input type="radio" name="q5" value="pioneer"> C) “Talk is cheap. Show me the code.”</label>
    </div>

    <div class="question">
      <h3>6. If you had to teach a workshop, what would it be on?</h3>
      <label><input type="radio" name="q6" value="creator"> A) How to design logos or create digital art</label>
      <label><input type="radio" name="q6" value="innovator"> B) How to pitch a business idea or make money online</label>
      <label><input type="radio" name="q6" value="pioneer"> C) How to code a basic game or website</label>
    </div>

    <div class="question">
      <h3>7. What’s your favorite type of tech video to watch?</h3>
      <label><input type="radio" name="q7" value="creator"> A) Behind-the-scenes of movie or game production</label>
      <label><input type="radio" name="q7" value="innovator"> B) Interviews with tech CEOs or product launches</label>
      <label><input type="radio" name="q7" value="pioneer"> C) Programming tutorials or ethical hacking challenges</label>
    </div>

    <button type="button" onclick="calculateResult()">Show Me My Tech Persona!</button>
  </form>

  <div id="result"></div>

  <script>
    function calculateResult() {
      const answers = document.querySelectorAll('input[type="radio"]:checked');
      let scores = { creator: 0, innovator: 0, pioneer: 0 };
      answers.forEach(answer => scores[answer.value]++);

      let highest = Object.entries(scores).sort((a, b) => b[1] - a[1])[0][0];

      let messages = {
        creator: "🎨 You're a *Creator*! You thrive in creative roles like game design, UX/UI, and digital media.",
        innovator: "🚀 You're an *Innovator*! You shine in business-savvy tech careers like tech entrepreneur or product manager.",
        pioneer: "🔐 You're a *Pioneer*! You love diving deep into coding, cybersecurity, or data science."
      };

      document.getElementById('result').innerText = messages[highest];
    }
  </script>
</body>
</html>"""

file_path = "/mnt/data/tech_persona_quiz.html"
with open(file_path, "w") as f:
    f.write(html_content)

file_path
