# Decentralized-Voting-System-Using-Ethereum-Blockchain

The Decentralized Voting System using Ethereum Blockchain is a secure and transparent solution for conducting elections. Leveraging Ethereum's blockchain technology, this system ensures tamper-proof voting records, enabling users to cast their votes remotely while maintaining anonymity and preventing fraud.

---

## Table of Contents
- [Features](#features)
- [Screenshots](#screenshots)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Code Structure](#code-structure)
- [License](#license)
- [Star the Project](#star-the-project)

---

## Features
- **JWT** for secure voter authentication and authorization.
- **Ethereum blockchain** for tamper-proof and transparent voting records.
- Removes the need for intermediaries, ensuring a **trustless voting process**.
- **Admin panel** to manage candidates, set voting dates, and monitor results.
- **Intuitive UI** for voters to cast votes and view candidate information.

---

## Screenshots

### Admin Page
![Admin Page](https://github.com/user-attachments/assets/314ab1b1-10bf-4c81-b114-b3ab6f51ec23)

### Voting Page
![Voting Page](https://github.com/user-attachments/assets/79d6737e-392c-4828-b1f2-46043fccf5f0)

### Login Page
![Login Page](https://github.com/user-attachments/assets/30a9f6cc-027e-4c62-9dcc-182ff8a60d17)

---

## Requirements
- **Node.js** (version 18.14.0)
- **Metamask**
- **Python** (version 3.9)
- **FastAPI**
- **MySQL Database** (port 3306)

---

## Installation

1. **Clone the repository**:
    ```sh
    git clone https://github.com/akanksha509/Decentralized-Voting-System-Using-Ethereum-Blockchain.git
    ```
2. **Download and install [Ganache](https://trufflesuite.com/ganache/)**.

3. **Create a workspace named `development`** in Ganache, then add `truffle-config.js` in the Truffle projects section by clicking **ADD PROJECT**.

4. **Install [Metamask](https://metamask.io/download/)** in your browser and import the Ganache accounts into Metamask.

5. **Add a network** to Metamask:
   - **Network Name**: Localhost 7575  
   - **RPC URL**: http://localhost:7545  
   - **Chain ID**: 1337  
   - **Currency Symbol**: ETH  

6. **Create a MySQL database** named `voter_db` (avoid using XAMPP). Inside this database, create a table `voters`:
    ```sql
    CREATE TABLE voters (
        voter_id VARCHAR(36) PRIMARY KEY NOT NULL,
        role ENUM('admin', 'user') NOT NULL,
        password VARCHAR(255) NOT NULL
    );
    ```

7. **Install Truffle globally**:
    ```sh
    npm install -g truffle
    ```

8. **Install Node.js dependencies** (in the project folder):
    ```sh
    npm install
    ```

9. **Install Python dependencies**:
    ```sh
    pip install fastapi mysql-connector-python pydantic python-dotenv uvicorn uvicorn[standard] PyJWT
    ```

---

## Usage

> **Note**: Update the **database credentials** in `./Database_API/.env` with your MySQL username, password, etc.

1. **Open Ganache** and select the `development` workspace.
2. **Open a terminal** in the project directory and enter the Truffle console:
    ```sh
    truffle console
    ```
3. **Compile the smart contracts**:
    ```sh
    compile
    ```
   Then exit the console by typing `.exit` or pressing `Ctrl + C`.

4. **Bundle `app.js` with Browserify**:
    ```sh
    browserify ./src/js/app.js -o ./src/dist/app.bundle.js
    ```
5. **Start the Node.js server**:
    ```sh
    node index.js
    ```
6. **Open another terminal**, navigate to the `Database_API` folder:
    ```sh
    cd Database_API
    ```
7. **Start the FastAPI server**:
    ```sh
    uvicorn main:app --reload --host 127.0.0.1
    ```
8. **In a new terminal**, migrate the Truffle contract to the local blockchain:
    ```sh
    truffle migrate
    ```
9. **Access the Voting app** at **http://localhost:8080/**.

---

## Code Structure

```plaintext
blockchain-voting-dapp/
├── build/
│   └── contracts/
│       ├── Migrations.json
│       └── Voting.json
├── contracts/
│   ├── Migrations.sol
│   └── Voting.sol
├── Database_API/
│   └── main.py
├── migrations/
│   └── 1_initial_migration.js
├── node_modules/
├── public/
│   └── favicon.ico
├── src/
│   ├── assets/
│   │   └── eth5.jpg
│   ├── css/
│   │   ├── admin.css
│   │   ├── index.css
│   │   └── login.css
│   ├── dist/
│   │   ├── app.bundle.js
│   │   └── login.bundle.js
│   ├── html/
│   │   ├── admin.html
│   │   ├── index.html
│   │   └── login.html
│   └── js/
│       ├── app.js
│       └── login.js
├── index.js
├── package.json
├── package-lock.json
├── truffle-config.js
└── README.md
License
This project is licensed under the MIT License.

Star the Project
⭐ If you like this project, please give it a star!





