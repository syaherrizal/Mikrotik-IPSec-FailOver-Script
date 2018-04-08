# Mikrotik-IPSec-FailOver
Before use this script make sure you read thinks below

1. This failover script only work for IPSec peer with static destination ip address
2. This failover script only work to failover responder IP Address
2. This failover script user mikrotik tools (Netwatch)

1. Dynamic Destination Address
SD-IPSec-FailOver-DOWN 
SD-IPSec-FailOver-UP

2. Static Destination Address
SS-IPSec-FailOver-DOWN
SS-IPSec-FailOver-UP 



Make sure to set primary host to monitor example "xxx.xxx.xxx.xxx" also interval and timeout value.

Make sure to set comment in policy and peer, this help script detect witch rule will be change the value.



How its work?
Condition 1 : Primary host UP
- if primary host UP and dst-address in peer same as with primary host than no change
Condition 2 : Primary host DOWN
- if primary host Down and dst-address in peer same as with primary host than change dst-address & sa-dst-address to secondary
Condition 3 : Primary host UP after DOWN
- if primary host UP and dst-address in peer not same as with primary host than change dst-address & sa-dst-address to primary
