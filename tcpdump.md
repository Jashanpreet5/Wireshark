# 📡 Tcpdump Notes (Beginner → Practical)

## 🔹 Introduction
`tcpdump` is a command-line tool used to capture and analyze network packets in real time.

---

# ⚙️ Basic Syntax
```bash
tcpdump [options]
```

---

# 📌 Important Options

## 🔸 1. Capture on Interface (-i)
```bash
tcpdump -i eth0
```
- Captures packets on a specific interface

---

## 🔸 2. Save Packets to File (-w)
```bash
tcpdump -w data.pcap
```
- Saves captured packets into a `.pcap` file  
- Output will NOT be shown on screen  
- Used for later analysis in Wireshark  

---

## 🔸 3. Read Packets from File (-r)
```bash
tcpdump -r data.pcap
```
- Reads previously saved packets  
- Useful for:
  - Attack analysis  
  - Protocol learning  
  - Offline inspection  

---

## 🔸 4. Limit Number of Packets (-c)
```bash
tcpdump -c 10
```
- Captures only 10 packets  
- Automatically stops after limit  
- Default: runs until Ctrl + C  

---

## 🔸 5. Disable Name Resolution (-n, -nn)

### -n
```bash
tcpdump -n
```
- Prevents DNS resolution  

### -nn
```bash
tcpdump -nn
```
- Prevents:
  - DNS resolution  
  - Port name resolution  

Example:
```
80 → http (normal)
-nn → 80
```

✔ Faster output  
✔ Preferred in cybersecurity  

---

## 🔸 6. Verbose Output (-v, -vv, -vvv)
```bash
tcpdump -v
tcpdump -vv
tcpdump -vvv
```

| Option | Description |
|--------|------------|
| -v     | Basic details |
| -vv    | More details |
| -vvv   | Maximum details |

Shows:
- TTL  
- Packet length  
- Header details  

---

# 📊 Summary Table

| Command | Explanation |
|--------|------------|
| -i     | Select interface |
| -w     | Write packets to file |
| -r     | Read packets from file |
| -c     | Limit packets |
| -n     | No DNS |
| -nn    | No DNS + No port |
| -v     | Verbose |

---

# 💻 Examples

## Example 1
```bash
tcpdump -i eth0 -c 50 -v
```
- Capture 50 packets  
- From eth0  
- With verbose output  

---

## Example 2
```bash
tcpdump -i wlo1 -w data.pcap
```
- Capture from WiFi  
- Save to file  

---

## Example 3
```bash
tcpdump -i any -nn
```
- Capture on all interfaces  
- No resolution  

---

# 🧠 Memory Trick

```
W → Write
R → Read
C → Count
N → No resolve
V → Verbose
```

---

# 🔥 Use Cases
- Network troubleshooting  
- Packet analysis  
- Cybersecurity investigations  
- Forensics  

---

# 🛠 Tools Integration
- Wireshark  
- Tshark  

---

# 📌 Pro Tip
```bash
tcpdump -nn
```
✔ Fast  
✔ Clean  
✔ Exam-friendly  
