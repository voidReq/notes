|        |           |                                                                                                                                                                                                                      |
| ------ | --------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -a     | amode     | Force attack mode (1 = static WEP, 2 = WPA/WPA2-PSK)                                                                                                                                                                 |
| -e     | essid     | If set, all IVs from networks with the same ESSID will be used. This option is also required for WPA/WPA2-PSK cracking if the ESSID is not broadcasted (hidden)                                                      |
| -b     | bssid     | Long version --bssid. Select the target network based on the access point's MAC address                                                                                                                              |
| -p     | nbcpu     | On SMP systems: # of CPU to use. This option is invalid on non-SMP systems                                                                                                                                           |
| -q     | _none_    | Enable quiet mode (no status output until the key is found, or not)                                                                                                                                                  |
| -C     | MACs      | Long version --combine. Merge the given APs (separated by a comma) into virtual one                                                                                                                                  |
| -l     | file name | (Lowercase L, ell) logs the key to the file specified. Overwrites the file if it already exists                                                                                                                      |
| Option | Param.    | Description                                                                                                                                                                                                          |
| -c     | _none_    | Restrict the search space to alpha-numeric characters only (0x20 - 0x7F)                                                                                                                                             |
| -t     | _none_    | Restrict the search space to binary coded decimal hex characters                                                                                                                                                     |
| -h     | _none_    | Restrict the search space to numeric characters (0x30-0x39) These keys are used by default in most Fritz!BOXes                                                                                                       |
| -d     | start     | Long version --debug. Set the beginning of the WEP key (in hex), for debugging purposes                                                                                                                              |
| -m     | maddr     | MAC address to filter WEP data packets. Alternatively, specify -m ff:ff:ff:ff:ff:ff to use all and every IVs, regardless of the network                                                                              |
| -n     | nbits     | Specify the length of the key: 64 for 40-bit WEP, 128 for 104-bit WEP, etc. The default value is 128                                                                                                                 |
| -i     | index     | Only keep the IVs that have this key index (1 to 4). The default behaviour is to ignore the key index                                                                                                                |
| -f     | fudge     | By default, this parameter is set to 2 for 104-bit WEP and to 5 for 40-bit WEP. Specify a higher value to increase the bruteforce level: cracking will take more time, but with a higher likelyhood of success       |
| -k     | korek     | There are 17 korek statistical attacks. Sometimes one attack creates a huge false positive that prevents the key from being found, even with lots of IVs. Try -k 1, -k 2, … -k 17 to disable each attack selectively |
| -x/-x0 | _none_    | Disable last keybytes brutforce                                                                                                                                                                                      |
| -x1    | _none_    | Enable last keybyte bruteforcing (default)                                                                                                                                                                           |
| -x2    | _none_    | Enable last two keybytes bruteforcing                                                                                                                                                                                |
| -X     | _none_    | Disable bruteforce multithreading (SMP only)                                                                                                                                                                         |
| -s     | _none_    | Show the key in ASCII while cracking                                                                                                                                                                                 |
| -y     | _none_    | Experimental single bruteforce attack which should only be used when the standard attack mode fails with more than one million IVs                                                                                   |
| -z     | _none_    | Invokes the PTW WEP cracking method (Default in v1.x)                                                                                                                                                                |
| -P     | number    | Long version --ptw-debug. Invokes the PTW debug mode: 1 Disable klein, 2 PTW.                                                                                                                                        |
| -K     | _none_    | Invokes the Korek WEP cracking method. (Default in v0.x)                                                                                                                                                             |
| -D     | _none_    | Long version --wep-decloak. Run in WEP decloak mode                                                                                                                                                                  |
| -1     | _none_    | Long version --oneshot. Run only 1 try to crack key with PTW                                                                                                                                                         |
| -M     | number    | (WEP cracking) Specify the maximum number of IVs to use                                                                                                                                                              |
| -V     | _none_    | Long version --visual-inspection. Run in visual inspection mode (only with KoreK)                                                                                                                                    |
| Option | Param.    | Description                                                                                                                                                                                                          |
| -w     | words     | Path to a wordlists or “-” without the quotes for standard in (stdin). Separate multiple wordlists by comma                                                                                                          |
| -N     | file      | Create a new cracking session and save it to the specified file                                                                                                                                                      |
| -R     | file      | Restore cracking session from the specified file                                                                                                                                                                     |

##### WPA-PSK options

|Option|Param.|Description|
|---|---|---|
|-E|file>|Create EWSA Project file v3|
|-j|file|Create Hashcat v3.6+ Capture file (HCCAPX)|
|-J|file|Create Hashcat Capture file|
|-S|_none_|WPA cracking speed test|
|-Z|sec|WPA cracking speed test execution length in seconds|
|-r|database|Utilizes a database generated by [airolib-ng](https://www.aircrack-ng.org/doku.php?id=airolib-ng "airolib-ng") as input to determine the WPA key. Outputs an error message if aircrack-ng has not been compiled with sqlite support|

##### SIMD Selection

|Option|Param.|Description|
|---|---|---|
|--simd|optimization|Use user-specified SIMD optimization instead of the fastest one|
|--simd-list|_none_|Shows a list of the SIMD optimizations available|

##### Other options

|Option|Param.|Description|
|---|---|---|
|-H|_none_|Long version --help. Output help information|
|-u|_none_|Long form --cpu-detect. Provide information on the number of CPUs and features available such as MMX, SSE2, AVX, AVX2, AVX512|

***EX***
-------------------------------------------
aircrack-ng -K 128bit.ivs  
Where:

- 128bit.ivs is the file name containing IVS.
    
- -K: Use KoreK attacks only
--------------------------------
To WEP dictionary crack a 64 bit key:

aircrack-ng -w h:hex.txt,ascii.txt -a 1 -n 64 -e teddy wep10-01.cap

Where:

- -w h:hex.txt,ascii.txt is the list of files to use. For files containing hexadecimal values, you must put a “h:” in front of the file name.
    
- -a 1 says that it is WEP
    
- -n 64 says it is 64 bits. Change this to the key length that matches your dictionary files.
    
- -e teddy is to optionally select the access point. Your could also use the “-b” option to select based on MAC address
    
- wep10-01.cap is the name of the file containing the data. It can be the full packet or an IVs only file. It must contain be a minimum of four IVs.
----------------------------------------------
 aircrack-ng -z ptw*.cap  

Where:

- -z means use the PTW methodology to crack the wep key. _Note:_ in v1.x, this is the default attack mode; use -K to revert to Korek.
    
- ptw*.cap are the capture files to use.
- -----------------------------------------------------
- ### WPA

Now onto cracking WPA/WPA2 passphrases. Aircrack-ng can crack either types.

aircrack-ng -w password.lst *.cap  
Where:

- -w password.lst is the name of the password file. Remember to specify the full path if the file is not located in the same directory.
    
- *.cap is name of group of files containing the captured packets. Notice in this case that we used the wildcard * to include multiple files.
- -----------------------------------------------------
- Cracking can sometimes take a very long time and it is sometimes necessary to turn off the computer or put it to sleep for a while. In order to handle this kind of situation, a new set of option has been created.

It will create and/or update a session file saving the current status of the cracking (every 10 minutes) as well as all the options used, wordlists and capture files used. Multiple wordlists can be used and it works with WEP and WPA.

aircrack-ng --new-session current.session -w password.lst,english.txt wpa-01.cap 

In order to restore the session, use --restore-session:

aircrack-ng --restore-session current.session

It will keep updating _current.session_ every 10 minutes.

Limitations:

- The wordlist must be files. For now, they cannot be _stdin_ or [airolib-ng](https://www.aircrack-ng.org/doku.php?id=airolib-ng "airolib-ng") databases
    
- Session has to be restored from the same directory as when first using --new-session
    
- No new options can be added when restoring session
- ------------------------------------
- ### How to use the key

If aircrack-ng determines the key, it is presented to you in hexadecimal format. It typically looks like:

 KEY FOUND! [11:22:33:44:55]

The length will vary based on the WEP bit key length used. See the table above which indicates the number of hexadecimal characters for the various WEP key bit lenghts.

You may use this key without the “:” in your favorite client. This means you enter “1122334455” into the client and specify that the key is in hexadecimal format. Remember that most keys cannot be converted to ASCII format. If the HEX key is in fact valid ASCII characters, the ASCII will also be displayed.

If you wish to experiment a bit with converting HEX to ASCII, see this [FAQ entry](https://www.aircrack-ng.org/doku.php?id=faq#how_do_i_convert_the_hex_characters_to_ascii "faq").

We do not specifically provide support or the details on how to configure your wireless card to connect to the AP. For linux, this [page](https://web.archive.org/web/20080212235953/http://wirelessdefence.org/Contents/LinuxWirelessCommands.htm "https://web.archive.org/web/20080212235953/http://wirelessdefence.org/Contents/LinuxWirelessCommands.htm") has an excellent writeup. As well, search the internet for this information regarding linux and Windows systems. As well, see the documentation for your card's wireless client. If you are using linux, check the mailing lists and forums specific to the distribution.

Additionally, Aircrack-ng prints out a message indicating the likelihood that the key is correct. It will look something similar to “Probability: 100%”. Aircrack-ng tests the key against some packets to confirm the key is correct. Based on these tests, it prints the probability of a correct key.

Also remember we do not support or endorse people accessing networks which do not belong to them.

### How to convert the hex key back to the passphrase?

People quite often ask if the hexadecimal key found by aircrack-ng can be converted backwords to the original “passphrase”. The simple answer is “NO”.

To understand why this is so, lets take a look at how these passphrases are converted into the hexadecimal keys used in WEP.

Some vendors have a wep key generator which “translates” a passphrase into a hexadecimal WEP key. There are no standards for this. Very often they just pad short phrases with blanks, zeroes or other characters. However, usually the passphrases are filled with zeros up to the length of 16 bytes, and afterwards the MD5SUM of this bytestream will be the WEP Key. Remember, every vendor can do this in a slightly different way, and so they may not be compatible.

So there is no way to know the how long the original passphrase was. It could as short as one character. It all depends on the who developed the software.

Knowing all this, if you still wish to try to obtain the original passphrase, Latin SuD has a tool which attempts reverse the process. Click [here](https://www.latinsud.com/wepconv.html "https://www.latinsud.com/wepconv.html") for the tool.

Nonetheless, these passphrases result in a WEP Key that is as easily cracked as every other WEP Key. The exact conversion method really does not matter in the end.

Keep in mind that wep passwords that look like “plain text” might either be ASCII or PASSPHRASE. Most (all) systems support ASCII and are the default, but some support passphrase and those which support it require users to specify whether it's ascii or a passphrase. Passphrases can be any arbitrary length. ASCII are usually limited to 5 or 13 (wep40 and wep104).

As a side note, Windows WZC only supports fixed length hex or ascii keys, so the shortest inputable key is 5 characters long. See the table above on this page regarding how many characters are needed for specific key lengths.