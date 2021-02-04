# POA
PROOF OF AUTHORITY
Why POA
Proof-of-Authority is a newer concept in the blockchain world where you have a number of pre-approved authority nodes called sealers. Any new node to add has to be voted on by the currently approved set of authority nodes, this provides a full control over which nodes can seal blocks (mine) on the private network.

The Ethereum Proof-of-Authority protocol is called Clique and is well described in the Clique Github issue. Ethereum currently uses this algorithm for the Kovan test network.

Proof-of-Authority is a near perfect fit for private networks but not at all suited for public networks where the trust should be as distributed as possible.


![POA](https://github.com/docfern/POA/blob/main/pictures/POA.png)

How to Start a POA Network
Generate two new nodes as pre-approved sealer addresses by creating accounts with a separate datadir using geth.
./geth --datadir node1 account new
./geth --datadir node2 account new

Generate Genesis Block
Run puppeth and follow the wizard
Choose Clique (Proof of Authority) consensus algorithm
Choose a block time
Paste both account addresses from the first step one at a time into the list of accounts to seal.
Paste them again in the list of accounts to pre-fund.
You can choose no for pre-funding the pre-compiled accounts.
Complete the rest of the prompts, and when you are back at the main menu, choose the "Manage existing genesis" option.
Export genesis configurations. This will fail to create two of the files, but you only need networkname.json.
With the genesis block creation completed, we will now initialize the nodes with the genesis' json file.
Initialize Nodes
Run the nodes in separate terminal windows with the commands:

./geth --datadir node1 --unlock "SEALER_ONE_ADDRESS" --mine --rpc --allow-insecure-unlock
./geth --datadir node2 --unlock "SEALER_TWO_ADDRESS" --mine --port 30304 --bootnodes "enode://SEALER_ONE_ENODE_ADDRESS@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock
MyCrypto for Testing
![Change Network](https://github.com/docfern/POA/blob/main/pictures/change_network.jpg)

Open the MyCrypto app
Click Change Network at the bottom left
Click "Add Custom Node"
Fill in the blanks
Choose Custom on the Network
![Custom](https://github.com/docfern/POA/blob/main/pictures/setup_custom.jpg)

clicking
Image(filename = PATH + "before_clicking.jpg", width=500, height=500)
![Before Clicking](https://github.com/docfern/POA/blob/main/pictures/before_clicking.jpg)


Image(filename = PATH + "after_clicking.jpg", width=500, height=500)
![After Clicking](https://github.com/docfern/POA/blob/main/pictures/after_clicking.jpg)


Image(filename = PATH + "successful.jpg", width=500, height=500)
![Successful](https://github.com/docfern/POA/blob/main/pictures/successful.jpg)

jpg
Image(filename = PATH + "winston.jpg", width=500, height=500)
![Winston Successful](https://github.com/docfern/POA/blob/main/pictures/winston.jpg)
