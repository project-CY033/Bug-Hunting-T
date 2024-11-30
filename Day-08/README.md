#  Day 7 revision

## Subdomain 
## subdomain of subdomain 
```
<target e.g bitso.com>
bitso.com
     help.bitso.com
           contact.bitso.com
                 sport.bitso.com

```

# tools

- 1. amass
- 2. sublister 
- 3. ffuf
- 4. httpx



# Day 8

## 1.first find subdomain 
## 2. use tool `sublister`

## 3. Sublister 
```
subfinder -d bitso.com -all -silent -o bitso.txt

```

## 4. Use `ffuf`
```
ffuf -u "http://FUZZ.bitso.com" -w  /home/kali/Desktop/n0kovo_subdomains_medium.txt -mc 200 --rate 100 -v
```






## Second tool
##  Oneforall  download form GitHub 
```
https://github.com/shmilylty/OneForAll.git
```


































