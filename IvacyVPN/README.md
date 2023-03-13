The steps I used to obtain this list was to grab the list of servers from [https://support.ivacy.com/servers-list ](https://support.ivacy.com/servers-list). 

I manually added these to a spreadsheet by copy and pasting the pages table of locations. I have included the .ods spreadsheet I used. After this I copied the lists into a text file and parsed using the command below. 


I sorted the file using this command to create yet another file that has all the duplications removed. Thus, smaller file size, less firewall parsing.

```

sort -u /OUTPUT/FILE/LOCATION/IvacyVPNDomains.txt > /OUTPUT/FILE/LOCATION/IvacyVPNDomainsSortedNoDupes.txt

```

That's it.
