# Code_Injector
Code injector is used to run bad code in background process, you can modify the code inside program.

Usage:
First Terminal:

pip install netfilterqueue

python code_injector.py

Second Terminal: 
Outside the Machine:

iptables -I FORWARD -j NFQUEUE --queue-num 0

Inside the machine:

iptables -I OUTPUT -j NFQUEUE --queue-num 0

iptables -I INPUT -j NFQUEUE --queue-num 0

python arp_spoofer.py

Third Terminal:

echo 1 > /proc/sys/net/ipv4/ip_forward

All Finished:

iptables --flush
