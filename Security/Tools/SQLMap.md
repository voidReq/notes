***Parameters***
---------------------------------------------  
-h: help  
-v: Verbosity level (takes 1-6)  
-u: The URL  
Request types(Leave empty for http){  
	--data=DATA         Data string to be sent through POST (e.g. "id=1")  
	--cookie=COOKIE     HTTP Cookie header value (e.g. "PHPSESSID=a8d127e..")  
	--random-agent      Use randomly selected HTTP User-Agent header value. Use if blocked by firewall  
    --proxy=PROXY       Use a proxy to connect to the target URL  
    --tor               Use Tor anonymity network  
    --check-tor         Check to see if Tor is used properly  
}  
Detection phase{  
	--level=LEVEL       Level of tests to perform (1-5, default 1)  
    --risk=RISK         Risk of tests to perform (1-3, default 1)  
}  
Enumeration{  
	-a, --all           Retrieve everything  
    -b, --banner        Retrieve DBMS banner  
    --current-user      Retrieve DBMS current user  
    --current-db        Retrieve DBMS current database  
    --passwords         Enumerate DBMS users password hashes  
    --dbs               Enumerate DBMS databases  
    --tables            Enumerate DBMS database tables  
    --columns           Enumerate DBMS database table columns  
    --schema            Enumerate DBMS schema  
    --dump              Dump DBMS database table entries  
    --dump-all          Dump all DBMS databases tables entries  
    -D DB               DBMS database to enumerate  
    -T TBL              DBMS database table(s) to enumerate  
    -C COL              DBMS database table column(s) to enumerate  
}  
  
