# zkSync Transfer Bot

## Installation

### Requirements

- [Node.js](https://nodejs.org/en/download/package-manager)
- [Docker (opsiyonel)](https://www.docker.com/products/docker-desktop/)

### Steps

1. Clone this:

```sh
   https://github.com/UnicorNn1/zkSync-Transfer-Bot.git
```

2. Go to the project directory:

```sh
   cd zk-transfer-bot
```

3. Install the required Node.js dependencies:

```sh
   npm install
```

## Configuration

There are two configuration files under the `config` folder in the root directory of the project: `tokens.json` and `wallets.json`. Tokens.json is an already configured file.

### wallets.json

This file contains wallet information and addresses to be transferred. For example:

```json
{
  "providerUrl": "https://mainnet.era.zksync.io/",
  "wallets": [
    {
      "privateKey": "YOUR_PRIVATE_KEY_1",
      "transferToAddress": "ADDRESS_TO_TRANSFER_TO_1"
    },
    {
      "privateKey": "YOUR_PRIVATE_KEY_2",
      "transferToAddress": "ADDRESS_TO_TRANSFER_TO_2"
    }
  ]
}
```

## Usage

### Running with Node.js

1. Start the project:

```sh
   npm i && npm start
```

### Running with Docker

1. Create the Docker image:

```sh
   docker build -t my-node-app .
```

2. Run the Docker container:

```sh
   docker run my-node-app
```

# Code Description

## src/monitor.js

This file tracks token transfers and performs transfer operations. The `transferTokens` function checks the balance of a wallet and transfers it to a specific address. The `monitorWallet` function monitors a specific wallet and listens for transfer events.

## Retry Mechanism

The code includes a retry mechanism to retry transactions in case of network failures. This mechanism retries operations up to a certain number of attempts and waits for a certain time for each failed attempt.

## Licence

This project is licensed under the MIT licence. See the LICENSE file for more information.
