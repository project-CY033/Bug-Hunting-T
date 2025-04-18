# **Subdomain Takeover** .
### defronix. com
### help.defronix.com -
### Github, Google Cloud, Amazon Cloud, unbounce, Azure, Netlify (To
### host some services on these 3rd party cloud services.)
### help.defronix.com = Reach to Github Service
### (redirection) + service showcase/ result

* # 🚀 CNAME - canonical name --> Work : map one domian to another without giving any ip address.
 


* # 🚀**What is Cloudflare**

<details>
<summary>Click to Read about Cloudflare</summary>

---

Cloudflare is a web infrastructure and website security company that provides services such as:

1. **Content Delivery Network (CDN):**
   - Speeds up website loading by caching content on servers located worldwide.
   - Ensures faster delivery of content to users based on their geographic location.

2. **DNS Management:**
   - Offers fast and reliable Domain Name System (DNS) services.
   - Helps manage domain records efficiently.

3. **DDoS Protection:**
   - Protects websites from Distributed Denial-of-Service (DDoS) attacks by filtering malicious traffic.

4. **Web Application Firewall (WAF):**
   - Blocks malicious traffic and protects websites from vulnerabilities like SQL injection and cross-site scripting (XSS).

5. **SSL/TLS Encryption:**
   - Provides free SSL certificates to secure websites with HTTPS.

6. **Load Balancing:**
   - Distributes traffic across multiple servers to ensure high availability and reliability.

7. **Bot Management:**
   - Identifies and mitigates harmful bot traffic while allowing good bots.

Cloudflare is widely used by websites to enhance performance, security, and reliability. It acts as a reverse proxy, sitting between the user and the server, to filter traffic and optimize delivery.

---

</details>


   


---


* # Notes on Subdomain Takeover - Steps, Commands, and Tools

#### **1. Introduction to Subdomain Takeover**
- Subdomain Takeover occurs when a subdomain points to a third-party service (e.g., GitHub, AWS) that is no longer in use, but the DNS entry (CNAME record) still exists. 
- A hacker can claim the abandoned service and take control of the subdomain .

---

#### **2. Steps to Identify and Exploit Subdomain Takeover**

1. **Reconnaissance**
   - Enumerate subdomains using tools like `Sublist3r`, `Amass`, or `Subfinder`.
   - Use the `dig` command to check DNS records:
     ```bash
     dig <subdomain> CNAME
     ```
     Look for CNAME entries pointing to third-party services .

2. **Check for Vulnerabilities**
   - Visit the subdomain in a browser or use tools to check for a **404 error page** or similar error messages indicating the service is unclaimed.
   - Example: GitHub's 404 error page might state, *"There isn't a GitHub Pages site here"* .

3. **Claim the Service**
   - If the service is unclaimed, create an account on the respective platform (e.g., AWS S3, GitHub Pages).
   - Use the subdomain name as the identifier (e.g., bucket name for AWS S3).
   - Upload a file (e.g., `index.html`) to confirm the takeover .

---

#### **3. Commands and Tools**

1. **Using `dig` Command**
   - To check DNS records:
     ```bash
     dig <subdomain> CNAME
     ```

2. **Using Tools for Automation**
   - **Subjack**: Scans subdomains for takeover vulnerabilities.
     ```bash
     subjack -w <subdomain_list.txt> -t 100 -ssl -v
     ```
   - **Subzy**: Detects subdomain takeover vulnerabilities.
     - Install:
       ```bash
       go install github.com/lukasikic/subzy@latest
       ```
     - Run:
       ```bash
       subzy run -targets <subdomain_list.txt>
       ```

3. **Manual Verification**
   - Use `dig` to confirm CNAME entries.
   - Visit the subdomain to check for error messages .

4. **Combining Subdomain Lists**
   - Combine multiple subdomain lists into one:
     ```bash
     cat file1.txt file2.txt | anew > final_list.txt
     ```

5. **Exploiting AWS S3 Bucket**
   - Create a bucket with the subdomain name:
     ```bash
     aws s3api create-bucket --bucket <subdomain_name> --region <region>
     ```
   - Upload an `index.html` file:
     ```bash
     aws s3 cp index.html s3://<subdomain_name>
     ```
   - Enable static website hosting .

---

#### **4. Tools Overview**

1. **Subzy**
   - Detects subdomain takeover vulnerabilities using fingerprint matching.
   - Install via Go and run commands to scan subdomains .

2. **Subjack**
   - Scans for subdomain takeover vulnerabilities and checks for unclaimed services .

3. **Nuclei**
   - A powerful tool for automated vulnerability scanning.
   - Install and use templates for subdomain takeover:
     ```bash
     nuclei -t subdomain-takeover-templates -l <subdomain_list.txt>
     ```

4. **Anew**
   - Combines and deduplicates subdomain lists .

---

#### **5. Key Points**
- Always verify results manually to avoid false positives.
- Use tools like `Subzy` and `Subjack` for automation but confirm findings using `dig` and browser checks.
- Ensure ethical use of these techniques and obtain proper permissions before testing .
