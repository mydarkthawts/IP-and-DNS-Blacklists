The steps I used to obtain these were obtaining the json file from [api.protonmail.ch/VPN/logicals ](https://api.protonmail.ch/vpn/logicals)

Then parsed the json file like so:
```
grep -oP '(?<="EntryIP":")[^"]*' logicals.json > protonVPNEntryIP.txt
```
```
grep -oP '(?<="ExitIP":")[^"]*' logicals.json > protonVPNExitIP.txt
```
```
grep -oP '(?<="Domain":")[^"]*' logicals.json > protonVPNDomains.txt
```

I know I could've bundled these commands together and knock it all out in one go but I prefer to inspect my work after each stage for accuracy.

I sorted the files using this command to create yet another file that has all the duplicate results removed. 
```
sort -u protonVPNEntryIP.txt > protonVPNEntryIPSortedNoDupes.txt
```
```
sort -u protonVPNExitIP.txt > protonVPNExitIPSortedNoDupes.txt
```
```
sort -u protonVPNDomains.txt > protonVPNDomainsSortedNoDupes.txt
```
