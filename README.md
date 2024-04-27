# Cybersecurity-Intro-workshop

Link to CFC notes: https://cfcapac.notion.site/CEW140424-0461f8b65fcd48579ed9cd652d0cc426

<h3>How hackers do manipulate other human beings?</h3>
- Using Fear, urgency, greed

<h3>Why it works?</h3>
- Emotions supersede common sense. Humans feel emotions first before logic.

<br>

```HTTP(Hyper Text Transfer Protocol)```

```HTTPS(Hyper Text Transfer Protocol Secure)```
- More and more phishing websites have https though

```Firefox``` would have warned not that the phishing site is not secure, ```google chrome``` did not

<h3>How to be more careful?</h3>
- slow down
- use antivirus, firewall
- ZERO TRUST POLICY - even if it seems like someone you know
- bookmark legit sites you use

<br>
<br>

<h3>What is IP Address:</h3>
- It's your device's unique ID on the web
- Internet Protocol Address (version4 - IPv4). It's a rule to locate a device on a network
- eg. 192.168.10.1
- 4 blocks of numbers separated by a period.
- How many permutations/total number of IP address? 256x256x256x256 = 4.29 billion
- Total human population - 8.1bil
- IPv4 Exhaustion - we officially ran out of IPv4 in 2011

<h3>How we address shortage problem?</h3>
- IPv6 - XXXX : XXXX : XXXX : XXXX: XXXX: XXXX:  XXXX: XXXX:
- 8 Blocks. 340 trillion

<h3>How do we deal with the lack of IPv4?</h3>
Division of internal and external IP address
- Interval vs External IP/ Private vs Public IP

<h3>External IP address</h3>
- external IP address is leased to you by ISP
- used for communication on the internet

<br>
<br>

<h3>How do we differentiate between internal and external addresses?</h3>

192.168.0.0 to 192.168.255.255 number range has been reserved for internal network/usage only
10.0.0.0 to 10.255.255.255 number range also reserved for internal usage
- but you only see that at like big offices with a lot of devices
  
<br>
<br>

<h3>Shodan</h3>
```Shodan``` can collect unsecured webcamera data, paid accounts can access and see them. I saw people's living rooms, main house gate entrance areas, offices and warehouses.

How to know if webcam you buy is secure? 
- check model and version, that they are updated to latest version

<h3>haveibeenpwned</h3>

Site that shows if your email has been found in a data breach: https://haveibeenpwned.com/

<h4>How to protect ourselves?</h4>

Good password hygiene
<ul>
  <li>use a different password for every account</li>
  <li>use a STRONG password - 13 or more characters</li>
  <li>Avoid modification of KNOWN words - eg. Password = P@s$w0rd!</li>
  <li>use password generator</li>
  <li>How to rmb? Use a password manager</li>
 <li>change password regularly (maybe yearly, but best is every few months)</li>
</ul>

<br>
<br>

![Time it takes to brute force in 2022](https://github.com/agentjimlam/Cybersecurity-Intro-workshop/assets/165074052/fc147308-564e-4213-a4cf-926970134f68)
<br>
Source: https://www.hivesystems.com/blog/are-your-passwords-in-the-green

![Time it takes CHATGPT to brute force in 2022](https://github.com/agentjimlam/Cybersecurity-Intro-workshop/assets/165074052/93f15515-b54e-45f4-9167-44ceceb8b39c)
<br>
Source: https://www.hivesystems.com/blog/are-your-passwords-in-the-green

<br>

<strong>Right now, AI only takes 8 months even to break a 12 char long, upper and lowercase + symbols + numbers password </strong>


<h4>What to do if password have been breached?</h4>
1. change the password, not same as previous ones
2. check if other info has been leaked

<br>
<br>
<br>


<h2>What is Stenography?</h3>
- Concept: Hiding data in the 2nd layer of another file

Refer to lab practice project in Kali-linux VM

<br>
<br>


<h2>Kali Linux</h2>

<br>
<br>


<h3>What is Kali Linux</h3>
- It is an OS, designed for Digital Forensics(blue team) and Penetration testing(Red team)

folder = directory

<h3>What is SSH?</h3>
- Secure SHell - allows us to connect to another computer via the terminal located somewhere else. You only see terminal. It is NOT Remote Desktop Protocol


<h3>What is BASH?</h3>
- BASH is a shell, it is a language used to interact with the system
- Why BASH?
  1. user-friendly
  2. linux friendly

<br>
<br>

<h3>CMD console</h3>
1. type - print 
2. dir - directory location you in
3. mkdir - create
4. cd - change directory
5. cls- clear
6. open notepad
7. dir /r - show contents of folder, including other layers/hidden files in folder 

<br>
<br>

<h3>Basic BASH Commands</h3>
1. clear or ctrl+L
2. pwd - print working directory/your location
- we are at home folder of user cew140424@ubuntu-CEW in the exercise
3. wget - download a file from the site given
4. ls - list directory
5. cat - print file

Sometimes our terminal will hang because of an incomplete command. Hit ```ctrl+c``` to end process and start again (ctrl + c shows as ```^C```)

<h3>Text Manipulation (Using BASH to analyse security)</h3>
- refer to course link at top

<h3>What is ```auth log```? </h3>
It is an authentication log for a linux's SSH service, it records all successful and failed attempts at logging into the machine via SSH

<br>
<br>

<h3>Additional Commands to further analyse auth.log?</h3>

<h4>How to filter?</h4>
Use | command 
1. grep filter for the specified word/term. | grep (word)
- grep (word)

2. You can chain filters
- ```grep (word1) | grep (word2)```

3. exclude out target word filter
- ```grep -v (word)```

4. counter
- ```wc -l```
- shows count of entries/events/interactions

5. see top part of output/print (top 10 lines default)
- ```| head``` 

6. see bottom part of output (bottom 10 lines default)
- ```| tail``` 

7. filter by columns
- awk '{print X $column}'

```
cat auth.log |grep Failed | grep root |grep -v invalid | awk '{print $11}'
```

every space is separator


```NF-Y``` = to count from X step from right to lelft

<h4>Why use NF-Y?</h4>
- Because not all the lines have same column numbers with same data type
- so there is some kind of standardized data placement/display where IP address is always 3 columns away from the right

<br>

```| sort```
Sort by number (from smallest to largest according to first character)
9 is below, 1 is at top, the 100 will be top

```| uniq```
Unique only works when sort is used first
- always rmb to do sort first, then do unique

```| uniq-c```
Counts the number of times the unique variable shows up, like username for example

```| sort -n``` 
- sort by numerical value, the higher value like 299 will be below


<br>
<br>
<br>

<h3>Challenge Lab part</h3>

Challenge part: determine how long is the duration from the start of the log to the first log for the target IP address? 

start time of auth.log.2 = Jan 31 04:41:02
first ip address timestamp = Jan 31 11:28:55

7hrs 47min, 55seconds = 420 + 47min 55sec = 467min 55 sec = 28020sec + 53sec = 28075


first timestamp = Jan 31 04:41:02 psimulator CRON[2372]: pam_unix(cron:session): session closed for user root
first ip address's timestamp = Jan 31 11:28:55 psimulator sshd[11628]: pam_unix(sshd:auth): authentication failure; logname= uid=0 euid=0 tty=ssh ruser= rhost=182.180.82.28  user=root

You can use | head to show first 10 log events, and | tail to show bottom 10 log events.



Qn: Assist the Security team in analyzing the auth.log.2 file and identify the number of unsuccessful access attempts made with the root username.

Qn: The security team has identified a series of access attempts from a range of IP addresses and needs assistance in calculating how many unique IPs were responsible for these unsuccessful entries.

Qn: Assist the investigators in identifying which IP address made the <a/b/c> number of unauthorized access attempts to the system.
- highest
- 2nd highest
- how many IP address have made over 10 unauthorized entry attempts into the system?






