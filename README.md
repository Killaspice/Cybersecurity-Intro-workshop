# Cybersecurity-Intro-workshop


How hackers do manipulate other human beings?
- Using Fear, urgency, greed

Why it works?
- Emotions supersede common sense. Humans feel emotions first before logic.


HTTP(Hyper Text Transfer Protocol)

HTTPS(Hyper Text Transfer Protocol Secure)
- More and more phishing websites have https though

Firefox would have warned not the phishing site is not secure

How to be more careful?
- slow down
- use antivirus, firewall
- ZERO TRUST POLICY - even if it seems like someone you know
- bookmark legit sites you use


What is IP Address:
- It's your device's unique ID on the web
- Internet Protocol Address (version4 - IPv4). It's a rule to locate a device on a network
- eg. 192.168.10.1
- 4 blocks of numbers separated by a period.
- How many permutations/total number of IP address? 256x256x256x256 = 4.29 billion
- Total human population - 8.1bil
- IPv4 Exhaustion - we officially ran out of IPv4 in 2011

How we address shortage problem?
- IPv6 - XXXX : XXXX : XXXX : XXXX: XXXX: XXXX:  XXXX: XXXX:
- 8 Blocks. 340 trillion

How do we deal with the lack of IPv4?
Division of internal and external IP address
- Interval vs External IP/ Private vs Public IP

External IP address
- external IP address is leased to you by ISP
- used for communication on the internet


How do we differentiate between internal and external addresses?

192.168.0.0 to 192.168.255.255 number range has been reserved for internal network/usage only
10.0.0.0 to 10.255.255.255 number range also reserved for internal usage
- but you only see that at like big offices with a lot of devices


Shodan can collect unsecured webcamera data, paid accounts can see

How to know if webcam you buy is secure? check model and version

How to protect ourselves? 
- Good password hygiene
  1. use a different password for every account
  2. use a STRONG password - 13 or more characters
  3. Avoid modification of KNOWN words - eg. Password = P@s$w0rd!
  4. use password generator
  5. How to rmb? Use a password manager
  6. change password regularly (maybe yearly, but best is every few months)

What to do if password have been breached?
1. change the password, not same as previous ones
2. check if other info have been leaked


What is Stenography?
- Concept: Hiding data in the 2nd layer of another file


What is Kali Linus?
- It is an OS, designed for Digital Forensics(blue team) and Penetration testing(Red team)
- 

folder = directory

What is SSH?
- Secure SHell - allows us to connect to another computer via the terminal located somewhere else. You only see terminal. It is NOT Remote Desktop Protocol


What is BASH?
- BASH is a shell, it is a language used to interact with the system
- Why BASH?
  1. user-friendly
  2. linux friendly

CMD console
1. type - print 
2. dir - directory location you in
3. mkdir - create
4. cd - change directory
5. cls- clear
6. open notepad
7. dir /r - show contents of folder, including other layers/hidden files in folder 

Basic BASH Commands
1. clear or ctrl+L
2. pwd - print working directory/your location
- we are at home folder of user cew140424@ubuntu-CEW in the exercise
3. wget - download a file from the site given
4. ls - list directory
5. cat - print file

Sometimes our terminal will hang because of an incomplete command. Hit ctrl+c to end process and start again (ctrl + c shows as ^C)

Text Manipulation (Using BASH to analyse security)

What is auth log? it is an authentication log for a linux's SSH service, it records all successful and failed attempts at logging into the machine via SSH



Additional Commands to further analyse auth.log?

How to filter?
Use | command 
1. grep filter for the specified word/term. | grep (word)
- grep (word)

2. You can chain filters
- grep (word1) | grep (word2)

3. exclude out target word filter
- grep -v (word)

4. counter
- wc -l
- shows count of entries/events/interactions

5. see top part of output/print (top 10 lines default)
- | head 

6. see bottom part of output (bottom 10 lines default)
- | tail 

7. filter by columns
- awk '{print X $column}'

cat auth.log |grep Failed | grep root |grep -v invalid | awk '{print $11}'

every space is separator


NF-Y = to count from X step from right to lelft

Why use NF-Y?
- Because not all the lines have same column numbers with same data type
- so there is some kind of standardized data placement/display where IP address is always 3 columns away from the right



| sort
Sort by number (from smallest to largest according to first character)
9 is below, 1 is at top, the 100 will be top

| uniq 
Unique only works when sort is used first
- always rmb to do sort first, then do unique

| uniq-c
Counts the number of times the unique variable shows up, like username for example

| sort -n 
- sort by numerical value, the higher value like 299 will be below



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


Link to CFC notes: https://cfcapac.notion.site/CEW140424-0461f8b65fcd48579ed9cd652d0cc426




