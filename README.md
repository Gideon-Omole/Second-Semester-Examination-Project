
# Cloud Engineering Exam Project

### Name : Gideon Omole
### Student ID: ALT/SOE/024/5235

## 1. Server Provisioning (Modern Approach)

**Cloud Provider:** Microsoft Azure  
**Virtual Machine Configuration:**
- **Subscription:** ME-MngEnvMCAP245340-v-giomole-1  
- **Resource Group:** Alt  
- **VM Name:** Gideon  
- **Region:** UK South (Europe)  
- **Availability:** No infrastructure redundancy  
- **Security Type:** Standard  
- **Image:** Ubuntu Pro 24.04 LTS (x64 Gen2)  
- **Size:** Standard_D2s_v3 (2 vCPUs, 8 GiB RAM)  
- **Public IP:** `4.221.123.186`  

**Key Steps:**  
- Created SSH key pair: `Exam Key`  
![SSH Key](./images/Exam%20Key.png)

- Enabled inbound rules for HTTP (Port 80) and HTTPS (Port 443).  

![http/https](./images/Alllow%20port%2080.png) 

![VM Successfully Created](./images/vm%20created.png)  


---

## 2. Web Server Setup (Next-Level Choices)

**SSH Client:** Termius  
**Connected via:** Saved private key for authentication.  

![SSH Connection](./images/SSH%20connection.png)  
  

### Nginx Installation:
1. Updated package manager:  
   ```bash
   sudo apt update
   ```
   ![APT Update](./images/sudo%20apt%20update.png)  

2. Installed Nginx:  
   ```bash
   sudo apt install nginx
   ```
   ![Nginx Installed](./images/Install%20Nginx.png)  

---

## 3. Dynamic Landing Page

**Content:**  
- **Name/Role:** Gideon Omole, Cloud Engineer  
- **Project Title:** *The Future of Cloud Migration*  
- **Features:**  
  - Project pitch highlighting innovation.  
  - Professional bio with skills and past work.  
- **Styling:** CSS  

---

## 4. Networking & Security (Production-Ready)

### Port Configuration:
- Verified inbound rules for Ports 80/443 in Azure NSG.  
  ![Inbound Rules 1](./images/Inbound%20port%20rules%201.png)  
  ![Inbound Rules 2](./images/Inbound%20port%20rules%202.png)  

### File Deployment:
1. Uploaded files via `scp`:  
   ```bash
   scp -i "Exam_key.pem" -r "Altshool_Semester2_Exam" Admin_user@4.221.123.186:~
   ```
   ![SCP Upload](./images/Upload%20files%20to%20server.png)  

2. Moved files to web directory:  
   ```bash
   sudo mv Altshool_Semester2_Exam /var/www/html
   ```
   ![Move Files](./images/home%20dir%20to%20var%20dir.png)  

3. Bought a Custom domain from Namecheap and added A records

   ![Move Files](./images/custom%20domain.png)  

### SSL with Certbot:
1. Installed Certbot:  
   ```bash
   sudo apt install certbot python3-certbot-nginx
   ```
   ![Certbot Install](./images/Install%20certbot.png)  

2. Obtained SSL certificate for my domain:  
   ```bash
   sudo certbot --nginx -d gidimigrate.xyz -d www.gidimigrate.xyz
   ```
   ![SSL Certificate](./images/SSL%20cerificate.png)  

**Access Options:**  
- **Public IP:** [http://4.221.123.186](http://4.221.123.186)  
- **Custom Domain:** [https://gidimigrate.xyz](https://gidimigrate.xyz)  

![Landing Page](./images/Landing%20page.jpeg)  


