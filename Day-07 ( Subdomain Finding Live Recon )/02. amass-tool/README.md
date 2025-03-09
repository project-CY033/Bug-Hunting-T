


# Use amass
- run
```
sudo apt install amass 
```

- commd
```
amass -h
```

- at last see `An example configuration file can be found here` 
- copy  this and open in browser to add API 

```                                                                                                                                                
https://github.com/owasp-amass/amass/blob/master/examples/config.yaml                                                                                                                            
```
- download this two  file `config.yaml` and `datasources.yaml` and add in `amass` folder
                                   
## to add  fllow the process
- open Home or file explorer 
- click view and select hidden file option 
- open `.config` folder 
- in `.config` folder ,  `amass`  folder is present.
-  in `amass` folder add `config.yaml` and `datasources.yaml` .
-  you can download both file form [amass](https://github.com/owasp-amass/amass/blob/master/examples/config.yaml )

- Now add API key in `datasources.yaml` file.


# Run the tool

- command
```
amass enum -h 
```

- now
```
amass enum -passive -d bitso.com -o <file path or save result file > -v
```
- eg
```
amass enum -passive -d bitso.com -o /home/kali/targret/bitso.txt -v
```























                                                    
