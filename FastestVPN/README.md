The steps I used to obtain this list was to grab the list of servers from [https://support.fastestvpn.com/vpn-servers ](https://support.fastestvpn.com/vpn-servers/). 

I manually added these to a spreadsheet by copy and pasting the pages table of locations. I have included the .ods spreadsheet I used. After this I copied the lists into a text file and parsed using the command below. 

I sorted the file using this command to create yet another file that has all the duplications removed. Thus, smaller file size, less firewall parsing.

```

sort -u /OUTPUT/FILE/LOCATION/FastestVPNDomains.txt > /OUTPUT/FILE/LOCATION/FastestVPNDomainsSortedNoDupes.txt

```

That's it.
