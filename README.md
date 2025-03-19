# 🏆 Internet Computer Token Project (DANN)

## 🌟 About the Project
This project is a **token management system** built on the **Internet Computer (IC)**. It provides functionalities for **creating, transferring, and managing tokens** using **Motoko** and **React**.

The project includes:
- **A Smart Contract** (`Token.mo`) that manages token balances and transfers.
- **A React Frontend** that allows users to interact with the contract.
- **Internet Identity Authentication** for secure access.

## 🎯 Features
✅ **Check your token balance**  
✅ **Claim free tokens from a Faucet** (airdrop: 10,000 DANN)  
✅ **Transfer tokens between users**  
✅ **Manage and charge the canister**  
✅ **Deploy the project on the IC network**  

---

# 🚀 Getting Started

## 📌 Prerequisites
Before running this project, make sure you have:
- ✅ **Node.js & npm** installed
- ✅ **DFX SDK** (Internet Computer development framework)
- ✅ **Internet Identity setup** for authentication

## 📂 Installation & Setup

1️⃣ Clone the repository
```bash
git clone https://github.com/your-username/token-project.git
cd token-project
```
2️⃣ Start the local development environment
```bash
dfx start --background
```
3️⃣ Deploy the canister
```bash
dfx deploy
```
4️⃣ Start the frontend
```bash
npm install
npm start
```
## 🔑 Managing Your Token Balance


### Check your Balance

1. Find out your principal id:

```
dfx identity get-principal
```

2.  Save it for later use

3. Format and store it in a command line variable:
```
OWNER_PUBLIC_KEY="principal \"$( \dfx identity get-principal )\""
```

4. Check that step 3 worked by printing it out:
```
echo $OWNER_PUBLIC_KEY
```

5. Check the owner's balance:
```
dfx canister call token balanceOf "( $OWNER_PUBLIC_KEY )"
```

## 💰 Charge the Canister


1. Check canister ID:
```
dfx canister id token
```

2. Save canister ID into a command line variable:
```
CANISTER_PUBLIC_KEY="principal \"$( \dfx canister id token )\""
```

3. Check canister ID has been successfully saved:
```
echo $CANISTER_PUBLIC_KEY
```

4. Transfer half a billion tokens to the canister Principal ID:
```
dfx canister call token transfer "($CANISTER_PUBLIC_KEY, 500_000_000)"
```

## 🚀 Deploy the Project to the Live IC Network

1. Create and deploy canisters:

```
dfx deploy --network ic
```

2. Check the live canister ID:
```
dfx canister --network ic id token
```

3. Save the live canister ID to a command line variable:
```
LIVE_CANISTER_KEY="principal \"$( \dfx canister --network ic id token )\""
```

4. Check that it worked:
```
echo $LIVE_CANISTER_KEY
```

5. Transfer some tokens to the live canister:
```
dfx canister --network ic call token transfer "($LIVE_CANISTER_KEY, 50_000_000)"
```

6. Get live canister front-end id:
```
dfx canister --network ic id token_assets
```
7. Copy the id from step 6 and add .raw.ic0.app to the end to form a URL.
e.g. zdv35-7qaaa-aaaai-qibuq-cei.raw.ic0.app

## 🔒 Security Best Practices
✅ DO NOT hardcode your Principal ID in Token.mo

✅ Use .env.local for storing sensitive keys and add it to .gitignore

✅ Use dfx identity get-principal instead of exposing Principal IDs

✅ Follow best practices for deploying on the IC network

## 🛠️ Technologies Used
Motoko (Smart Contract Language)

React.js (Frontend)

DFX SDK (Internet Computer Development)

Internet Identity (Secure Authentication) 

### Tip

If you want to test it out without authentication, comment out everything related to authentication and uncomment the code that is currently commented