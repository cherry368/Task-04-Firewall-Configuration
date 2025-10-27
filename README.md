# 🔒 Task-04: Firewall Configuration and Traffic Filtering

## 🎯 Objective
To understand how a firewall filters network traffic and manage firewall rules to allow or block specific ports.

## 🧰 Tools Used
- **Windows Firewall** (for Windows users)
- **UFW (Uncomplicated Firewall)** (for Linux users)

---

## 🪟 Windows Firewall Configuration

### 1️⃣ Open Firewall Configuration Tool
Press **Windows + R** → Type `wf.msc` → Hit **Enter**

📸 **Screenshot Example:**
```
/screenshots/windows_open_firewall.png
```

### 2️⃣ List Current Firewall Rules
Go to **Inbound Rules** or **Outbound Rules** in the left panel.

📸 **Screenshot Example:**
```
/screenshots/windows_list_rules.png
```

### 3️⃣ Block Inbound Traffic on Port 23 (Telnet)
1. Click **Inbound Rules** → **New Rule** → **Port** → **TCP** → **Specific local ports: 23**
2. Choose **Block the connection** → Apply to all profiles → Name as **"Block Telnet Port 23"**

📸 **Screenshot Example:**
```
/screenshots/windows_block_telnet.png
```

### 4️⃣ Test the Rule
Open **Command Prompt** and run:
```cmd
telnet localhost 23
```

**Expected Output:** Connection failed or refused

📸 **Screenshot Example:**
```
/screenshots/windows_test_block.png
```

### 5️⃣ Remove the Test Block Rule
Go back to **Inbound Rules** → Find **"Block Telnet Port 23"** → Right-click → **Delete**

📸 **Screenshot Example:**
```
/screenshots/windows_remove_rule.png
```

---

## 🧾 Command Summary Table

| Action | Windows Command/Steps |
|--------|----------------------|
| **View Rules** | GUI → Inbound Rules |
| **Block Port 23** | New inbound rule (TCP 23) |
| **Test Rule** | `telnet localhost 23` |
| **Remove Rule** | Delete via GUI |

---

## 🔍 Summary — How Firewall Filters Traffic

- A **firewall** acts as a protective barrier between trusted and untrusted networks.
- It filters packets based on rules defining whether to **allow** or **deny** traffic.
- **Inbound Rules:** Control incoming connections.
- **Outbound Rules:** Control outgoing connections.
- **Allow Rules:** Permit specific services (e.g., SSH).
- **Deny Rules:** Block insecure services (e.g., Telnet).

---

## 🧩 Example Output (Linux)

```
Status: active

To                         Action      From
--                         ------      ----
22/tcp                     ALLOW       Anywhere
23/tcp                     DENY        Anywhere
```


## ✅ Outcome

You have successfully:
- ✅ Configured and managed firewall rules
- ✅ Tested port blocking and unblocking
- ✅ Allowed SSH access
- ✅ Restored system to its original state
- ✅ Understood traffic filtering and network protection

---

## 📁 Repository Structure

```
Task-04-Firewall-Configuration/
│
├── README.md
├── screenshots/
│   ├── windows_open_firewall.png
│   ├── windows_block_telnet.png
│   ├── linux_block_telnet.png
│   └── linux_final_output.png
└── report.docx   # Optional report
```
