## background

hello, i am Nethu Liyanagunawardana and i am a tech, cyber security and hacking enthusiast. i play around with cyber security and attack tools and play around fixing computers. 
in early august, 2026, i met Vajira Ginneliya, an experienced software engineer working in the Financial Technology domain. i mentioned my interest in cyber security, and hacking. and showed him a 15 year old computer that i had fixed and run kali linux on. then i proceed to ask if he would guide me through a security related project.
he suggested a variety of ideas which i decided to build the honey pot idea he presented, and a daily stand-up where i can ask questions about things i didn't understand.


## 2026-08-17

we had our first discussion about the project, and vajira decided to make it a week long project, from today, monday to the 24th. so i first researched.
I learned what honey pots are and learn how they work. After a bit of YouTube and chatGPT, and help from my vajira, i had figured out roughly what i needed to make a honey pot. also, since i am only somewhat proficient in python, i needed to figure out how to use logging, socket, and datetime. so i started learning what each of them are and how they work using YouTube videos and Coursera. then, i had to research about which ports are safe to open with out giving access in to anything important, so i could use it for tests. for this, i decided on port 2222.

## 2026-08-18

while doing the reading on Coursera, i came up with a line that said there were legal limits on what you can do with honeypots such as, you cant counter attack, you cant store sensitive data, such as the attackers personal info, like, name, address, etc. And i have to be careful to only capture attacker IPs, not innocent users. i also cannot actively lure someone in to it. and while not legal, i must make it somewhat secure to ensure that the attacker cant actually perform a virtual privilege escalation attack. this means i will need a virtual machine.

the link to the site:  https://cyberdefensereview.army.mil/Portals/6/Documents/CDR%20Journal%20Articles/WALLACE_VISGER_CDR_V3N2_SUMMER-2018_Complete-4.pdf?ver=2018-09-05-090305-017

## 2026-08-20

i read a bit more about the legalities involved as i was confused as to the time i could store them for, i was also confused as to why you would have a honey pot is the IP address is all you wanted to take, as it was clear what much more could be done, such as precise location tracking unless using whonix, tor, or a vpn. also, i can get the OS data, to figure out what type of operating systems were used to perform attacks. but ultimate, i didn't want to challenge the law and after discussing with my uncle, i decided to only log the IP, and delete the data after 4-6 hours. i also, would want to deploy it for different times such as once at 8am, to 2pm, 12 am to 8pm, by doing this, i can get a good image of what times these attacks where active, and could make a rough guess of where the person is, i suppose? 

## 2026-08-21

i tried my first attempt, which could only open port 2222, and close it successfully, which worked. then i moved on to logging the date and time and the IP of the attacker, which proved to be quite difficult as i had forgotten how to format things. but eventually, i made a prototype that could listen into port 2222, and log it in a file, along with the date, time and the IP of the attacker. the problem was that with a bit of tinkering, an outsider can get into my account, then system32, and that was a very big problem.
<img width="608" height="95" alt="image" src="https://github.com/user-attachments/assets/76e19896-58cd-4518-9461-af9557d75407" />
<img width="931" height="874" alt="Screenshot 2026-08-23 200817" src="https://github.com/user-attachments/assets/bdf33fd3-92c4-4dd1-9916-76d80a4f8660" />
<img width="1051" height="455" alt="Screenshot 2026-08-23 200826" src="https://github.com/user-attachments/assets/cfef718b-3600-403a-ae28-261c0ca34d69" />



## 2026-08-22

vajira had made a online, virtual server, and he added me, which meant that i can now safely run this with out the risk of getting actually attacked. this lead to another problem which was that i knew nothing about servers, or how to handle them. but after some trouble, eventually vajira managed to teach me how to join and use the server where i managed to run the honeypot, which worked and i could log the data. the problem was that it works only on port 2222, and not a spectrum such as 1~2000, which meant unless a very specified attack occurs, the chances are, i wont catch anything. 
he then took some time to teach me about ssh key-gen, ssh name@IP, tcpdump, and a few more tools.

## 2026-08-23

i reflect upon the day before yesterday, as vajira managed to find a vulnerability and perform a log injection and scare me. 
<img width="1877" height="828" alt="Screenshot 2026-08-23 180820" src="https://github.com/user-attachments/assets/964ec2bd-d412-491e-82f4-d432c0182a39" />
the weakness happened to be: data 
<img width="925" height="74" alt="image" src="https://github.com/user-attachments/assets/247cfa11-f411-454f-b523-4fa42b46cb04" />

where the logging doesn't look for embedded newlines, and .strip() doesn't sanitise the code, it removes the white space at the end of the code, not the \n in the middle.                                
this pointed out that once again, i am still learning, and i was no where near skilled.
we also discussed a bit more into weaknesses of the honeypot i made, then taught me a bit about log injection. 
