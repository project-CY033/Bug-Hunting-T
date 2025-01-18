# Day- 10 

## 1. Tools [GO](#tools)
## 2. Check CNAM Recored [GO](#check-record)
## 3.           [GO]()

## How to Find Subdomains [GO](#find-subdomain)


---
---
# Tools
<details>
  <summary >Click to Ready about Day 10 Tools Section</summary>

---
---
# Tool - 1  `Can I take over XYZ?`

- ###  "Can I take over XYZ?" — a list of services and how to claim (sub)domains with dangling DNS records.
- ### Go this repository  [Can I take over XYZ?](https://github.com/EdOverflow/can-i-take-over-xyz)







</details>


---


# 2. Check CNAM Recored 
### Check Record 

<details >
   <summary>Click to see the staps</summary>

---
---

## Staps 
- Open terminal in linux
- We have to used `dig` command
- in terminla
```
dig <sub domain or any domain which you awant to chaenc the CNAM record >
```
- Example
```
dig  accounts.tesla.com
```

### for particular means only see `CNAM`
```
dig accounts.tesla.com CNAM
```


# OR Use `nslookup`
```
nslookup <sub domain or any domain which you awant to chaenc the CNAM record >
```
- Examplte
```
nslookup accounts.tesla.com
```

-  use `CNAM` 
```
nslookup accounts.tesla.com CNAM
```
- want to see full details
```
nslookup accounts.tesla.com ANY
```


 
  
</details>

---



# 3.  
<details >
   <summary>Click to see the staps</summary>

---
---



 
  
</details>

---



#  4. 
<details >
   <summary>Click to see the staps</summary>

---
---



 
  
</details>



---





 
































# Find Subdomain
<details>
  <summary>Click to see the staps or Process</summary>

---
---

To find subdomains of a target domain, you can use various methods and tools. Here are some effective techniques:

### 1. **DNS Enumeration**:
- Use online tools like **SecurityTrails**, **DNSdumpster**, or **Spyse** which can help you discover subdomains for a specific domain.

### 2. **Brute Forcing**:
- Tools like **Sublist3r**, **Amass**, or **Gobuster** can brute-force subdomains by using a wordlist.
- Example command for Gobuster:
```bash
gobuster dns -u example.com -w /path/to/wordlist.txt
```

### 3.  use of  Sublister

```bash
python sublist3r.py -d example.com
```






### 4. Use of Subfinder

```bash
subfinder -h
```

```bash
go get -u github.com/projectdiscovery/subfinder/v2/cmd/subfinder
```

```bash
subfinder -d example.com
```

1. **Specify Multiple Domains**:
```bash
subfinder -d domain1.com -d domain2.com
```

2. **Save Results to a File**:
```bash
subfinder -d example.com -o subdomains.txt
```

3. **Use with Other Tools**: You can pipe the output from Subfinder into other tools for further testing or enumeration.











# To prepare a final list of active live subdomains, you can follow these steps using various tools and commands:

### 1. **Subdomain Enumeration**

Use tools like **Sublist3r** or **Amass** to enumerate subdomains from various search engines and sources.

#### **Using Sublist3r:**
```bash
git clone https://github.com/aboul3la/Sublist3r.git
cd Sublist3r
pip install -r requirements.txt
python sublist3r.py -d example.com -o subdomains.txt
```

- **Sublist3r**:  
 ```
 sublist3r -d example.com -o sublist3r_output.txt
 ```




#### **Using Amass:**
```bash
amass enum -d example.com -o subdomains.txt
```


  - **Amass**:  
       ```
       amass enum -passive -d example.com -o amass_output.txt
       ```

- **Assetfinder**:  
       ```
       assetfinder --subs-only example.com > assetfinder_output.txt
       ```

### 2. **Brute Force Subdomains**
 


3. **Combine and Deduplicate Subdomains**  
   Merge results from all tools and remove duplicates.

   - **Command**:  
     ```
     cat sublist3r_output.txt amass_output.txt assetfinder_output.txt | sort | uniq > combined_subdomains.txt
     ```

4. **Resolve Subdomains (DNS Verification)**  
   Use tools to verify if the subdomains resolve to an IP address.

   - **Tools and Commands**:
     - **Dnsx**:  
       ```
       dnsx -l combined_subdomains.txt -o resolved_subdomains.txt
       ```
     - **MassDNS**:  
       ```
       ./massdns -r resolvers.txt -t A -o S -w massdns_output.txt combined_subdomains.txt
       ```

5. **Check for Active and Live Subdomains**  
   Identify live subdomains by sending HTTP/HTTPS requests to them.

   - **Tools and Commands**:
     - **httpx**:  
       ```
       httpx -l resolved_subdomains.txt -o live_subdomains.txt -silent
       ```
     - **Curl (manual check)**:  
       ```
       curl -I https://subdomain.example.com
       ```

6. **Filter Results**  
   - Remove subdomains that return non-200 HTTP status codes or are otherwise inactive.
   - Use tools like `grep` to filter results:
     ```
     grep '200 OK' live_subdomains.txt > active_subdomains.txt
     ```


#         OR
#### **Using a simple HTTP check with curl:**
```bash
cat subdomains.txt | while read sub; do
    if curl -s --head "$sub" | grep "200 OK" > /dev/null; then
        echo "$sub is active"
    fi
done > active_subdomains.txt
```



     

7. **Export Final List**  
   Save the validated list of live subdomains in your desired format, such as TXT, CSV, or JSON.

---

### Sample List of Tools and Commands for Each Step

| **Tool**         | **Purpose**                              | **Command Example**                                      |
|-------------------|------------------------------------------|----------------------------------------------------------|
| Sublist3r         | Subdomain enumeration                   | `sublist3r -d example.com -o sublist3r_output.txt`      |
| Amass             | Passive/active enumeration              | `amass enum -passive -d example.com -o amass_output.txt` |
| Assetfinder       | Lightweight subdomain discovery         | `assetfinder --subs-only example.com > output.txt`      |
| dnsx              | Resolve subdomains to IPs              | `dnsx -l combined_subdomains.txt -o resolved.txt`       |
| MassDNS           | Bulk DNS resolution                    | `./massdns -r resolvers.txt -t A -o S -w output.txt`    |
| httpx             | Check active/live subdomains           | `httpx -l resolved_subdomains.txt -o live.txt -silent`  |
| Curl              | Manual HTTP response validation         | `curl -I https://subdomain.example.com`                |
| grep              | Filtering based on HTTP status          | `grep '200 OK' live_subdomains.txt > active.txt`        |

---

### Final Output Structure

- **Raw Discovery**: `combined_subdomains.txt`
- **Resolved Subdomains**: `resolved_subdomains.txt`
- **Live and Active Subdomains**: `live_subdomains.txt`  

 





















 







</details>
















