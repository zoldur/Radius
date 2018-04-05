# Radius
Shell script to install a [Radius Masternode](http://www.radiuscrypto.online/) on a Linux server running Ubuntu 16.04. Use it on your own risk.
***

## Installation
```
wget -q https://raw.githubusercontent.com/zoldur/Radius/master/radius_install.sh
bash radius_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the Radius Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **1000** RADIUS to **MN1**. You need to send all 1000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **masternode outputs**  
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash TxIndex
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* TxIndex:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is un
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
masternode start-alias MN1
``` 
14. Login to your VPS and check your masternode status by running the following command. 
```
radius-cli masternode status
```
***

## Usage:
```
radius-cli masternode status  
radius-cli getinfo
```
Also, if you want to check/start/stop **Radius**, run one of the following commands as **root**:

```
systemctl status Radius #To check if Radius service is running  
systemctl start Radius #To start Radius service  
systemctl stop Radius #To stop Radius service  
systemctl is-enabled Radius #To check if Radius service is enabled on boot  
```  
***

## Donations

Any donation is highly appreciated

**RADIUS**: RRJ3k3LmtVeaMdZqxsBcvdPF5879fw2CQW  
**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh  
**ETH**: 0x26B9dDa0616FE0759273D651e77Fe7dd7751E01E  
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB  
