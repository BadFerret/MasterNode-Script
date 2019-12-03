![Logo](https://allforonebusiness.org/wp-content/uploads/2018/12/Logo_allforone.png)
# All For One Business Masternode Setup Guide
This guide will assist you in setting up a All For One Business Masternode on a Linux Server running Ubuntu 16.04. (this may also work on Ubuntu 18.04, but 16.04 is the suggested version)

This guide will show you the safest way to run a masternode.  This setup is knows as a Hot/Cold wallet setup.  In this setup you will have 2 wallets (one with the coins, and one without the coins).  It is the safest setup because your coins will reside in a "cold" wallet ("cold" means that it does not need to constantly be connected to the internet). In this setup, there is very little risk of someone hacking onto your wallet and taking your coins.

If you require further assistance contact the support team @ [Discord](https://discord.gg/F7WEQNy)
***
## Requirements
1) **1,001 Acreage coins. (1000.01 coins will work, but it is simpler to say 1001 is required)**
2) **A Vultr VPS running Linux Ubuntu 16.04. (Ubuntu 18.04 may work, but it is suggested to use 16.04)**
3) **A Windows, Mac, or Linux QT wallet running on a local machine (like your home computer).**
4) **An SSH client such as [Bitvise](https://dl.bitvise.com/BvSshClient-Inst.exe)**
***
## Contents
* **Section A**: Preparing the local (cold) wallet
* **Section B**: Obtaining coins to run a masternode
* **Section C**: Downloading and installing Bitvise.
* **Section D**: Connecting to the VPS and installing the MN script via Bitvise.
* **Section E**: Connecting & Starting the masternode.
***

## Section A: Preparing the local (cold) wallet 
***Step 1***
* Download the latest "QT" wallet for your operating system
- [Windows 32bit] (https://www.google.com)
- [Windows 64bit] (https://www.google.com)
- [Macintosh] (https://www.google.com)

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


## Section B: Downloading and installing BitVise. 

***Step 1***
* Download Bitvise [here](https://dl.bitvise.com/BvSshClient-Inst.exe)
***

***Step 2***
* Select the correct installer depending upon your operating system. Then follow the install instructions. 

![Example-BitVise Installer](https://i.imgur.com/yF3694G.png)
***


## Section C: Connecting to the VPS & Installing the MN script via Bitvise.

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

## Section D: Preparing the Local wallet

***Step 1***
* Download and install the Acreage wallet [here](https://acreagecoin.io/)
***

***Step 2***
* Send EXACLY 5,000 ACR to a receive address within your wallet.
***

***Step 3***
* Create a text document to temporarily store information that you will need. 
***

***step 4***
* Go to the console within the wallet 

![Example-console](https://i.imgur.com/6NM7G9a.png)
***

***Step 5***
* Type the command below and press enter 

`masternode outputs` 

![Example-outputs](https://i.imgur.com/GD7Ro1m.png)
***

***Step 6***
* Copy the long key (this is your transaction ID) and the 1 or 2 at the end (this is your output index)
* Paste these into the text document you created earlier as you will need them in the next step.
***

# Section E: Connecting & Starting the masternode 

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
