# Final Exam 2420

## Authur 
### Aashay Bharadwaj 

## Part 1 
sudo apt update && sudo apt upgrade -y

## Part 2
![](images/part1.png)
![](images/part1-boot.png)
![](images/part1-json.png)


## Part 3
journalctl -b -p 0..4  -o json-pretty


Part 4
script 
 `#!/bin/bash
#: Title        : Print user Service                                   
#: Date         : December 8, 2022                         
#: Author       : Aashay Bharadwaj                                
#: Version      : 1.0                                       
#: Description  : Print users with UID between 1000-5000 and the current logged in user
echo "Regular users on the system are:" 
grep -E '^([^:]*:){2}([1-4][0-9]{3}|5000):' /etc/passwd

echo "Users currently logged in are:" 
who | grep $USER -o
`
saved in dir /opt/final

## Part 5

 `[UNIT]
Description=Service to start final script to print users

[Service]
Type=simple
ExecStart=/opt/final

[Install]
WantedBy=multi-user.target`

file save in dir /etc/systemd/system

## Part 6
`Description=Timer to start the final  service which prints user info everyday after boot

[Timer]
OnCalender=*_*_* 05:00:00
Persistent=true

[Install]
WantedBy=timers.target`

file save in /etc/systemd/system




