# Hey, I'm Nikos! 👋  

![Profile Views](https://komarev.com/ghpvc/?username=nikos-chatzatoglou&color=blueviolet)  

### 🔭 **What I’m up to**  
- By day: Front-end developer building stuff with **React/Next.js** ⚛️  
- By night: Start new projects and never finish them  
- Always: Tinkering with **AI**, hacking on **open-source**, or breaking things in **Solidity/Go** 🤖  

### 🛠️ **Toolbox**  
**Code & Frameworks:**  
![](https://img.shields.io/badge/TypeScript-007ACC?style=flat&logo=typescript&logoColor=white)
![](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)
![](https://img.shields.io/badge/Next.js-000000?style=flat&logo=nextdotjs&logoColor=white)
![](https://img.shields.io/badge/Express.js-000000?style=flat&logo=express&logoColor=white)
![](https://img.shields.io/badge/Solidity-363636?style=flat&logo=solidity&logoColor=white)
![](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)  

**Learning right now:**  
![](https://img.shields.io/badge/Express.js-000000?style=flat&logo=express&logoColor=white)


### 📫 **Let’s chat!**  
- **Collab?** I'm all ears for... (you name it) → [Drop me an email](mailto:nikos.chatzatoglou@example.com) 📬  
- **LinkedIn:** Let's talk out about work → [Connect here](https://www.linkedin.com/in/nikos-chatzatoglou-399360173) 💼  
- **Fun fact:** I trade hiking trails for code trails 🏞️  

---

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=nikos-chatzatoglou&layout=compact&theme=radical)

## 🎮 Interactive Tic Tac Toe

Want to take a quick break? Play a game of Tic Tac Toe directly from my profile!  
Click the button below to try it out on a live demo (hosted externally):

[![Play Tic Tac Toe](https://img.shields.io/badge/Play-Tic_Tac_Toe-brightgreen)](https://your-demo-link.com)

Curious about how it works? Check out the source code snippet below:

```jsx
// TicTacToe.js
import React, { useState } from 'react';

const calculateWinner = (squares) => {
  const lines = [
    [0, 1, 2], [3, 4, 5], [6, 7, 8],
    [0, 3, 6], [1, 4, 7], [2, 5, 8],
    [0, 4, 8], [2, 4, 6],
  ];
  for (let [a, b, c] of lines) {
    if (squares[a] && squares[a] === squares[b] && squares[a] === squares[c])
      return squares[a];
  }
  return null;
};

const TicTacToe = () => {
  const [squares, setSquares] = useState(Array(9).fill(null));
  const [xIsNext, setXIsNext] = useState(true);

  const handleClick = (i) => {
    if (squares[i] || calculateWinner(squares)) return;
    const newSquares = squares.slice();
    newSquares[i] = xIsNext ? 'X' : 'O';
    setSquares(newSquares);
    setXIsNext(!xIsNext);
  };

  const renderSquare = (i) => (
    <button
      onClick={() => handleClick(i)}
      style={{
        width: '60px',
        height: '60px',
        fontSize: '24px',
        margin: '2px',
      }}
    >
      {squares[i]}
    </button>
  );

  const winner = calculateWinner(squares);
  const status = winner ? `Winner: ${winner}` : `Next Player: ${xIsNext ? 'X' : 'O'}`;

  return (
    <div>
      <div style={{ marginBottom: '10px' }}>{status}</div>
      <div style={{ display: 'flex' }}>
        {renderSquare(0)}
        {renderSquare(1)}
        {renderSquare(2)}
      </div>
      <div style={{ display: 'flex' }}>
        {renderSquare(3)}
        {renderSquare(4)}
        {renderSquare(5)}
      </div>
      <div style={{ display: 'flex' }}>
        {renderSquare(6)}
        {renderSquare(7)}
        {renderSquare(8)}
      </div>
      <button
        onClick={() => {
          setSquares(Array(9).fill(null));
          setXIsNext(true);
        }}
        style={{ marginTop: '10px' }}
      >
        Reset Game
      </button>
    </div>
  );
};

export default TicTacToe;
