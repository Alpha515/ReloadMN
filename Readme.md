## Reload Masternode Installation
Shell script to install a RLD Masternode on a Linux server running Ubuntu 16.04. This script was tested on a fresh install of Ubuntu 16.04 <a href="https://www.vultr.com/?ref=7424117">Vultr VPS</a>. Please use at your own risk.
***

## Installation for version 1.0.1.1 (TestNet)
Copy & paste the command below to your VPS to start the installation process.
```
cd && sudo apt-get update -y && sudo apt-get install p7zip-full -y && sudo apt-get -y install git && sudo git clone https://github.com/Alpha515/ReloadMN && cd ReloadMN/ && sudo bash RLD-instal.sh
```
***

## Desktop Wallet Setup

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:<br>
<OL>
  <li>Open the RLD Desktop Wallet.</li>
  <li>Go to RECEIVE and create a New Address and give it a name i.e. MN1</li>
  <li>Send 15,000,000 RLD to MN1.</li>
  <li>Wait for 16 confirmations.</li>
  <li>Go to Tools -> "Debug Console"</li>
  <li>Type the following command: masternode genkey</li>
  <li>Type the following command: masternode outputs</li>
  <li>Go to Tools -> "Open Masternode Configuration File"</li>
  <li>Add the following entry:

```
Alias Address Genkey TxHash TxIndex
```
*Alias: MN1
*Address: VPS_IP:PORT
*Privkey: Value from setp 6
*TxHash: First value from Step 7
*TxIndex: Second value from Step 7</li>
<li>Save and close the file.</li>
<li>Restart the wallet</li>
<li>Go to Masternode Tab. If you tab is not shown, please enable it from: Settings - Options - Wallet - Show Masternodes Tab</li>
<li>Click Update status to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is unlocked.</li>
<li>Select your MN and click Start Alias to start it.</li></OL>
Alternatively, open Debug Console and type:
```
masternode start-alias false MN1
```
Login to your VPS and check your masternode status by running the following command. If you get **status 4**, it means your masternode is active.
```
rld-cli masternode status
```
***

## Usage:
```
rld-cli mnsync status     #To check the sync status of the masternode
rld-cli masternode status #To check the status of the masternodes   
rld-cli getinfo           #To get information about RLD client 
```
Also, if you want to check/start/stop rld, run one of the following commands as root:
```
systemctl status rld.service      #To check if RLD service is running  
systemctl start rld.service       #To start RLD service  
systemctl stop rld.service        #To stop RLD service  
systemctl is-enabled rld.service  #To check if RLD service is enabled on boot  
```
***

## Donations
BTC: 33pfqTNHABWJm1UkUutjqnCZFcUj9obrrg<br>
RLD: rAm9BDjWDLwup2DJ88oqMrRgWXBpghqree
