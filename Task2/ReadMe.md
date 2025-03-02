# KYC Complaint Token:

## Create leo Project:
- Command:
    ```sh
    leo new dipson_kyc_complaint_token
    ```

## Install dependencies:
- Command:
    ```sh
    cd dipson_kyc_complaint_token
    leo add token_registry
    leo add credits
    ```

## Compiled Program:
- Command:
    ```sh
    leo build
    ```

## Deploy to testnet:
- Value of Endpoint must be changed with: `https://api.explorer.provable.com/v1` in `.env` file.
- Now, the value of `PRIVATE_KEY` in `.env` must be replaced.
- We will require some token to deploy our program into testnet.

- Command:
    ```sh
    leo deploy --network testnet
    ```
    
    <details><summary> Detailed Output </summary><blockquote>

    ~~~sh
    📦 Creating deployment transaction for 'dipson_kyc_complaint_token.aleo'...

    Base deployment cost for 'dipson_kyc_complaint_token.aleo' is 10.18405 credits.

    +---------------------------------+----------------+
    | dipson_kyc_complaint_token.aleo | Cost (credits) |
    +---------------------------------+----------------+
    | Transaction Storage             | 4.413000       |
    +---------------------------------+----------------+
    | Program Synthesis               | 4.771050       |
    +---------------------------------+----------------+
    | Namespace                       | 1.000000       |
    +---------------------------------+----------------+
    | Priority Fee                    | 0.000000       |
    +---------------------------------+----------------+
    | Total                           | 10.184050      |
    +---------------------------------+----------------+

    Your current public balance is 14.860437 credits.

    ✅ Created deployment transaction for 'dipson_kyc_complaint_token.aleo'

    Broadcasting transaction to https://api.explorer.provable.com/v1/testnet/transaction/broadcast...

    ⌛ Deployment at1dyguxq6xuaz950q2heuk3mt2h39ue47ey58me04lyfh6dsdm2u8qkq0tu4 ('dipson_kyc_complaint_token.aleo') has been broadcast to https://api.explorer.provable.com/v1/testnet/transaction/broadcast.
    ~~~

    </blockquote></details>

- On-Chain Outputs: 
    - Transaction ID: `at1dyguxq6xuaz950q2heuk3mt2h39ue47ey58me04lyfh6dsdm2u8qkq0tu4`
    - Aleo Program: [https://testnet.aleo.info/program/dipson_kyc_complaint_token.aleo](https://testnet.aleo.info/program/dipson_kyc_complaint_token.aleo)
    - Deploy Txn: [https://testnet.aleo.info/transaction/at1dyguxq6xuaz950q2heuk3mt2h39ue47ey58me04lyfh6dsdm2u8qkq0tu4](https://testnet.aleo.info/transaction/at1dyguxq6xuaz950q2heuk3mt2h39ue47ey58me04lyfh6dsdm2u8qkq0tu4) 


# Signature:
## Sign with `Transaction ID`:
- For me, program deployed Transaction ID is: `at1dyguxq6xuaz950q2heuk3mt2h39ue47ey58me04lyfh6dsdm2u8qkq0tu4`. Command:
    ```sh
    leo account sign -d --private-key <redacted> --message "at1dyguxq6xuaz950q2heuk3mt2h39ue47ey58me04lyfh6dsdm2u8qkq0tu4" --raw
    ```
- Output:
    ```sh
    sign1n7hs2zvaclx9xq6nrg75vg445halylfr4vup88ce9pwmj0qwjvqc2ed6zqmhdre40nya56qr9kuhgp7ddp6evycpumv9vn82dnfpyq4z3ku2r6nfe0g0pf6e6tlvc53xrktfmtksdtq6l0q0c4kqtjnhq80h804g6x09zfctv4fk7ux2888jsmr59htqps7p3cg9amq5utaq68u0jz6
    ```