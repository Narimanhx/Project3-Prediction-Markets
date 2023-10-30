# README

# Project 3 - Prediction Markets
created by:
* Haywar Zhu
* Scott Speers
* Amar Sen
* Nariman Hosseini

## Streamlit Frontend - Chat App with MongoDB

This part of the project is a simple chat application built with Streamlit and MongoDB. Users can register, log in, and chat with each other. Admin users can clear the chat. The chat messages are stored in a MongoDB database.

## Prerequisites

Before running app.py, make sure you have the following prerequisites installed:

- Python (3.7 or higher)
- [Streamlit](https://streamlit.io/)
- [PyMongo](https://pymongo.readthedocs.io/)
- [Passlib](https://passlib.readthedocs.io/)
- A running MongoDB server

## Installation

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/Narimanhx/Project3-Prediction-Markets

## Usage

1. Open the app in your web browser by navigating to the provided [URL](https://prediction-markets.streamlit.app/).

2. Register a new user by selecting "Register" and providing a username and password.

3. Log in with your newly registered user or an existing user by selecting "Login."

4. Chat with other users by entering messages in the chat input box and clicking "Send."

5. Users can refresh the chat with the "Refresh" button.

6. Admin users can clear the chat by clicking the "Clear Chat" button.

## Implementation Details
* User registration and authentication are handled through MongoDB. User passwords are securely hashed using the Passlib library.
* Chat messages are stored in a MongoDB collection and are periodically refreshed every 5 seconds, ensuring that all logged-in users see the same chat messages.
* Admin users have the ability to clear the chat, which removes all chat messages from the MongoDB collection.

  
## Solidity Smart Contract -- Prediction.Sol

The smart contract is designed to handle betting on two outcomes (Team A and Team B). Its versatile design enables applicability to any event characterized by binary outcomes—be it coin flips, sporting events, stock market fluctuations, and the like. The admin can open or close betting, decide the outcome of the bet based on real world result, and, if necessary (such as in the event of a game suspension), withdraw funds from the contract. Players can place bets, and claim their winnings once the outcome is decided.

### Main Functions

- `toggleBetting(true for open)`: Admin can open or close betting.
- `placeBet(true for TeamA)`: Place a bet on Team A or Team B. The function is payable, meaning it requires sending ETH along with the transaction.
- `withdraw(uint256 amount)`: Admin can withdraw ETH from the contract.
- `decideOutcome(true for teamA Won)`: Admin can decide the outcome of the bet.
- `claimWinnings()`: Players can claim their winnings based on the outcome and their bet.

### View Functions
- `getTotalBets()`: View function to get the total bets placed on Team A and Team B.
- `getBetDetails(address bettor)`: View function to get the bet details of a specific player.
- `getOutcome()`: View function to get the current outcome of the bet.
- `getAdmins()`: View function to get the admin and fee recipient addresses.

## Front-End Interface (For Player) -- Prediction.py

The interface, designed with user-friendliness in mind, empowers players to seamlessly connect their Ethereum wallets, place bets, and review the betting outcomes. 
![interface](streamlit_ui.png)

### Features

- Wallet connection using Ethereum private key.
- Betting on Team A or Team B.
- Display of current outcome, total bets, and calculated odds.
- Input for bet amount and submission of the bet.
- Show the expected payout if win.
- Claiming of wining.

## Installation and Usage

1. Clone the repository to your local machine.
2. Navigate to the project directory and install the required dependencies: `pip install streamlit web3==5.23.0`
3. Deploy the smart contract to your preferred Ethereum network and note down the contract address.
4. Update the `contract_address` variable in the Streamlit code with the deployed contract address.
5. Run the Streamlit app: `streamlit run prediction.py`
6. Your web browser will be opened to interact with the platform.
