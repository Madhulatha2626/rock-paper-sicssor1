<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Rock Paper Scissors Game</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');

  body {
    background: linear-gradient(135deg, #667eea, #764ba2);
    font-family: 'Poppins', sans-serif;
    margin: 0;
    padding: 0;
    color: #fff;
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    align-items: center;
    justify-content: center;
  }

  h1 {
    font-weight: 600;
    font-size: 3rem;
    margin-bottom: 0.25em;
    text-shadow: 2px 2px 8px rgba(0,0,0,0.3);
  }

  .scoreboard {
    font-size: 1.25rem;
    margin-bottom: 1.5rem;
    letter-spacing: 1px;
    text-shadow: 1px 1px 6px rgba(0,0,0,0.4);
  }

  .choices {
    display: flex;
    gap: 2rem;
    margin-bottom: 2rem;
  }

  button.choice-btn {
    background: #fff;
    border: none;
    border-radius: 50%;
    width: 100px;
    height: 100px;
    font-size: 2rem;
    font-weight: 600;
    color: #764ba2;
    cursor: pointer;
    box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
    transition: all 0.3s ease;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  button.choice-btn:hover {
    background: #764ba2;
    color: #fff;
    transform: scale(1.1);
    box-shadow: 0 12px 20px rgba(0, 0, 0, 0.3);
  }

  .result {
    font-size: 1.75rem;
    margin-bottom: 1.5rem;
    min-height: 2.5rem;
    font-weight: 600;
    letter-spacing: 0.5px;
    text-shadow: 2px 2px 10px rgba(0,0,0,0.3);
  }

  .reset-btn {
    background: transparent;
    border: 2px solid #fff;
    border-radius: 25px;
    color: #fff;
    padding: 0.6em 2em;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    letter-spacing: 1px;
    transition: all 0.3s ease;
    box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
  }
  .reset-btn:hover {
    background: #fff;
    color: #764ba2;
    box-shadow: 0 12px 20px rgba(0, 0, 0, 0.3);
  }

  .choices button span {
    display: block;
    font-size: 0.6rem;
    margin-top: 0.3rem;
    font-weight: 500;
    color: #764ba2;
  }
</style>
</head>
<body>
  <h1>Rock Paper Scissors</h1>
  <div class="scoreboard">
    You: <span id="user-score">0</span> &nbsp;&nbsp;|&nbsp;&nbsp; Computer: <span id="computer-score">0</span>
  </div>
  <div class="choices">
    <button class="choice-btn" data-choice="rock" title="Rock">
      ✊
      <span>Rock</span>
    </button>
    <button class="choice-btn" data-choice="paper" title="Paper">
      ✋
      <span>Paper</span>
    </button>
    <button class="choice-btn" data-choice="scissors" title="Scissors">
      ✌️
      <span>Scissors</span>
    </button>
  </div>
  <div class="result" id="result"></div>
  <button class="reset-btn" id="reset-btn">Reset Game</button>

<script>
  const userScoreSpan = document.getElementById('user-score');
  const computerScoreSpan = document.getElementById('computer-score');
  const resultDiv = document.getElementById('result');
  const resetBtn = document.getElementById('reset-btn');
  const choiceButtons = document.querySelectorAll('.choice-btn');

  let userScore = 0;
  let computerScore = 0;

  function computerPlay() {
    const choices = ['rock', 'paper', 'scissors'];
    const randomIndex = Math.floor(Math.random() * choices.length);
    return choices[randomIndex];
  }

  function determineWinner(userChoice, compChoice) {
    if (userChoice === compChoice) {
      return 'tie';
    }
    if (
      (userChoice === 'rock' && compChoice === 'scissors') ||
      (userChoice === 'paper' && compChoice === 'rock') ||
      (userChoice === 'scissors' && compChoice === 'paper')
    ) {
      return 'win';
    }
    return 'lose';
  }

  function capitalize(word) {
    return word.charAt(0).toUpperCase() + word.slice(1);
  }

  function playRound(userChoice) {
    const compChoice = computerPlay();
    const winner = determineWinner(userChoice, compChoice);

    let message = `You chose ${capitalize(userChoice)}, computer chose ${capitalize(compChoice)}. `;

    if (winner === 'win') {
      userScore++;
      userScoreSpan.textContent = userScore;
      message += 'You win this round! 🎉';
      resultDiv.style.color = '#00ff99';
    } else if (winner === 'lose') {
      computerScore++;
      computerScoreSpan.textContent = computerScore;
      message += 'You lose this round. 😞';
      resultDiv.style.color = '#ff4d4d';
    } else {
      message += "It's a tie. 🤝";
      resultDiv.style.color = '#ffd700';
    }

    resultDiv.textContent = message;
  }

  choiceButtons.forEach(button => {
    button.addEventListener('click', () => {
      playRound(button.dataset.choice);
    });
  });

  resetBtn.addEventListener('click', () => {
    userScore = 0;
    computerScore = 0;
    userScoreSpan.textContent = userScore;
    computerScoreSpan.textContent = computerScore;
    resultDiv.textContent = '';
  });
</script>

</body>
</html>

