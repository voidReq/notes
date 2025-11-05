**Parameters**
---------------------------------------

-m: Hash type{
0: md5
100:SHA1
}


-a: Attack mode{
0: Dictionary (ex: hashcat -m 0 -a 0 md5.txt rockyou.txt )
1: Combinator (tries combinations of words from wordlist)
3: Mask attack (see below)
6: Hybrid (wordlists+mask)
7: Hybrid(masks+wordlists)
9: Association (Username, filename, hints, etc)
}

**MASK ATTACK**
-----------------------------------
https://hashcat.net/wiki/doku.php?id=mask_attack
- ?l = abcdefghijklmnopqrstuvwxyz
- ?u = ABCDEFGHIJKLMNOPQRSTUVWXYZ
- ?d = 0123456789
- ?h = 0123456789abcdef
- ?H = 0123456789ABCDEF
- ?s = «space»!"#$%&'()**+,-./:;<=>?@[]^_`{|}~<</>><<*>>
- ?a = ?l?u?d?s
- ?b = 0x00 - 0xff
 Ex: ?l?u?d: Would crack for combinations like aA0, fQ4, etc.