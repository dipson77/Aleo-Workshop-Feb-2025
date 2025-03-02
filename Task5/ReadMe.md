# Building Zefi App

## Create new leo Project:
```sh
leo new dipson_token_vesting_linear
```

## Setup project:
```sh
cd dipson_token_vesting_linear
leo add token_registry
leo add credits
```

## Modified `main.leo`:
- Modified inside `main.leo` but change value of address with your public address.

## Deploy Project:
- Command:
    ```sh
    leo deploy --network testnet -y
    ```
    <details><summary> Detailed Output </summary><blockquote>

    ~~~sh

       Leo ✅ Compiled 'dipson_token_vesting_linear.aleo' into Aleo instructions
    📦 Creating deployment transaction for 'dipson_token_vesting_linear.aleo'...

    Base deployment cost for 'dipson_token_vesting_linear.aleo' is 13.1082 credits.

    +----------------------------------+----------------+
    | dipson_token_vesting_linear.aleo | Cost (credits) |
    +----------------------------------+----------------+
    | Transaction Storage              | 5.326000       |
    +----------------------------------+----------------+
    | Program Synthesis                | 6.782200       |
    +----------------------------------+----------------+
    | Namespace                        | 1.000000       |
    +----------------------------------+----------------+
    | Priority Fee                     | 0.000000       |
    +----------------------------------+----------------+
    | Total                            | 13.108200      |
    +----------------------------------+----------------+

    Your current public balance is 14.676387 credits.

    ✅ Created deployment transaction for 'dipson_token_vesting_linear.aleo'

    Broadcasting transaction to https://api.explorer.provable.com/v1/testnet/transaction/broadcast...

    ⌛ Deployment at1n6evzf35d2lu4jaqxw8pagkhthw4g38ys49xnvp5m76aj932nv8qupgmyz ('dipson_token_vesting_linear.aleo') has been broadcast to https://api.explorer.provable.com/v1/testnet/transaction/broadcast.
    ~~~

    </blockquote></details>

- On-Chain Outputs:
    - Transaction ID: `at1n6evzf35d2lu4jaqxw8pagkhthw4g38ys49xnvp5m76aj932nv8qupgmyz`
    - Aleo Program: [https://testnet.aleo.info/program/dipson_token_vesting_linear.aleo](https://testnet.aleo.info/program/dipson_token_vesting_linear.aleo)
    - Deploy Txn: [https://testnet.aleo.info/transaction/at1n6evzf35d2lu4jaqxw8pagkhthw4g38ys49xnvp5m76aj932nv8qupgmyz](https://testnet.aleo.info/transaction/at1n6evzf35d2lu4jaqxw8pagkhthw4g38ys49xnvp5m76aj932nv8qupgmyz) 


# Signature:
## Sign with `Transaction ID`:
- For me, program deployed Transaction ID is: `at1n6evzf35d2lu4jaqxw8pagkhthw4g38ys49xnvp5m76aj932nv8qupgmyz`. Command:
    ```sh
    leo account sign -d --private-key <redacted> --message "at1n6evzf35d2lu4jaqxw8pagkhthw4g38ys49xnvp5m76aj932nv8qupgmyz" --raw
    ```
- Output:
    ```sh
    sign1hmcw9tyv5eg9dt8hzqjj7s0vdd4tgha7z4vt68uypph2k3qw55q58umzlqjvaat6kghe7lgcczl4nd7py88wu8jvs5sh6dc5gw34sqaz3ku2r6nfe0g0pf6e6tlvc53xrktfmtksdtq6l0q0c4kqtjnhq80h804g6x09zfctv4fk7ux2888jsmr59htqps7p3cg9amq5utaq6ant7un
    ```