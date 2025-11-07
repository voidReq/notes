# NOTE:
- I hope to update this soon. I don't know when I wrote this, but I think it was a while ago, and looking back on it, it's not my best work...
## Combining commands
- Use | to separate commands
- Use > to put into a txt
- Ex: cat ip.txt | grep "64 bytes" | cut -d " " -f 4 | tr -d ":"
- The above enters ip.txt, finds the line that says "64 bytes", and cuts on the fourth segment, segmented by spaces. It then takes out any colons in the line.
## For loops
- Use $x in the command to input x
- Use $ with a number to reference a specific arg
- Remember to run chmod +x %fileName% if you want to run it
- Run by typing ./%fileName%
- In a loop, end the line with an & to run multiple times at once, or a ; to run one at a time
## RUN:
`./%fileName% argOne arg2 arg3 etc`

## EXAMPLE:

```
#!/bin/bash //Lets computer know where it runs from
if [  "$1"  ==  "" ] //Checks if first (second) parameter is empty
then
echo" You forgot an IP address! Use ./ipsweep %firstThreeOctets%"

else
for ip in `seq 1 254`; do
ping -c 1 $1$ip | grep "64 bytes" | cut -d " " -f 4 | tr -d ":" & //Ampersand lets it check multiple ips at once
done //Finishes "for" loop
fi //Finishes "if" "else"
```

- Run using ./ipsweep 192.168.4
- Pair with: for ip in $(cat ips.txt); do nmap $ip; done