# Getting Started with ALEO:

## Create new project:
- Command:
    ```sh
    leo new dipsonbhujel_bidder_auction
    ```

- Create 3 accounts. Owner, Bidder1, Bidder2.
- Command:
    ```sh
    snarkos account new
    ```
- So, run above command 3 times in terminal:
    <details><summary> Detailed Output </summary><blockquote>

    ~~~
    $ snarkos account new
        Private Key  <hidden>
        View Key  <hidden>
        Address  aleo17wjgfjntm9ha6lx80ze8fhmff7s2tga70jgz2vwnn99rr2368qfqcundea

    $ snarkos account new
        Private Key  <hidden>
        View Key  <hidden>
        Address  aleo1zd7npntgtz3lc8sgcsr0sswgg4r0juyfxgqjawfaag9c7vew4u8sx4jn9w

    $ snarkos account new
        Private Key  <hidden>
        View Key  <hidden>
        Address  aleo19y5dghd5lwh53sjwtd5v3hdh0t0drn36gqpmcn683t43ml9zsvqq343kte
    ~~~
    
    </blockquote></details>

- In above output, suppose 1 a/c with Address `aleo17wjgfjntm9ha6lx80ze8fhmff7s2tga70jgz2vwnn99rr2368qfqcundea` is owner and remaining 2nd and 3rd a/cs are bidders. 
- Make sure `ENDPOINT` in `.env` file is `https://api.explorer.provable.com/v1`.
     
## Deploy To Testnet:
- We need ALEO token in each accounts. So load up before moving any further.
- Now, the value of `PRIVATE_KEY` in `.env` must be replaced with the `PRIVATE_KEY` of the Owner.
- Command:
    ```sh
    leo deploy --network testnet -y
    ```
    <details><summary> Detailed Output </summary><blockquote>

    ~~~
       Leo ✅ Compiled 'dipsonbhujel_bidder_auction.aleo' into Aleo instructions
    📦 Creating deployment transaction for 'dipsonbhujel_bidder_auction.aleo'...


    Base deployment cost for 'dipsonbhujel_bidder_auction.aleo' is 14.495675 credits.

    +----------------------------------+----------------+
    | dipsonbhujel_bidder_auction.aleo | Cost (credits) |
    +----------------------------------+----------------+
    | Transaction Storage              | 3.639000       |
    +----------------------------------+----------------+
    | Program Synthesis                | 9.856675       |
    +----------------------------------+----------------+
    | Namespace                        | 1.000000       |
    +----------------------------------+----------------+
    | Priority Fee                     | 0.000000       |
    +----------------------------------+----------------+
    | Total                            | 14.495675      |
    +----------------------------------+----------------+

    Your current public balance is 29.830178 credits.

    ✅ Created deployment transaction for 'dipsonbhujel_bidder_auction.aleo'

    Broadcasting transaction to https://api.explorer.provable.com/v1/testnet/transaction/broadcast...

    ⌛ Deployment at18848cd65040znxpj3tksrm3k6e38zqxv2zmvhjpauaxrlnfr9upqgz9n39 ('dipsonbhujel_bidder_auction.aleo') has been broadcast to https://api.explorer.provable.com/v1/testnet/transaction/broadcast.
    ~~~

    </blockquote></details>


- On-Chain Outputs: 
    - Deployment ID: `at18848cd65040znxpj3tksrm3k6e38zqxv2zmvhjpauaxrlnfr9upqgz9n39`
    - Aleo Program: [https://testnet.aleo.info/program/dipsonbhujel_bidder_auction.aleo](https://testnet.aleo.info/program/dipsonbhujel_bidder_auction.aleo)
    - Deploy Txn: [https://testnet.aleo.info/transaction/at18848cd65040znxpj3tksrm3k6e38zqxv2zmvhjpauaxrlnfr9upqgz9n39](https://testnet.aleo.info/transaction/at18848cd65040znxpj3tksrm3k6e38zqxv2zmvhjpauaxrlnfr9upqgz9n39) 


## Execution Details:
- 1st Bidder Execution:
    - Transition ID: `at1ah8n09trwa3ry7dct4ymdxarz09nqpwhy9esrp2mytt3wkexsv8q5gh05a`
    - Output Record: `record1qyqspf7k3j6mq8xxv7h5unlhnfx2gryddeuknevygrdwa82pja6jnvcgqvrxy6tyv3jhyscqqgpqpllexvprclg3e06g0d4zjj88w6ehgfg2dfm5x0tq9haq9s0928s9ywn2kmlgennzgak99uymphrpk4m287943fcscpa7309zahlx9cxqvctdda6kuaprqqpqzqpjtldn3pzaka5kpwqj5aez2aj9hq4cldgmzgf3avjt6hykeuqepgykju6lwa5kumn9wg3sqqspqq26g3l34hfq8d5nqydd08pqckzsc736zn8t5dstqfu7az00lcssaqu9ewwc0qu3cxd4cvfqwyty0ntyqy3n0yxgvra9d8xmxzv8gpsrpns87u`

- 2nd Bidder Execution:
    - Transition ID: `at1v67wunmec8f2djtmhwp4jdmr7y7wnxq7vsrcad03re262pl2rqrs36xj9s`
    - Output Record: `record1qyqsq9duumvna28gmag2vgdvel3sxa55dkjpv7yyjywaxhx0edumuecjqvrxy6tyv3jhyscqqgpqq9n0egqmucd7r2mn676vwcjam0qtag7mmwuk3ntz0fuugcjfngq02ddqzj967zv2tphjvmzmlceyqjtpmg9tg6hlz6sf0378rmj3agqsvctdda6kuaprqqpqzqyvvq8fa6nnv60l6ltsllvlhl9xx67lvwc4mjjfylsh7km0nw6xqsykju6lwa5kumn9wg3sqqspqpg2qn30khupvpzrs0aqyrn5jrfuj0yt9f6pkaseleq2vesdr3e39lcwtx4hwel45wg2kh8majyxthxhvwp339pjr44g0fl2jr0p9uqsqw9n30`

- Decrypt Record using:
    ```sh
    snarkos developer decrypt -v <VIEW_KEY> -c <RECORD_CIPHERTEXT>
    ```

- Resolve Bid:
    - Transition ID: `at1twy07ldpkctk7nqh274ldxnedf6sljhga3dnjmnq2dj0r5mm9uzqzrgu32`
    - Output Record: `record1qyqspmx9zsh9dkjrylxh3n2w9m50kctcvxz87gq9nsjkgc2mcjf3xkqtqvrxy6tyv3jhyscqqgpqpu82fnm3f8h0xnrreq5drhgvret6ayx4vml22s5k9h2xymjswqsv0va32kjmra24yuth70qkxgukzf3cmyg52q99dgf5ech0cm9zycrsvctdda6kuaprqqpqzqys922xuc7q435xq3vdv6rfm8dslwve5dv5zvcmv5tlnuuh0guzzyykju6lwa5kumn9wg3sqqspqrhtgj6zh0faaxnfuwf37j0me9qhckwfaxnw7s6m0h25qxuhzcdslr5dws9acjnnztgmc3prwc8l7js9ape3m7lv03lsgnfguwmydncrtz657h`

- Finish Bid:
    - Transition ID: `at1s35ms7ulmng8r4ctvsaegzm3qndv0hg6mrwafrryfk0g9q2jlggq3cp44e`
    - Output Record: `record1qyqsqs9j0s435ks07qzkydy654cp59ucc3wnq3zj9eg3ang2hgvwkgcrqvrxy6tyv3jhyscqqgpqqz224r93km6vstqgps0hdtxtvq8ep8w70w4syc3wpdgwxx2h5wc0vn4vwx34wy99y0gywrtzhpl52jsjg6uh8845pgdg9a3tukyhv5rqvctdda6kuaprqqpqzq89n5kurz0d2w40j88n38jy4pynsh3mzpmk4er4n5ak3trurufrq5ykju6lwa5kumn9wg3sqqspqpejkmeyzn58ztfz50r2qdhsr6f59hyeae9lfcca9axvz872krn3qqzh63rq9vq4vqam835ltqckceex40wau7u3tkv65ccylwdp6pcqg9z8lh`

- Claim Bid:
    - Transition ID: `at1jdur8qafyrpyxhs5duv9ymnekc98h2dp9xc9a0ucyst7autdmv9qnltftl`
    - Output Record: `record1qyqspydzp37w9megesdg3xpze7ndtwq0yk4adx0qpe3pmtzzadk09ggyqyrxzmt0w4h8ggcqqgqspq768kwwc5adnmcscvldhn3nanww3hg49am6gpszx466sqrg0gqs0a9teynh4cr0dwshttqk628fe38ds2r3n3j390vtrd59zh0w3qqs67q0wh`

# Signature:
## Sign with `true`:
- Command:
    ```sh
    leo account sign --private-key <redacted> --message true
    ```

- Output:
    ```sh
    sign1qkrrfsnqruewgqqxw7n95vlgs0kjpppgpnvlwsww3ax6yyuw65pyy96f828chdgv4xntqnlj5pxxd5dhl4dyjvxvpvpyss9uphjpzqtu23rr6mhkgkrusjsmmc7taewueergms2yf25r2fxqy9fphr4aqrj4uvr5pmmj9hcjx0g5kvp3mxavfe7fq5ppdgjnkpyg65u0acrsc8da4j4
    ```

# Signature:
## Sign with `true`:
- Command:
    ```sh
    leo account sign --private-key <redacted> --message true
    ```

- Output:
    ```sh
    sign1nujpjrjf59vnd73mg42zpzjvql6p746uuwdfklufpj5f3jg3zqpam3gpw58juwyvhwshpf9c4crym3s3hplkz0w693pzqwdg42e06q9z3ku2r6nfe0g0pf6e6tlvc53xrktfmtksdtq6l0q0c4kqtjnhq80h804g6x09zfctv4fk7ux2888jsmr59htqps7p3cg9amq5utaq660qnus
    ```

## Sign with `Transaction ID`:
- For me, program deployed Transaction ID is: `at18848cd65040znxpj3tksrm3k6e38zqxv2zmvhjpauaxrlnfr9upqgz9n39`. Command:
    ```sh
    leo account sign -d --private-key <redacted> --message "at18848cd65040znxpj3tksrm3k6e38zqxv2zmvhjpauaxrlnfr9upqgz9n39" --raw
    ```
- Output:
    ```sh
    sign1qn474nkd7hdp4yw7flvp7r5fn668lh0hc20mz3048e55fvwdqypa0cjppmdwrhj73hxmaqgpwceqhkqvf753mpas8a37k6c4v32hgq9z3ku2r6nfe0g0pf6e6tlvc53xrktfmtksdtq6l0q0c4kqtjnhq80h804g6x09zfctv4fk7ux2888jsmr59htqps7p3cg9amq5utaq6vswaxp
    ```