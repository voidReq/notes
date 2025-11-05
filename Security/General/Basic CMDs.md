#arp #basics #cd #chmod #cp #echo #ifconfig #ip #iwconfig #kali #locate #mkdir #mousepad #nano #navigation #passwd #rm #route #terminal #usage -----------------Navigation
**pwd: Show current directory**
-pwd
**rm: Remove directory (or file)**
-rm %fileName%
-rm -r //to rm empty files
**mkdir: Makes new directory**
mkdir %directoryName%
**cd: Change directory**
-cd %directory%
Ex: cd Downloads || cd ..
**ls: List directory**
-ls (folderName)
-Returns non-hidden files in active directory. use "ls -la" for hidden files

-----------------**Forensics**
**locate/find: Finds a file anywhere**
-locate/find %fileName%
**file: Shows file type**
-file %fileName%
**cat: Reads file contents**
-cat %fileName%
-Create a file: cat > %fileName%.txt
**exiftool: Shows file details**
-exiftool %fileName
**grep: Searches for keywords**
-grep '%keyword%' %directoryName%
**fls: Dump partition table of disk image**
-fls
**base64**: Decode a base64 string
-base64 -d (prompts a string to be entered)

-----------------**File manipulation**

**cp: Copies a file into a different directory**
-cp %fileName% %directoryName%
**echo: Can be used to make and write to a file**
-echo "%msg%" > %fileName%
-You can use >> to add more contents on a new line without overr
Ex: -echo "Hello" > hello.txt
**touch: Makes an empty file**
-touch
**nano: a GUI for writing and making files**
-nano %fileName%
**mousepad/nano: Creates file, writes to it, opens in notepad**
-mousepad/nano %fileName%

**chmod: Changes perms of a file**
-chmod +%perms% %fileName%
Ex: chmod +rwx hello.txt //Gives read, write, execute
Ex: chmod 777 hello.txt //Gives all perms
![d2c5ef5701e3014cd8a6a61572cf30d0.png](:/b8b26e20f4154a9c91c8b06257210705)
**unzip/gunzip: Unzips a file**
-unzip/gunzip %fileName%

-----------------**Users*

**passwd**
-Changes pswd
**adduser: Adds a new user**
-adduser %userName%
**su: Switches user**
-su %userName%

-----------------**Networking**

**ifconfig: Gives basic information including what kind of /network, and ipv4, etc**
-ifconfig
**ping: pings**
-ping %ip%
Use > to put into a txt
Ex: ping xxx.xxx.xxx.xxx -c 1 > randomFile.txt
**iwconfig: Shows wireless connections**
-iwconfig
**ip: Shows basic ip information**
-ip a: same info as ifconfig
-ip n: most basic data, ipv4 and ipv6 (same as arp -a)
-ip r: Routing data (same as route)

-----------------**Cryptography**
**md5sum/sha256sum: Encrypts poorly**
-md5sum/sha256sum %fileName%.txt

