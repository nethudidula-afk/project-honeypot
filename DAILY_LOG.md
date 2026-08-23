## 2026-08-17

I learned what honey pots are and decided to learn how they work. After a bit of YouTube and chatGPT, i had figured out roughly what i needed to make a honey pot. also, since i am only somewhat proficient in python, i needed to figure out how to use logging, socket, and datetime. so i started learning what each of them are and how they work using YouTube videos and Coursera. then, i had to research about which ports are safe to open with out giving access in to anything important, so i could use it for tests. for this, i decided on port 2222.

## 2026-08-18

while doing the reading on Coursera, i came up with a line that said there were legal limits on what you can do with honeypots such as, you cant counter attack, you cant store sensitive data, such as the attackers personal info, like, name, address, etc. And i have to be careful to only capture attacker IPs, not innocent users.i also cannot actively lure someone in to it. and while not legal, i must make it somewhat secure to ensure that the attacker cant actually perform a virtual privilege escalation attack. this means i will need a virtual machine.

## 2026-08-20

i read a bit more about the legalities involved as i was confused as to the time i could store them for, i was also confused as to why you would have a honey pot is the IP address is all you wanted to take, as it was clear what much more could be done, such as precise location tracking unless using whonix, tor, or a vpn. also, i can get the OS data, to figure out what type of operating systems were used to perform attacks. but ultimate, i didn't want to challenge the law, so i decided to only log the IP, and delete the data after 4-6 hours. i also, would want to deploy it for different times such as once at 8am, to 2pm, 12 am to 8pm, by doing this, i can get a good image of what times these attacks where active, and could make a rough guess of where the person is, i suppose? 

##2026-08-21

i tried my first attempt, which could only open port 2222, and close it successfully, which worked. then i moved on to logging the date and time and the IP of the attacker, which proved to be quite difficult as i had forgotten how to format things. but eventually, i made a prototype that could listen into port 2222, and log it in a file, along with the date, time and the IP of the attacker. the problem was that with a bit of tinkering, an outsider can get into my my account, then system32, and that was a very big problem.

##2026-08-21

my uncle had made a online, virtual server, and he added me, which meant that i can now safely run this with out the risk of getting actually attacked. this lead to another problem which was that knew nothing about servers, or how to handle them. but after some trouble, eventually my uncle managed to teach me how to join and use the server where i managed to run the honeypot, which worked and i could log the data. the problem was that it works only on port 2222, and not a spectrum such as 1~2000, which meant unless a very specified attack occurs, the chances are, i wont catch anything. 

