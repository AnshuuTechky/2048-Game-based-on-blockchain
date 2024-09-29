### Explanation Script

This web-based **2048 Game** is enhanced with wallet integration using **ethers.js** and **Web3** for Ethereum. The game is built using **HTML, JavaScript, and CSS** for styling. Below is a breakdown of the functionality:

1. **HTML**:
    - The main structure contains the game grid, score container, wallet connect button, and game-over screen.
    - Uses external libraries like **Google Fonts** and **ethers.js** for Ethereum wallet connection.
  
2. **CSS**:
    - Provides a clean UI with a grid layout for the 2048 game tiles, styled with different colors based on the tile number.
    - Styles wallet integration buttons and game-over screen.

3. **JavaScript**:
    - **Grid Creation**: Creates a 4x4 grid with div elements, representing the game board. Each tile is a 'box' class.
    - **Sliding Mechanism**: Supports swipe and keyboard events (`ArrowUp`, `ArrowDown`, `ArrowLeft`, `ArrowRight`) to slide numbers on the grid.
    - **Random Number Generation**: Randomly generates new "2" or "4" tiles after each valid move.
    - **Game Over**: Detects when no more moves are possible and displays a "Game Over" screen with the final score.
    - **Wallet Integration**: Allows users to connect their Ethereum wallet via **MetaMask**.
    - **Minting High Scores**: Once the game ends, if the wallet is connected, the player's high score can be minted as an Ethereum token.

### Core Functions:
- **createGrid**: Creates the initial grid layout for the game.
- **slideUp, slideDown, slideLeft, slideRight**: Controls the sliding of tiles in each direction.
- **generateTwo, generateFour**: Adds a random "2" or "4" tile after each move.
- **mintWithHighScore**: If the Ethereum wallet is connected, this function sends the high score to the blockchain for minting as a token.

---

### ReadMe

# 2048 Game with Ethereum Wallet Integration

This is a simple implementation of the **2048 Game** with Ethereum wallet connectivity. The user can play the game and mint their high score on the Ethereum blockchain using **ethers.js** and **Web3**.

## How It Works:

1. **Game Logic**: This project implements the classic 2048 game logic with sliding, tile merging, and scoring.
2. **Ethereum Wallet Integration**: Users can connect their Ethereum wallet using MetaMask. Once connected, the wallet address is displayed on the screen.
3. **Minting High Score**: After the game ends, users can mint their high score as an Ethereum token on the blockchain by interacting with a deployed smart contract.

## Technologies Used:

- **HTML, CSS, JavaScript**: Frontend of the game.
- **ethers.js & Web3.js**: To integrate Ethereum blockchain functionality and handle wallet interactions.
- **MetaMask**: For Ethereum wallet management.
  
## Features:

- **Classic 2048 Game**: Move tiles on a 4x4 grid using arrow keys or swipe gestures.
- **Wallet Connection**: Allows users to connect their Ethereum wallet using MetaMask.
- **High Score Minting**: Mint high scores on the blockchain with a connected wallet.

## Setup Instructions:

### Prerequisites:

1. **MetaMask**: Ensure MetaMask is installed and set up in your browser.
2. **Web3 & ethers.js**: The required libraries are included in the `index.html`.

### Steps:

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/2048-ethereum-game.git
   cd 2048-ethereum-game
   ```

2. Open the `index.html` file in your browser.

3. To interact with Ethereum:
   - Install **MetaMask** in your browser.
   - Click "Connect Wallet" on the webpage.
   - Play the game, and when the game ends, your final score can be minted as an Ethereum token.

### File Overview:

- `index.html`: Contains the main structure and game layout.
- `style.css`: Contains the game UI styles.
- `script.js`: Implements the game logic, wallet connection, and score minting functions.

### Key Code Sections:

- **Wallet Connection**: 
  ```javascript
  if (window.ethereum) {
      await window.ethereum.request({ method: 'eth_requestAccounts' });
      const web3 = new Web3(window.ethereum);
  }
  ```

- **Minting High Score**:
  ```javascript
  const mintWithHighScore = async (score) => {
      const contractAddress = 'your-contract-address';
      const abi = [your-contract-abi];
      const tx = await contract.mintWithHighScore(score);
  };
  ```

### Future Enhancements:

- Add network validation to ensure the user is connected to the correct Ethereum network (e.g., Mainnet, Ropsten).
- Implement an on-chain leaderboard to track top scores.
- Enhance UI/UX for smoother gameplay experience.

---

## License

This project is licensed under the MIT License.
