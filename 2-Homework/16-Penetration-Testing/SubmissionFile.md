## Week 16 Homework Submission File: Penetration Testing 1

#### Step 1: Google Dorking


- Using Google, can you identify who the Chief Executive Officer of Altoro Mutual is:
    -  **Karl Fitzgerald**
 
- How can this information be helpful to an attacker:
    - **Attacker could do a whale phishing attack**

#### Step 2: DNS and Domain Discovery

Enter the IP address for `demo.testfire.net` into Domain Dossier and answer the following questions based on the results:

  1. Where is the company located: 
     
     **Sunnyvale, CA 94085**
 
  2. What is the NetRange IP address: 
     
     **65.61.137.64 - 65.61.137.127**
  
  3. What is the company they use to store their infrastructure:    
    **CustName:       Rackspace Backbone Engineering**
        **Address:         9725 Datapoint Drive, Suite 100**
        **City:             San Antonio**
        **StateProv:       TX**
        **PostalCode:      78229**

  4. What is the IP address of the DNS server:     
    **65.61.137.117**

#### Step 3: Shodan

- What open ports and running services did Shodan find:
- **https://www.shodan.io/host/65.61.137.117 
 Open Ports: 80/TPC Apache Tomcat/Coyote JSP engine, 443/TCP Apache Tomcat/Coyote JSP engine**

#### Step 4: Recon-ng

- Install the Recon module `xssed`. 
- Set the source to `demo.testfire.net`. 
- Run the module. 

Is Altoro Mutual vulnerable to XSS: 
  **Yes, 1 vulnerability found. Example, input the following script in the Search box will result in a pop up window.**
     **<script>alert("www.sec-r1z.com")</script>**

### Step 5: Zenmap

Your client has asked that you help identify any vulnerabilities with their file-sharing server. Using the Metasploitable machine to act as your client's server, complete the following:

- Command for Zenmap to run a service scan against the Metasploitable machine: 


 **The Metasploitable machine IP address is 192.168.0.10
   type zenmap in kali vm command line
   Input Target 192.168.0.10
   Profile: Quick scan
  I can see the raw nmap Command is nmap -T4 -A 192.168.0.10  Click Scan*
 
- Bonus command to output results into a new text file named `zenmapscan.txt`:
       **On Zenmap screen, click Scan menu, select Save Scan (Ctrl+S), Select File Type: Nmap text format (.nmap). Type file Name as: zenmapscan.txt. Or in command line, run nmap -T4 -A 192.168.0.10 -oN zenmapscan.txt**

- Zenmap vulnerability script command: 
   
   **Click the Profile tab at the top and select Edit Selected Profile.
     Click on the Scripting tab and view all the scripts that start with ftp.
     Select the ftp-vsftpd-backdoor script by placing a check in the box.
     Click Save Changes to save the profile settings.**
     
- Once you have identified this vulnerability, answer the following questions for your client:
  1. What is the vulnerability:
  
    **CVE-2011-2523 vsFTPd 2.3.4 backdoor**
    
  2. Why is it dangerous:


    **Vulnerability can be exploited to run a shelland then gain root privileges**
  
  3. What mitigation strategies can you recommendations for the client to protect their server:


    **Patch,update servers and disable FTP**

---
© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.  

