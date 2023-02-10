const playButton = document.querySelector('#play-button');
const resultDisplay = document.querySelector('#result');

const choices = ['rock', 'paper', 'scissors'];

playButton.addEventListener('click', () => {
  const playerChoice = prompt("Rock, paper, or scissors?").toLowerCase();

  if (!choices.includes(playerChoice)) {
    resultDisplay.textContent = "Invalid choice. Please try again.";
    return;
  }

  const computerChoice = choices[Math.floor(Math.random() * choices.length)];

  if (playerChoice === computerChoice) {
    resultDisplay.textContent = "It's a draw!";
  } else if (
    (playerChoice === 'rock' && computerChoice === 'scissors') ||
    (playerChoice === 'paper' && computerChoice === 'rock') ||
    (playerChoice === 'scissors' && computerChoice === 'paper')
  ) {
    resultDisplay.textContent = "You win!";
  } else {
    resultDisplay.textContent = "The computer wins. Try again!";
  }

  resultDisplay.textContent += ` (Player: ${playerChoice} vs Computer: ${computerChoice})`;
});
