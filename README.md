![Logo](https://allforonebusiness.org/wp-content/uploads/2018/12/Logo_allforone.png)
# All For One Business Masternode Setup Guide
This guide will assist you in setting up a All For One Business Masternode on a Linux Server running Ubuntu 16.04. (this may also work on Ubuntu 18.04, but 16.04 is the suggested version)

This guide will show you the safest way to run a masternode.  This setup is knows as a Hot/Cold wallet setup.  In this setup you will have 2 wallets (one with the coins, and one without the coins).  It is the safest setup because your coins will reside in a "cold" wallet ("cold" means that it does not need to constantly be connected to the internet). In this setup, there is very little risk of someone hacking onto your wallet and taking your coins.

If you require further assistance contact the support team @ [Discord](https://discord.gg/F7WEQNy)
***
## Requirements
1) **1,001 AFO coins. (1000.01 coins will work, but it is simpler to say 1001 is required)**
2) **A Vultr VPS running Linux Ubuntu 16.04. (Ubuntu 18.04 may work, but it is suggested to use 16.04)**
3) **A Windows, Mac, or Linux QT wallet running on a local machine (like your home computer).**
4) **An SSH client such as [Bitvise](https://dl.bitvise.com/BvSshClient-Inst.exe)**
***
## Contents
* **Section A**: Preparing the local (cold) wallet
* **Section B**: Obtaining the coins to run a masternode
* **Section C**: Creating the collateral transaction
* **Section D**: Creating the VPS within Vultr
* **Section E**: Downloading and installing Bitvise.
* **Section F**: Connecting to the VPS and installing the MN script via Bitvise.
* **Section G**: Connecting and starting the masternode.
***

## Section A: Preparing the local (cold) wallet 
***Step 1***
* Download the latest "QT" wallet for your operating system
  * Windows 32bit (https://www.google.com)
  * Windows 64bit (https://www.google.com)
  * Macintosh (https://www.google.com)
***

***Step 2***
* Install the wallet and allow it to synchronize fully. If there are no connections or it is synchronizing slowly, go to the discord server and search for `addnode` nodes to add to your wallet to speed it up.
***

## Section B: Obtaining the coins to run a masternode. 
Now you need to get the coins to run a masternode.  Remember, you will need a little more than 1000 coins to start a masternode.  1000.01 coins would be enough, but usually i get 1001 coins to be safe.  You need this small amount of extra coins to pay the transaction fee to make the "collateral transaction" in a later step below.  If you already have enough coins to run the masternode, then just skip to next section (Creating the collateral transaction).  If you do not have enough coins yet, then follow these instructions.

***Step 1***
* Open the wallet and go to the `Receive` tab to create a new receiving address.
* Type a label for this address in the `Label` field. If you are getting coins from an exchange, use a label like `From Graviex` or if you are buying in presale use a lable like `From Presale`.
* Click the `Request Payment` button.
* A new window will pop up, in that window, you will see an address labelled `address`.  This is the address you will receive your coins on. Click the `Copy Address` button at the bottom of the window to copy the address to your clipboard. If you are withdrawing from the exchange, withdraw to this address.  If you are buying from presale, give this address to the person selling you the coins.
  *NOTE: Always send a small amount of coins to your address first to test it.  If the test is successful, then send the full amount.  Meaning, if you are withdrawing from an exchange, just withdraw 1 coin.  If you receive that coin in your wallet, then withdraw the rest of the coins.
* Once you have at least 1000.01 coins in your wallet, you can move on the the next section.  
***

## Section C: Creating the collateral tranaction.
In this section you will be sending yourself exactly 1000 coins in one single transaction. This is known as the `collateral transaction`. As long as you are running your masternode, these coins will be locked in your wallet and will not stake, they will only be used to keep your masternode running.

***Step 1***
* Open the wallet and go to the `Receive` tab to create a new masternode (receiving) address.
* Type `MN1` as the label for this address in the `Label` field.
* Click the `Request Payment` button.
* A new window will pop up, in that window, you will see an address labelled `address`.  This will be your masternode address and it is where you will send the 1000 coins. Click the `Copy Address` button at the bottom of the window to copy the address to your clipboard.
***

***Step 2***
* Go to the `Send` tab in the wallet and paste the address from your clipboard into the `Pay To` field.  The `Label` field should automatically fill in with `MN` (or whatever you labelled your masternode address).  If it does not autofill with the masternode address label, then do not continue as you will not be sending the coins to yourself, try step 1 above again.
***

***Step 3***
* Enter exactly 1000 in the `Amount` box. And then click the `Send` button.
***

## Section D: Creating the VPS within [Vultr](https://www.vultr.com/?ref=8337866-4F) 
***Step 1***
* Register at [Vultr](https://www.vultr.com/?ref=8337866-4F)
***

***Step 2***
* After you have added funds to your account go [here](https://my.vultr.com/deploy/) to create your Server
***

***Step 3*** 
* Choose a server location (preferably somewhere close to you)
![Example-Location](https://i.imgur.com/ozi7Bkr.png)
***

***Step 4***
* Choose a server type: Ubuntu 16.04
![Example-OS](https://i.imgur.com/aSMqHUK.png)
***

***Step 5***
* Choose a server size: $5/mo will be fine 
![Example-OS](https://i.imgur.com/UoGoHcM.png)
***

***Step 6*** 
* Set a Server Hostname & Label (name it whatever you want)
![Example-hostname](https://i.imgur.com/uu0rvOr.png)
***

***Step 7***
* Click "Deploy now"

![Example-Deploy](https://i.imgur.com/4qpYuH0.png)
***

## Section E: Downloading and installing BitVise. 

***Step 1***
* Download Bitvise [here](https://dl.bitvise.com/BvSshClient-Inst.exe)
***

***Step 2***
* Select the correct installer depending upon your operating system. Then follow the install instructions. 

![Example-BitVise Installer](https://i.imgur.com/yF3694G.png)
***


## Section F: Connecting to the VPS & Installing the MN script via Bitvise.

***Step 1***
* Copy your VPS IP (you can find this by going to the server tab within Vultr and clicking on your server. 
![Example-Vultr](https://i.imgur.com/z41MiwY.png)
***

***Step 2***
* Open the bitvise application and fill in the "Hostname" box with the IP of your VPS.
![Example-PuttyInstaller](https://i.imgur.com/vkN1alC.png)
***

***Step 3***
* Copy the root password from the VULTR server page.
![Example-RootPass](https://i.imgur.com/JnXQXav.png)
***

***Step 4***
* Type "root" as the login/username.
![Example-Root](https://i.imgur.com/5TPoE9x.png)
***

***Step 5*** 
* Paste the password into the Bitvise terminal by right clicking (it will not show the password so just press enter)
![Example-RootPassEnter](https://i.imgur.com/zVhOAKu.png)
***

***Step 6*** 
* Once you have clicked open it will open a security alert (click yes).  
***

***Step 7***
* Paste the code below into the Bitvise terminal then press enter (it will just go to a new line)
![Example-RootPassEnter](https://i.imgur.com/K6xlnav.png)

`wget -q https://raw.githubusercontent.com/AcreageCoin/MasterNode-Script/master/acr_install.sh`
***

***Step 8***
* Paste the code below into the Bitvise terminal then press enter

`bash acr_install.sh`

![Example-Bash](https://i.imgur.com/myvmKTE.png)

***

***Step 9***
* Sit back and wait for the install (this will take 10-20 mins)
***

***Step 10***
* When prompted to enter your Masternode Gen key - press enter

![Example-installing](https://i.imgur.com/sLvWd1S.png)
***

***Step 11***
* You will now see all of the relavant information for your server.
* Keep this terminal open as we will need the info for the wallet setup.
![Example-installing](https://i.imgur.com/Q87LcnW.png)
***

# Section G: Connecting & Starting the masternode 

***Step 1***
* Go to the tools tab within the wallet and click open "masternode configuration file" 
![Example-create](https://i.imgur.com/COsfvfA.png)
***

***Step 2***

* Fill in the form. 
* For `Alias` type something like "MN01" **don't use spaces**
* The `Address` is the IP and port of your server (this will be in the Bitvise terminal that you still have open).
* The `GenKey` is your masternode GEN key (This is also in the Bitvise terminal that you have open).
* The `TxHash` is the transaction ID/long key that you copied to the text file.
* The `Output Index` is the 0 or 1 that you copied to your text file.
![Example-create](https://i.imgur.com/9b1I3bk.png)

Click "File Save"
***

***Step 3***
* Close out of the wallet and reopen Wallet
*Click on the Masternodes tab "My masternodes"
* Click start all in the masternodes tab
***

***step 4***
* Check the status of your masternode within the VPS by using the command below:

`arc-cli masternode status`

`acr-cli getinfo`

*You should see ***status 4 or 9***

If you do, congratulations! You have now setup a masternode. If you do not, please contact support and they will assist you.


Made By BitYoda
