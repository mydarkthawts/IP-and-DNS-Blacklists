-=| ProtonVPN has closed off the original method of loading their server list and downloading the json file, instead we will use their cached json file of the server list that the app downloads to the linux home folder in .cache |=-

The steps I used to obtain these were obtaining the json file from /home/USERNAME/.cache/Proton/VPN/serverlist.json

Then parsed the json file like so:
```
grep -oP '(?<="EntryIP":")[^"]*' serverlist.json > protonVPNEntryIP.txt
```
```
grep -oP '(?<="ExitIP":")[^"]*' serverlist.json > protonVPNExitIP.txt
```
```
grep -oP '(?<="Domain":")[^"]*' serverlist.json > protonVPNDomains.txt
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
