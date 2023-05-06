# Lab 10
* # Hash function with randomization
    ```sh
    senku@Senku:/mnt/c/codes/design 6/iot/lesson10$ python3 hash_value.py
    The hash for 1 is: 1
    The hash for 1.0 is: 1
    The hash for 3.14 is: 322818021289917443
    The hash for Python is: -8088609925687507611
    The hash for a tuple of vowels is: 1051093065956816224
    The hash for an object of person is: -8824810098525850467
    senku@Senku:/mnt/c/codes/design 6/iot/lesson10$ python3 hash_value.py
    The hash for 1 is: 1
    The hash for 1.0 is: 1
    The hash for 3.14 is: 322818021289917443
    The hash for Python is: -5170201513910043555
    The hash for a tuple of vowels is: -5907524278951684598
    The hash for an object of person is: 3170565729335591051
    ```
    * Hash values for 1, 1.0 and 3.14 are the same. Hash values for Python, a tuple of vowels, an object of person are different
* # SHA-2 Secure Hash Algorithm
    ```sh
    senku@Senku:/mnt/c/codes/design 6/iot/lesson10$ python3 snakecoin.py
    Block #1 has been added to the blockchain!
    Hash: e5f9dda0ac00e6891c81d912657b25deae136280514bfb5c4edb75a0099bb135

    Block #2 has been added to the blockchain!
    Hash: 9902772e5883f2a7d4d0e76065eb2a7f24edef53c57844684825d120b1eb517d

    Block #3 has been added to the blockchain!
    Hash: 8e6d84e14048e8984c5c0638ada41ff4cff3fb8dec10e9a87683e7dd41fc2adb

    Block #4 has been added to the blockchain!
    Hash: 23b2e31e0712ed9cd3a85df0aa3c47cd1ca16bdaeb073be4c12e588d389da5a2

    Block #5 has been added to the blockchain!
    Hash: 5dcc8ec3c385728506e7dce06d886eecb2a33cd2526e7387a3acf40f847ab259

    Block #6 has been added to the blockchain!
    Hash: 54cbbfba40ec503712d571a9a241e3ffe57f364ed0591ff30b3eaf3d524d5bbe

    Block #7 has been added to the blockchain!
    Hash: a38318736ef1171484eb9cf5508d94fa57d0c789aa7d7f4ec0c2b9ef94baea82

    Block #8 has been added to the blockchain!
    Hash: 8789a74172a49dd26b9555feff33633baad0674e640c2370b7f756889f97fd2a

    Block #9 has been added to the blockchain!
    Hash: f7adc8f25922f9f3674ade620878b7a6f38488170ef3569c457c4c73abd0b068

    Block #10 has been added to the blockchain!
    Hash: 6957ea854727ef5cd71dd5674bf1f100deb8dc53a57ff1958a8a7a760d68bf6c

    Block #11 has been added to the blockchain!
    Hash: 77443730e963b3d3c0b0b1f85132241e48a134318ea1fc2b4556853bd1b6a5c5

    Block #12 has been added to the blockchain!
    Hash: 6541a3b80fe0dabc71d137edad832fd5d95608fb02e97f823aea33df62e7995f

    Block #13 has been added to the blockchain!
    Hash: 1a18e3985c1a65b32f1baf21ba97c2fb77d095d2bcdc39b92860bd080456822b

    Block #14 has been added to the blockchain!
    Hash: 51edb9e41523dd66db85215dcae3096fe1c997e6966c441fe846d2830c4f4b66

    Block #15 has been added to the blockchain!
    Hash: e750b7ae794c43ba0f6f61293a304721680f8157ca0059538c8f4c41397fd894

    Block #16 has been added to the blockchain!
    Hash: d5f117ca1a302715316f6f8dfccdfaa75d1db3cd287fe4631d690adb7ba94ff3

    Block #17 has been added to the blockchain!
    Hash: 7a7d5cb1993023007c7d35fd622098559b9d18be4e6486d1dfa962befb26b394

    Block #18 has been added to the blockchain!
    Hash: b3c4d03bd0e8b482dfdac2930cee62ec238399c4dfa4b06d249cdb506ccd5e80

    Block #19 has been added to the blockchain!
    Hash: 1416ab47047a50937856810bfa5df77705fd62c4dd0f4468a6a62ec86f554961

    Block #20 has been added to the blockchain!
    Hash: 0dd2de184cc042d852f8e16bb37c18af29d8b8544ae9e98353390a2d2d530f3d
    ```
* # Terminal 1: Run the SnakeCoin server at http://127.0.0.1:5000/
    ```sh
    python3 snakecoin-server-full-code.py
    * Serving Flask app 'snakecoin-server-full-code'
    * Debug mode: off
    WARNING: This is a development server. Do not use it in a production deployment. 
    Use a production WSGI server instead.
    * Running on http://127.0.0.1:5000
    Press CTRL+C to quit
    ```
* # Terminal 2: Create a transaction and mine a new block at http://127.0.0.1:5000/mine
    ```
    senku@Senku:/mnt/c/codes/design 6/iot/lesson10$ curl "localhost:5000/txion" \   
    >      -H "Content-Type: application/json" \
    >      -d '{"from": "akjflw", "to":"fjlakdj", "amount": 3}'
    Transaction submission successful
    senku@Senku:/mnt/c/codes/design 6/iot/lesson10$ curl localhost:5000/mine        
    {"index": 2, "timestamp": "2023-05-06 12:01:51.056098", "data": {"proof-of-work": 36, "transactions": [{"from": "akjflw", "to": "fjlakdj", "amount": 3}, {"from": "network", "to": "q3nf394hjg-random-miner-address-34nf3i4nflkn3oi", "amount": 
    1}]}, "hash": "88e2a9ca44271b72ef2f02fa89ce2936242ab64f775f01fbc0ab6a168e6714ca"}
    ```
    ![](/lab_10/server.PNG)
    ![](/lab_10/mine.PNG)
* # Terminal 1: Uncomment the last line of node_server.py (or search for port=8000) and run
    ```sc
    senku@Senku:/mnt/c/codes/design 6/iot/lesson10/python_blockchain_app$ python3 node_server.py
    * Serving Flask app 'node_server'
    * Debug mode: on
    WARNING: This is a development server. Do not use it in a production deployment. 
    Use a production WSGI server instead.
    * Running on http://127.0.0.1:8000
    Press CTRL+C to quit
    * Restarting with stat
    * Debugger is active!
    * Debugger PIN: 137-919-793
    ```
* # Terminal 2: Run run_app.py (Press Ctrl+C to quit)
    ```sc
    senku@Senku:/mnt/c/codes/design 6/iot/lesson10/python_blockchain_app$ python3 run_app.py
    * Serving Flask app 'app'
    * Debug mode: on
    WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
    * Running on http://127.0.0.1:5000
    Press CTRL+C to quit
    * Restarting with stat
    * Debugger is active!
    * Debugger PIN: 137-919-793
    ```
    ![](/lab_10/server%202.PNG)
    ![](/lab_10/mine%202.PNG)
    ![](/lab_10/server%203.PNG)