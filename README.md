# Aadhar Identity Management System

The Aadhaar Identity Management System is a blockchain-based decentralized application that securely stores Aadhaar card data on the Ethereum blockchain. This system provides greater control over personal information and is more secure than traditional centralized identity management systems. Users can choose which data to share and revoke access at any time. This solution is transparent, secure, and efficient, reducing the time and cost of identity verification processes.

## Prerequisites

To run this project locally, you will need the following software installed on your system:

-   Node.js (version: v19.8.1)
-   npm (version: 9.6.4)
-   Truffle (version: v5.8.1)
-   Geth (version: 1.11.5-stable-a38f4108)

## Running the Project

Follow the steps below to run the project:

1. If you are running this project for the first time, follow these steps:

    i. Move to the root directory `cd ~`.

    ii. Create a directory `mkdir singlenode`.

    iii. Move into the created directory `cd singlenode`.

    iv. Create a `genesis.json` file with the following code:

    ```
    {
     "config": {
     "chainId": 4321,
     "homesteadBlock": 0,
     "eip150Block": 0,
     "eip155Block": 0,
     "eip158Block": 0,
     "byzantiumBlock": 0,
     "constantinopleBlock": 0
     },
     "alloc": {},
     "difficulty" : "0x20000",
     "gasLimit"   : "0x8880000"
    }
    ```

    v. Create a directory `mkdir node1`.

    vi. Initialize the genesis to that node using `geth --datadir node1 init genesis.json`.

2. Now start the node using:

    `geth --http --http.corsdomain http://remix.ethereum.org --allow-insecure-unlock --http --http.port 8545 --http.addr 127.0.0.1 --http.corsdomain "*" --http.api "eth,net,web3,personal,miner" --datadir node1 --nodiscover --networkid 4321 --port 30303 console --rpc.enabledeprecatedpersonal`

3. Create an account using `personal.newAccount()`. Enter a password.

4. Using web3, keep the account unlocked using `web3.personal.unlockAccount(eth.accounts[0],'password',0)`. Replace the password with the set password.

5. Set the etherbase using `miner.setEtherbase(eth.accounts[0])`.

6. Start the miner using `miner.start()`.

7. Open up the project directory in another terminal and install all the required node modules using `npm install`.

8. Compile the project using `truffle compile`.

9. Migrate the project using `truffle migrate`.

10. Deploy the GUI locally using `npm run buildandrun`.

11. In your browser, open up `http://localhost:3001`.

## Working

1. First, click on "Sign up".

2. This opens up the Sign Up page.

3. Fill in all the details and click on "Submit".

4. If all the details are correct, you will be redirected back to the home page.

5. Click on "Login".

6. Login using proper credentials.

7. If the provided credentials are proper, then you will be redirected to the dashboard page.

8. Then click on the "Organisation" option to manage your permissions.

9. Click on "Add" and add the required permissions.

10. In another tab, open `http://localhost:3001/insurance.html` to access the page where we can verify if only the information that we have given permission are being accessed.

11. Fill in all the details and then click "Submit". If all the provided details are correct and permission is granted by the user, you will be alerted with an alert box saying "Your request would be processed soon". If you don't have the required permission, you will be alerted "You don't have the required permission".

### Frameworks and Libraries Used

The Aadhaar Identity Management System was developed using Truffle for blockchain development and ExpressJS for middleware API. The following libraries were also used: jQuery and Bootstrap.
