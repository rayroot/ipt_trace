# ipt_trace
Just like a PRISM for tuning iptables, especially in the case of NetworkPolicy on Kubernetes, and still on proccess. if you have any idea, let me know please! 

First of all, thanks to @yadutaf , because this work most come from the project of tracepkt 

Usage: ./ipt_trace.py [TARGET_IP] 
The result maybe : 
```
# ./ipt_trace.py  10.233.75.138

    NETWORK NS        INTERFACE    TYPE ADDRESSES                          IPTABLES
[  4026531992]             eth0 request 10.200.0.11 -> 10.233.75.138           raw.PREROUTING  :ACCEPT
[  4026531992]             eth0 request 10.200.0.11 -> 10.233.75.138        mangle.PREROUTING  :ACCEPT
[  4026531992]             eth0 request 10.200.0.11 -> 10.233.75.138           nat.PREROUTING  :ACCEPT
[  4026531992]             eth0 request 10.200.0.11 -> 10.233.75.138        mangle.FORWARD     :ACCEPT
[  4026531992]             eth0 request 10.200.0.11 -> 10.233.75.138        filter.FORWARD     :ACCEPT
[  4026531992]  calia2e8da4e94c request 10.200.0.11 -> 10.233.75.138        mangle.POSTROUTING :ACCEPT
[  4026531992]  calia2e8da4e94c request 10.200.0.11 -> 10.233.75.138           nat.POSTROUTING :ACCEPT
[  4026531992]  calia2e8da4e94c   reply 10.233.75.138 -> 10.200.0.11           raw.PREROUTING  :ACCEPT
[  4026531992]  calia2e8da4e94c   reply 10.233.75.138 -> 10.200.0.11        mangle.PREROUTING  :ACCEPT
[  4026531992]  calia2e8da4e94c   reply 10.233.75.138 -> 10.200.0.11        mangle.FORWARD     :ACCEPT
[  4026531992]  calia2e8da4e94c   reply 10.233.75.138 -> 10.200.0.11        filter.FORWARD     :ACCEPT
[  4026531992]             eth0   reply 10.233.75.138 -> 10.200.0.11        mangle.POSTROUTING :ACCEPT

[  4026531992]  calia2e8da4e94c request 10.233.75.138 -> 10.233.75.137         raw.PREROUTING  :ACCEPT
[  4026531992]  calia2e8da4e94c request 10.233.75.138 -> 10.233.75.137      mangle.PREROUTING  :ACCEPT
[  4026531992]  calia2e8da4e94c request 10.233.75.138 -> 10.233.75.137         nat.PREROUTING  :ACCEPT
[  4026531992]  calia2e8da4e94c request 10.233.75.138 -> 10.233.75.137      mangle.FORWARD     :ACCEPT
[  4026531992]  calia2e8da4e94c request 10.233.75.138 -> 10.233.75.137      filter.FORWARD     :ACCEPT
[  4026531992]  cali6ee846a124e request 10.233.75.138 -> 10.233.75.137      mangle.POSTROUTING :ACCEPT
[  4026531992]  cali6ee846a124e request 10.233.75.138 -> 10.233.75.137         nat.POSTROUTING :ACCEPT
[  4026531992]  cali6ee846a124e   reply 10.233.75.137 -> 10.233.75.138         raw.PREROUTING  :ACCEPT
[  4026531992]  cali6ee846a124e   reply 10.233.75.137 -> 10.233.75.138      mangle.PREROUTING  :ACCEPT
[  4026531992]  cali6ee846a124e   reply 10.233.75.137 -> 10.233.75.138      mangle.FORWARD     :ACCEPT
[  4026531992]  cali6ee846a124e   reply 10.233.75.137 -> 10.233.75.138      filter.FORWARD     :ACCEPT
[  4026531992]  calia2e8da4e94c   reply 10.233.75.137 -> 10.233.75.138      mangle.POSTROUTING :ACCEPT
```
