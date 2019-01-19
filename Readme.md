## Reload Masternode Installation
Shell script to install a RLD Masternode on a Linux server running Ubuntu 16.04. Use it on your own risk.

***

## Installation for version X.X.X
```
cd && sudo apt-get update -y && sudo apt-get update -y && sudo apt-get install p7zip-full -y && sudo apt-get -y install git && sudo git clone https://github.com/Alpha515/ReloadMN && cd ReloadMN/ && sudo bash RLD-instal.sh
```
***

## Desktop wallet setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:<br>
<UL>
  <li>Open the RLD Desktop Wallet.</li>
  <li>Go to RECEIVE and create a New Address: MN1</li>
</UL>
1.Open the RLD Desktop Wallet.<br>
2.Go to RECEIVE and create a New Address: MN1
3.Send 15,000,000 RLD to MN1.
4.Wait for 16 confirmations.
5.Go to Tools -> "Debug Console"
6.Type the following command: masternode genkey
7.Type the following command: masternode outputs
8.Go to Tools -> "Open Masternode Configuration File"
9.Add the following entry:
```
Alias Address Genkey TxHash TxIndex
```
*Alias: MN1
*Address: VPS_IP:PORT
*Privkey: Value from setp 6
*TxHash: First value from Step 7
*TxIndex: Second value from Step 7
10ave and close the file.
11Go to Masternode Tab. If you tab is not shown, please enable it from: Settings - Options - Wallet - Show Masternodes Tab
12Click Update status to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.
13Select your MN and click Start Alias to start it.
14Alternatively, open Debug Console and type:
```
masternode start-alias false MN1
```
Login to your VPS and check your masternode status by running the following command. If you get **status 4**, it means your masternode is active.
```
bltg-cli masternode status
```
***

## Usage:
```
bltg-cli mnsync status
bltg-cli masternode status  
bltg-cli getinfo
```
Also, if you want to check/start/stop bltg, run one of the following commands as root:
```
systemctl status bltg.service #To check if BLTG service is running  
systemctl start bltg.service #To start BLTG service  
systemctl stop bltg.service #To stop BLTG service  
systemctl is-enabled bltg.service #To check if BLTG service is enabled on boot  
```
***

## Donations


