# Firewall Configuration and Testing - Day 3

## Step 1: Open firewall configuration tool
- Press **Win + R** → type `wf.msc` → Enter.  
- This opens **Windows Defender Firewall with Advanced Security**.

---

## Step 2: List current firewall rules
- In the left panel → click **Inbound Rules**.  
- You will see existing rules for Windows services and apps.  

(Command alternative:)  
```powershell
netsh advfirewall firewall show rule name=all
```

---

## Step 3: Add a rule to block inbound traffic on a specific port (Port 23 - Telnet)
1. Right-click **Inbound Rules** → **New Rule…**  
2. Select **Port** → Next  
3. Choose **TCP** and enter **23** → Next  
4. Select **Block the connection** → Next  
5. Apply to **Domain, Private, Public** → Next  
6. Name it: `Block Telnet (Port 23)` → Finish  

---

## Step 4: Test the rule
Using Telnet (if installed):  
```powershell
telnet localhost 23
```
Connection should fail.  

Or with Nmap:  
```bash
nmap -p 23 localhost
```
It should show port **23 as filtered/closed**.

---

## Step 5: Add rule to allow SSH (Port 22) [Linux-only step]
If SSH is enabled:  
- Create a new inbound rule → Port → TCP 22 → **Allow the connection**.  
- Name it `Allow SSH`.  

---

## Step 6: Remove the test block rule
- Go to **Inbound Rules**.  
- Find `Block Telnet (Port 23)` → Right-click → **Delete** or **Disable**.  

---

## Step 7: Document commands or GUI steps used
- Screenshots of:  
  - Inbound Rules list  
  - Telnet block rule created  
  - Test results from Telnet/Nmap  

---

## Step 8: Summary
A firewall monitors **inbound and outbound traffic**. Rules decide whether traffic is allowed or blocked.  
- Filters traffic by **port, protocol, IP address, or application**.  
- Blocking unused ports reduces attack surface.  
- Allowing only trusted connections increases security.  

