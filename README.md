### Hi there š

<!--
**Abhijith92/Abhijith92** is a āØ _special_ āØ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- š­ Iām currently working on ... Java script code
- š± Iām currently learning ... Testing and AI
- š« How to reach me: ... abhijithnair100@gmail.com
- ā” Fun fact: ... I have a large sense of Humour 
--> The code is shown below:

//begining of the code

'use strict';

// console.log(document.querySelector('.message').textContent);
// document.querySelector('.message').textContent = 'š correct number!';

// document.querySelector('.number').textContent = 13;
// document.querySelector('.score').textContent = 10;

// document.querySelector('.guess').value = 23;
// console.log(document.querySelector('.guess').value);

const SecretNumber = Math.trunc(Math.random() * 20) + 1;
let score = 20;
let Highscore = 0;

document.querySelector('.check').addEventListener('click', function () {
  const guess = Number(document.querySelector('.guess').value);
  console.log(guess, typeof guess);

  if (!guess) {
    document.querySelector('.message').textContent = 'š« no number!';
  } else if (guess === SecretNumber) {
    document.querySelector('.message').textContent = 'š correct number!';

    document.querySelector('.number').textContent = SecretNumber;

    document.querySelector('body').style.background = '#60b347';
    document.querySelector('.number').style.width = '30rem';
    if (Highscore > score) {
      Highscore = score;
      document.querySelector('.Highscore').textContent = Highscore;
    }
  } else if (guess > SecretNumber) {
    if (score > 1) {
      document.querySelector('.message').textContent = 'š Too High!';
      score--;
      document.querySelector('.score').textContent = score;
    } else {
      document.querySelector('.message').textContent = 'you lost the game!';
      document.querySelector('.score').textContent = 0;
    }
  } else if (guess < SecretNumber) {
    if (score > 1) {
      document.querySelector('.message').textContent = 'š Too Low!';
      score--;
      document.querySelector('.score').textContent = score;
    } else {
      document.querySelector('.message').textContent = 'you lost the game!';
      document.querySelector('.score').textContent = 0;
    }
  }
});

document.querySelector('.again').addEventListener('click', function () {
  score = 20;
  SecretNumber = Math.trunc(Math.random() * 20) + 1;

  document.querySelector('.message').textContent = 'Start guessing...';
  document.querySelector('.score').textContent = score;
  document.querySelector('.number').textContent = '?';
  document.querySelector('.guess').textContent = '';
  document.querySelector('body').style.background = '#222';
  document.querySelector('.number').style.width = '15rem';
});
// end of code
