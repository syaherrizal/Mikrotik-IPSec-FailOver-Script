# Mikrotik-IPSec-FailOver
Before use this script make sure you read thinks below

1. This failover script only use for IPSec peer with static destination ip address
2. This failover script only work to failover responder IP Address
2. This failover script user mikrotik tools (Netwatch)

Make sure to set primary host to monitor example "xxx.xxx.xxx.xxx" also interval and timeout value.

How its work?
Condition 1 : Primary host UP
- if primary host UP and dst-address in peer same as with primary host than no change
Condition 2 : Primary host DOWN
- if primary host Down and dst-address in peer same as with primary host than change dst-address & sa-dst-address to secondary
Condition 3 : Primary host UP after DOWN
- if primary host UP and dst-address in peer not same as with primary host than change dst-address & sa-dst-address to primary
