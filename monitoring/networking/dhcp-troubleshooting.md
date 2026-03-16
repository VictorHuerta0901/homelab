Problem
Ubuntu VM did not receive IPv4 address.

Investigation
Running ip a showed only IPv6 address.

Cause
DHCP request was not triggered automatically.

Solution
sudo dhclient ens18

Result
VM received address 10.0.0.164 and network connectivity was restored.
