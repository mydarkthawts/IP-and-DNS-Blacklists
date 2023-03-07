The steps I used to obtain these were obtaining the json file from [api.protonmail.ch/VPN/logicals ](https://api.protonmail.ch/vpn/logicals)

Then parsing the json file like so:
```
grep -oP '(?<="EntryIP":")[^"]*' /LOCATION/TO/JSON/protonVPNlogicals.json > /OUTPUT/FILE/LOCATION/protonVPNEntryIP.txt
```
```
grep -oP '(?<="ExitIP":")[^"]*' /LOCATION/TO/JSON/protonVPNlogicals.json > /OUTPUT/FILE/LOCATION/protonVPNExitIP.txt
```
```
grep -oP '(?<="Domain":")[^"]*' /LOCATION/TO/JSON/protonVPNlogicals.json > /OUTPUT/FILE/LOCATION/protonVPNDomains.txt
```

I know I could've bundled these commands together and knock it all out in one go but I prefer to inspect my work after each stage for accuracy and corruption.
So, I sorted the outputed files using this command to create yet another file that has all the duplications removed. Thus, smaller file size, less firewall parsing.
```
sort -u /OUTPUT/FILE/LOCATION/protonVPNEntryIP.txt > /OUTPUT/FILE/LOCATION/protonVPNEntryIPSortedNoDupes.txt
```
```
sort -u /OUTPUT/FILE/LOCATION/protonVPNExitIP.txt > /OUTPUT/FILE/LOCATION/protonVPNExitIPSortedNoDupes.txt
```
```
sort -u /OUTPUT/FILE/LOCATION/protonVPNDomains.txt > /OUTPUT/FILE/LOCATION/protonVPNDomainsSortedNoDupes.txt
```

That's it.
This will pull the IP addresses and domains into a file as specified by the grep command above and sort them using the second set of commands to ensure there are no duplicates.
