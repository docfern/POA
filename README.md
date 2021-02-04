# POA
### PROOF OF AUTHORITY<br>
#### Why POA<br>
Proof-of-Authority is a newer concept in the blockchain world where you have a number of pre-approved authority nodes called sealers. Any new node to add has to be voted on by the currently approved set of authority nodes, this provides a full control over which nodes can seal blocks (mine) on the private network.<br>
<br>
The Ethereum Proof-of-Authority protocol is called Clique and is well described in the Clique Github issue. Ethereum currently uses this algorithm for the Kovan test network.<br>
<br>
Proof-of-Authority is a near perfect fit for private networks but not at all suited for public networks where the trust should be as distributed as possible.<br>
<br>

![POA](https://github.com/docfern/POA/blob/main/pictures/POA.png)
<br>
#### How to Start a POA Network<br>
Generate two new nodes as pre-approved sealer addresses by creating accounts with a separate datadir using geth.
- ./geth --datadir node1 account new
- ./geth --datadir node2 account new

Generate Genesis Block<br>
Run puppeth and follow the wizard<br>
Choose Clique (Proof of Authority) consensus algorithm<br>
Choose a block time<br>
Paste both account addresses from the first step one at a time into the list of accounts to seal.<br>
Paste them again in the list of accounts to pre-fund.<br>
You can choose no for pre-funding the pre-compiled accounts.<br>
Complete the rest of the prompts, and when you are back at the main menu, choose the "Manage existing genesis" option.<br>
Export genesis configurations. This will fail to create two of the files, but you only need networkname.json.<br>
With the genesis block creation completed, we will now initialize the nodes with the genesis' json file.<br>
Initialize Nodes<br>
Run the nodes in separate terminal windows with the commands:<br>

- ./geth --datadir node1 --unlock "SEALER_ONE_ADDRESS" --mine --rpc --allow-insecure-unlock
- ./geth --datadir node2 --unlock "SEALER_TWO_ADDRESS" --mine --port 30304 --bootnodes "enode://SEALER_ONE_ENODE_ADDRESS@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock
<br>

#### MyCrypto for Testing<br>

![Change Network](https://github.com/docfern/POA/blob/main/pictures/change_network.jpg)
<br>
<br>
Open the MyCrypto app<br>
Click Change Network at the bottom left<br>
Click "Add Custom Node"<br>
Fill in the blanks<br>
Choose Custom on the Network<br>
![Custom](https://github.com/docfern/POA/blob/main/pictures/setup_custom.jpg)
<br>
<br>
![Before Clicking](https://github.com/docfern/POA/blob/main/pictures/before_clicking.jpg)
<br>
<br>
![After Clicking](https://github.com/docfern/POA/blob/main/pictures/after_clicking.jpg)


![Successful](https://github.com/docfern/POA/blob/main/pictures/successful.jpg)

![Winston Successful](https://github.com/docfern/POA/blob/main/pictures/winston.jpg)
