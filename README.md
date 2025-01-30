# TryHack3M-Bricks-Heist


**Got the target `10.10.140.218` and host `bricks.thm`**
After navigating to this url `https://bricks.thm` found this page

![home page](screenshots/Screenshot_2025-01-30_07_15_09.png)

**viewd source code to find any path or exposed directory**
![](screenshots/Screenshot_2025-01-30_07_15_15.png)
Figures it's an wordpress site by viewing the src o stylesheet.

**used `wpscan` to get more details about the plugins and themes**
command used: `wpscan --url https://bricks.thm/ --disable-tls-checks`
![](screenshots/Screenshot_2025-01-30_07_40_10.png)

as we can see the plugin and it's version searched for exploit and found this
![](/screenshots/Screenshot_2025-01-30_07_17_11.png)

**cloned the repo and run the exploit**
![](screenshots/Screenshot_2025-01-30_07_19_36.png)
**Got the shell**

As per question found this informations :
1. What is the content of the hidden .txt file in the web folder?
commands: `ls -al` then `cat 6**********.txt`
![](screenshots/Screenshot_2025-01-30_07_21_05.png)

2. What is the name of the suspicious process?
**used command**: `systemctl cat ubuntu.service`
![](screenshots/Screenshot_2025-01-30_07_47_40.png)

3. What is the service name affiliated with the suspicious process?
**used command**: `systemctl list-units --type=service`
![](screenshots/Screenshot_2025-01-30_07_24_51.png)

4. What is the log file name of the miner instance?
**used command**: `ls -al /lib/NetworkManager/`
![](screenshots/Screenshot_2025-01-30_07_52_02.png)

5. What is the wallet address of the miner instance?
we did find the id but it's seem encrypted so lets decrypt
![](screenshots/Screenshot_2025-01-30_07_55_28.png)

6. The wallet address used has been involved in transactions between wallets belonging to which threat group?

step 1 : navigate to : `https://blockchair.com/` and search up the address.
![](screenshots/Screenshot_2025-01-30_07_58_22.png)

step 2 : open transaction to see the details
![](screenshots/Screenshot_2025-01-30_07_58_35.png)

step 3: navigate to privacy section showing issues 
![](screenshots/Screenshot_2025-01-30_07_58_42.png)
![](screenshots/Screenshot_2025-01-30_07_59_21.png)

step 4: search each addresses on at a time and see
![](screenshots/Screenshot_2025-01-30_08_00_27.png)

step 5: read the articles
![](screenshots/Screenshot_2025-01-30_08_01_23.png)
and here we got the group name LockBit
