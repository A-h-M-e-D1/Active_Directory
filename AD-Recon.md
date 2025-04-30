# Active Directory - Initial Enumeration & Information Gathering

## 1. IP Addresses and Domain Names

###  Purpose
- Detect IP ranges used in the environment
- Discover the domain name (e.g. corp.local)
- Enumerate internal hostnames

###  Tools & Examples
- **netdiscover**:
  ```bash
  netdiscover -r <target-ip>/24
  ```
- **arp-scan**:
  ```bash
  arp-scan --interface=eth0 <target-ip>/24
  ```
- **nmap (Ping scan)**:
  ```bash
  nmap -sn <target-ip>/24
  ```
- **nslookup**:
  ```bash
  nslookup example.com
  ```
- **dig**:
  ```bash
  dig example.com
  ```
- **nbtstat**:
  ```bash
  nbtstat -A <target-ip>
  ```

---

## 2. Subnet Information

###  Purpose
- Understand if DC is in the same subnet
- Identify VLANs or network segmentation
- Find potential pivot points

### 🛠️ Tools & Examples
- **arp-scan**:
  ```bash
  arp-scan --interface=eth0 <target-ip>/24
  ```
- **ip a**:
  ```bash
  ip a
  ```
- **ip route**:
  ```bash
  ip route
  ```

---

## 3. Network Topology

###  Purpose
- Discover network layout, routers, firewalls
- Detect if AD is on the same network

### 🛠️ Tools & Examples
- **traceroute**:
  ```bash
  traceroute <target-ip>
  ```
- **Wireshark**:
  - Start capture and look for LLMNR, NBNS or NetBIOS traffic.

---

## 4. Domain Controller Details

###  Purpose
- Locate the DC
- Detect services and OS version
- Identify attack surfaces (SMB, LDAP, Kerberos)

###  Tools & Examples
- **nslookup SRV records**:
  ```bash
  nslookup -type=SRV _ldap._tcp.dc._msdcs.example.com
  ```
- **ldapsearch**:
  ```bash
  ldapsearch -x -H ldap://domain-controller-ip -D "user@example.com" -w "password" -b "DC=example,DC=com" "objectclass=*"
  ```
- **nmap**:
  ```bash
  nmap -sC -sV -p <>  <target-ip>
  ```
- **BloodHound**:
  - Use SharpHound ingestor after access.

---

## 5. Enumeration

###  Purpose
- Enumerate usernames and privileges
- Discover trust relationships
- Find exploitable service accounts

###  Tools & Examples
- **enum4linux**:
  ```bash
  enum4linux -a <target-ip>
  ```
- **nbtscan**:
  ```bash
  nbtscan <target-ip>/24
  ```
- **smbclient**:
  ```bash
  smbclient -L //<target-ip> -U ""
  ```
- **smbmap**:
  ```bash
  smbmap -H <target-ip>
  ```
- **kerbrute** (user enumeration):
  ```bash
  kerbrute userenum --dc <domain-controller-ip> -d example.com users.txt
  ```
- **GetUserSPNs.py** (Kerberoasting):
  ```bash
  GetUserSPNs.py example.com/user:password -dc-ip <domain-controller-ip>
  ```
- **nltest**:
  ```bash
  nltest /domain_trusts
  ```
- **netdom**:
  ```bash
  netdom query /domain
  ```



