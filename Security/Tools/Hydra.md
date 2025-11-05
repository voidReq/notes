#ssh #hydra #bruteforce
  
***PARAMETER LIST***  
-----------------------------------------  
-s: Port  
-L: The username list //use a lowercase L with a username if you don't want a wordlist  
-P: The password list //use a lowercase P with a username if you don't want a wordlist  
ssh: Attacks ssh server  
ftp: Attacks ftp server  
-t: The number of parallel threads working on the task  
-M: IP range list  
-v: Activates verbose mode (shows each attempt  
-C: Combolist  
-h: help  
-d: Enables debug mode, showing all details  
-o: Saves results to a file (usage: -o result:txt) (can also be other file types)  
-e: Activates checking mutations of each password{  
	nsr: checks null, same, and reverse  
}  
-R: Use **hydra -R** to resume an interrupted attack  
-x: random characters (check examples) (min:max:charset============>)  
  
***EXAMPLE LIST***  
-----------------------------------------  
Bruteforce username and passwords of an ssh server: **hydra -L user.txt -P pass.txt x ssh -t 4**{  
	-L: The username list   
	-P: The password list   
	x: Target address  
	ssh: The mode  
	-t: The number of parallel threads working on the task  
}  
  
Bruteforce an ftp server with -x: **hydra -l ignite -x 1:3:1& ftp://192.168.1.141**{  
	-x:{  
	1: The min number of characters per pswd  
	3: The max number of characters  
	1: Char set (1 for numbers, a for lowercase and A for uppercase characters) (Characters following this argument are automatically added to the char set)  
	&: Also char set  
	}  
}  
