# Blockchain
New net is a blockchain network which was set up for Zbank and can be utilized to test the transfer of ethereum from network to network. 

To run run the network you should download the github repository including the newnet.json file and the two file folders for each of the nodes. Save these files into the directory which contains your blockchain tools such as puppeth and geth.

IN order to launch the network you should run the following commands in git bash. ensure you are in the blockchain directory prior to running.

#1 initialize the network
You should run puppeth and initialize a network called newnet referring to the JSON file for details on the network

#2 launch the notes
./geth --datadir node1 --unlock "E198332e9a6BeE136FF9FBcD86b54bb3c71e3cE2" --mine --rpc --allow-insecure-unlock
./geth --datadir node2 --unlock "69ba263dC8d68752221B6b5c4561E6b703a76B54" --mine --port 30304 --bootnodes "enode://c6c173ce949d1b80b6f7e2e9f806867dc29735b0bd9598a5ba684fb57b6bb19da0ba7c982800d5922486fd3bbff6e826544c239f037981e3dd8d848f37667a28@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock

#3 Connect to Crytpo Wallet once both nodes are up and running. 

    * Open the MyCrypto app, then click `Change Network` at the bottom left:

    ![change network](Images/change-network.png)

    * Click "Add Custom Node", then add the custom network information that you set in the genesis.

    * Make sure that you scroll down to choose `Custom` in the "Network" column to reveal more options like `Chain ID`:

    ![custom network](Images/custom-network.png)

    * Type `ETH` in the Currency box.
    
    * In the Chain ID box, type the chain id you generated during genesis creation.

    * In the URL box type: `http://127.0.0.1:8545`.  This points to the default RPC port on your local machine.

    * Finally, click `Save & Use Custom Node`. 


#4 Test networks by sending money between the accounts

   * Select the `View & Send` option from the left menu pane, then click `Keystore file`.

    ![select_keystore_file](Images/select_keystore_file.png)

    * On the next screen, click `Select Wallet File`, then navigate to the keystore directory inside your Node1 directory, select the file located there, provide your password when prompted and then click `Unlock`.

    * This will open your account wallet inside MyCrypto. 
    
    * Looks like we're filthy rich! This is the balance that was pre-funded for this account in the genesis configuration; however, these millions of ETH tokens are just for testing purposes.   

    ![keystore_unlock](Images/keystore_unlock.gif)

    * In the `To Address` box, type the account address from Node2, then fill in an arbitrary amount of ETH:

     ![transaction send](Images/transaction-send.png)

    * Confirm the transaction by clicking "Send Transaction", and the "Send" button in the pop-up window.  

    ![Send transaction](Images/send-transaction.gif)

    * Click the `Check TX Status` when the green message pops up, confirm the logout:

    ![check tx](Images/check-tx-status.png)

    * You should see the transaction go from `Pending` to `Successful` in around the same blocktime you set in the genesis.

    * You can click the `Check TX Status` button to update the status.

    ![successful transaction](Images/transaction-status.png)

Congratulations, you successfully created your own private blockchain on newnet!
