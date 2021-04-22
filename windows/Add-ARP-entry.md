# Adding an ARP entry in Windows

## Clear the ARP cache
Clearing the ARP cache gives us a "fresh start". We can clear the cache with the following
command:
```batch
arp -d
```

## Adding a new ARP entry
Now that we've cleared the ARP entry, we can add a new entry using the following command:
```batch
arp -s 192.168.100.23 00-13-C6-00-02-0F
```
Be sure to change the IP and the hardware address as needed.
