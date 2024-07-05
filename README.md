# Link to enrollment tansaction
https://explorer.solana.com/tx/2a5K9ZLykoua31EJzGynhGmHHQLRgsF9gFsTwmxLdCXEr4WnjQLYM2RBV8UC3A32jE4dUcoPPsoQho4N9jA1GqbT?cluster=devnet

# Description of files

run `yarn`to install alle dependencies

use the commited wallet in `dev-wallet.json` to run the scripts (except for `enroll.ts`) or create your own keypair wit `yarn keygern`. Copy the private key (bs58 - as you get it from exporting from Phantom) of your dev wallet into a `.env` file as describted in `.env.example` if you want to run the `enroll.ts` script.

All connections are hardcoded to use the devnet.

## keygen.ts
Executed by running `yarn keygen`

Generates a keypair using the @solana/web3.js library and prints the public and private keys to the console. The secret key can be is displayed as a Uint8Array.

## airdrop.ts
Executed by running `yarn airdrop`

Airdrops 2 SOL to the public key of the keypair saved in `dev-wallet.json`

Change the read of the keypair (line 4) to use the private key from the `.env` file by replacing this with lines 9 and 10 from `enroll.ts`.

## transfer.ts
Executed by running `yarn transfer`

Transfers 1/100 SOL from the public key of the keypair saved in `dev-wallet.json` to the hardcoded public key in line 5.

## enroll.ts
Executed by running `yarn enroll`

Requires DEV_PK in `.env` to be set. DEV_PK expects a private key in base58 format(as you get e.g. when exporting from Phantom wallet).

Takes the github account name hardcoded in line 15 and writes it to the WBA program specified by the IDL in `programs/wba_prereq.ts` on devnet. To achieve this the anchor js client is used. 

After completing the transaction a link to the transaction will be printed to the console.








