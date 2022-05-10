# EC441 final Ziwen Xie & Xinyu Liu
## Question 1 : Mininet
### Question 1.1
We created a python topology:
``` python
from mininet.link import Link,TCLink
from mininet.node import Node,Host,OVSSwitch,Controller
from mininet.net import Mininet,CLI
from mininet.log import setLogLevel
from mininet.topo import Topo
from mininet.topolib import TreeTopo


class MyTopo( Topo ):
    
    def build( self ):

        # Add hosts and switches
        h1 = self.addHost( 'h1',ip = '128.197.128.9' )
        h2 = self.addHost( 'h2',ip = '128.197.128.10' )
        
        s1 = self.addSwitch( 's1' )
        s2 = self.addSwitch( 's2' )
        #rightSwitch = self.addSwitch( 's4' )

        # Add links
        self.addLink( h1, s1, bw='1m')
        self.addLink( s1,s2, bw='1m')
        self.addLink( s2,h2, bw='1m')
        
        
        #net.get('h1').setIP('')
        


topos = { 'mytopo': ( lambda: MyTopo() ) }
```
After that we execute the command
```sh
sudo mn --custom topo.py --topo mytopo
```
to start a mininet session

### Question 1.2 
we started a xterm session
```sh
xterm h1 h2
```
Then, We first use HTTP to tranmit the wordle.txt file
In the h1 node
 we enter# EC441 final Ziwen Xie & Xinyu Liu
## Question 1 : Mininet
### Question 1.1
We created a python topology:
``` python
from mininet.link import Link,TCLink
from mininet.node import Node,Host,OVSSwitch,Controller
from mininet.net import Mininet,CLI
from mininet.log import setLogLevel
from mininet.topo import Topo
from mininet.topolib import TreeTopo


class MyTopo( Topo ):
    
    def build( self ):

        # Add hosts and switches
        h1 = self.addHost( 'h1',ip = '128.197.128.9' )
        h2 = self.addHost( 'h2',ip = '128.197.128.10' )
        
        s1 = self.addSwitch( 's1' )
        s2 = self.addSwitch( 's2' )
        #rightSwitch = self.addSwitch( 's4' )

        # Add links
        self.addLink( h1, s1, bw='1m')
        self.addLink( s1,s2, bw='1m')
        self.addLink( s2,h2, bw='1m')
        
        
        #net.get('h1').setIP('')
        


topos = { 'mytopo': ( lambda: MyTopo() ) }
```
After that we execute the command
```sh
sudo mn --custom topo.py --topo mytopo
```
to start a mininet session

### Question 1.2 
we started a xterm session
```sh
xterm h1 h2
```
Then, We first use HTTP to tranmit the wordle.txt file
In the h1 node
 we enter
 ```sh
 python3 -m http.server 90&
 ```
 to create a server
 and then we make h2 as a client by 
 ```sh
 wget --output-document=/home/josie/wordle.txt 128.197.128.9
 ```
 to get the file
 In the report we can see that the speed is 1mb/s
 
 for UDP we use the `iperf` to genrate udp tranmission in a 2 second time frame
 for ICMP we `ping` h1 and h2
 for ARP we boradcast
 
 they all recorded in a PCAPNG file attached
 

 ```sh
 python3 -m http.server 90&
 ```
 to create a server
 and then we make h2 as a client by 
 ```sh
 wget --output-document=/home/josie/wordle.txt 128.197.128.9
 ```
 to get the file
 In the report we can see that the speed is 1mb/s
 
 for UDP we use the `iperf` to genrate udp tranmission in a 2 second time frame
 for ICMP we `ping` h1 and h2
 for ARP we boradcast
 
 they all recorded in a PCAPNG file attached
 
