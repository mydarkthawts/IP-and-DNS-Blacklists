-=| ProtonVPN has closed off the original method of loading their server list and downloading the json file, instead we will use their cached json file of the server list that the app downloads to the linux home folder in the .cache hidden folder |=-

The steps I used to obtain these were obtaining the json file from /home/USERNAME/.cache/Proton/VPN/serverlist.json

Then parsed the json file with grep and sorted to remove duplicates like so:
```
grep -oP '"Domain"\s*:\s*"\K[^"]+' serverlist.json | sort -u > domains.txt
```
```
grep -oP '"EntryIP"\s*:\s*"\K[^"]+' serverlist.json | sort -u > entry_ips.txt
```
```
grep -oP '"ExitIP"\s*:\s*"\K[^"]+' serverlist.json | sort -u > exit_ips.txt
```
