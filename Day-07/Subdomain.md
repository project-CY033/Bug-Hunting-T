# Subdomain enumeration

#  download `golang` 
- command
```
apt install golang
```


## clone subfinder
[subfinder](https://github.com/projectdiscovery/subfinder.git)

- for finding more valid subdomain configer api 
- run to se the provider
```
subfinder -ls 
```

- to add API fllow the process
- open Home or file explorer 
- click view and select hidden file option 
- open `.config` folder 
- in `.config` folder `subfinder`  folder is present.
-  in `subfinder` folder `provider-config.yaml` file is present in this configer all API.

- then in terminal 

```
sudo apt install subfinder

 ```

- command 

```
subfinder -d <Target domain> -o <file name > -v
```

- eg
```
subfinder -d nba.com -o /home/kali/targret/nbasub.txt -v
```


 
- command 
 


## Clone Sublist3r
 
- [Sublist3r](https://github.com/aboul3la/Sublist3r.git)
 

## Run the tool 
- use 
```
python3 sublist3r.py -d <domain or target> -o <fiel name or path>   
```

- eg
```
python3 sublist3r.py -d nba.com -o /home/kali/targret/nba.txt   
```

## clone ffuf 
[ffuf](https://github.com/ffuf/ffuf.git)




