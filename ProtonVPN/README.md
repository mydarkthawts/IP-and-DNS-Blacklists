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

That's it.
This will pull the IP addresses and domains into a file as specified by the grep command above.
