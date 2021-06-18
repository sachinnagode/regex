### cat regex18.txt 
834
519
4874
5
89
45687
25
645

### grep '^[0-9][0-9][0-9]$' regex18.txt 
### grep '^[0-9]{3}$' regex18.txt 
### cat regex19.txt 
lion
tiger
leopard
fox
kangaroo
bat
mouse
cuckoo
deer
### grep '^[a-z]{4,6}$' regex19.txt 
### cat regex20.txt 
ha
hahahahaha
hahaha
hahahaha
haha

hahahahahaha
hahahahahahahaha
hahahahahahahahaha
### grep '^(ha){4,}' regex20.txt 
### cat regex21.txt 
ha
haha
hahahahaha
hahahaha
hahaha
hahahahahahaha
hahahahahaha
### grep '^(ha){,2}$' regex21.txt 
### grep '^(ha){1,2}$' regex21.txt 
### grep -E  '^(ha){1,2}$' regex21.txt 
### grep -E '^(ha){1,2}$' regex21.txt 
### grep -E'^(ha){1,2}$' regex21.txt 
grep: invalid option -- '^'
Usage: grep [OPTION]... PATTERNS [FILE]...
Try 'grep --help' for more information.
### grep -E '^(ha){1,2}$' regex21.txt 
### grep -E '^(ha){,2}$' regex21.txt 
### grep -E '^(ha){4,}' regex20.txt 
hahahahaha
hahahaha
hahahahahaha
hahahahahahahaha
hahahahahahahahaha
### grep '^[a-z]{4,6}$' regex19.txt 
### grep -E '^[a-z]{4,6}$' regex19.txt 
### grep -E'^[a-z]{4,6}$' regex19.txt 
grep: invalid option -- '^'
Usage: grep [OPTION]... PATTERNS [FILE]...
Try 'grep --help' for more information.
### grep -E '^[a-z]{4,6}$' regex19.txt 
### cat regex21.txt 
ha
haha
hahahahaha
hahahaha
hahaha
hahahahahahaha
hahahahahaha
### cat regex22.txt 
fooaaaabar
fooabar
foobar
fooaabar
fooxxxbar
fooxbar
### 
### cat regex22.txt 
fooaaaabar
fooabar
foobar
fooaabar
fooxxxbar
fooxbar
### grep -E 'fooa+bar' regex22.txt 
fooaaaabar
fooabar
fooaabar
### cat regex23.txt 
https://website
http://website
httpss://website
httpx://website
httpxx://website
### grep '^https?.*'
^[[A^C
### grep '^https?.*' regex23.txt 
### grep -E '^https?.*' regex23.txt 





### grep -E '^https?://website' regex23.txt 
https://website
http://website
### cat  regex24.txt 
sapwood
rosewood
logwood
teakwood
plywood
redwood
### grep -E '^(log|ply)wood$
> ^C
### grep -E '^(log|ply)wood$' regex24.txt 
### grep -E '^(log|ply)wood' regex24.txt 
logwood
plywood
### sed -r 's/^(log|ply)wood/balle/g' regex24.txt 
sapwood
rosewood
balle
teakwood
balle
redwood
### cat regex25.txt 
1280x720
1920x1080
1600x900
1280x1024
800x600
1024x768
### sed -r 's/([0-9]+3)x([0-9]+3)/\1 pix by \2 pix/g'
^C
### sed -r 's/([0-9]+3)x([0-9]+3)/\1 pix by \2 pix/g' regex25.txt 
1280x720
1920x1080
1600x900
1280x1024
800x600
1024x768
### sed -r 's/([0-9]+)x([0-9]+)/\1 pix by \2 pix/g' regex25.txt 
1280 pix by 720 pix
1920 pix by 1080 pix
1600 pix by 900 pix
1280 pix by 1024 pix
800 pix by 600 pix
1024 pix by 768 pix
### cat regex25.txt 
1280x720
1920x1080
1600x900
1280x1024
800x600
1024x768
### sed -r 's/([0-9]+)x([0-9]+)/\1 pix by \2 pix/g' regex25.txt 
1280 pix by 720 pix
1920 pix by 1080 pix
1600 pix by 900 pix
1280 pix by 1024 pix
800 pix by 600 pix
1024 pix by 768 pix
###  cat regex25.txt 
1280x720
1920x1080
1600x900
1280x1024
800x600
1024x768
### cat regex26.txt 
John Wallace
Steve King
Martin Cook
Adam Smith
Irene Peter
Alice Johnson
### sed -r 's/([a-zA-Z]+)\s([a-zA-Z]+)/\2,\1/g' regex26.txt 
Wallace,John
King,Steve
Cook,Martin
Smith,Adam
Peter,Irene
Johnson,Alice
### cat regex27.txt 
7:32
6:12
12:23
1:23
11:33
4:21
### sed -r 's/([0-9]{1,2}):([0-9]{1,2})/\2 mins past \1/g' regex27.txt 
32 mins past 7
12 mins past 6
23 mins past 12
23 mins past 1
33 mins past 11
21 mins past 4
### sed -r 's/([0-9]{1,2}):([0-9]{2})/\2 mins past \1/g' regex27.txt 
32 mins past 7
12 mins past 6
23 mins past 12
23 mins past 1
33 mins past 11
21 mins past 4
### cat regex28.txt 
914.582.3013
873.334.2589
521.589.3147
625.235.3698
895.568.2145
745.256.3369
### sed -r 's/[0-9]{3}\.[0-9]{3}\.([0-9]{4})/xxx.xxx.\1/g' regex28.txt 
xxx.xxx.3013
xxx.xxx.2589
xxx.xxx.3147
xxx.xxx.3698
xxx.xxx.2145
xxx.xxx.3369
### cat regex29.txt 
Jan 5th 1987
Dec 26th 2010 
Mar 2nd 1923
Oct 1st 2008
Aug 3rd 2009
Jun 10th 2001
### sed -r 's/([a-zA-Z]{3})\s([0-9]{1,2}).*\s([0-9]{4})/\2-\1-\3/g' regex29.txt 
5-Jan-1987
26-Dec-2010 
2-Mar-1923
1-Oct-2008
3-Aug-2009
10-Jun-2001
### sed -r 's/([a-zA-Z]{3})\s([0-9]{1,2}).*\s[0-9]{2}([0-9]{2})/\2-\1-\3/g' regex29.txt 
5-Jan-87
26-Dec-10 
2-Mar-23
1-Oct-08
3-Aug-09
10-Jun-01
### cat regex30.txt 
(914).582.3013
(873).334.2589
(521).589.3147
(625).235.3698
(895).568.2145
(745).256.3369
### sed -r 's/\(([0-9]{3})\)(\.[0-9]{3}\.[0-9]{4})/\1\2/g
> ^C
### sed -r 's/\(([0-9]{3})\)(\.[0-9]{3}\.[0-9]{4})/\1\2/g' regex30.txt 
914.582.3013
873.334.2589
521.589.3147
625.235.3698
895.568.2145
745.256.3369
### a
