## **Challenge Name:** I'm Just a Shark

### **Category:** Forensics

---

### **Difficulty:** Medium

---

### **Challenge Description:**

> *Find the flag within this mess... but beware, it might not appear as you expect. Perhaps the key lies in a ~47 twist.*

The challenge involved analyzing a packet capture file using Wireshark. The flag was hidden within the packets and encrypted. The task was to decode the flag and retrieve it.

---

## **Solution**

### **Step 1: Exploring the Packets**

* Opened the file in **Wireshark** and browsed through the packets.
* Initially inspected various protocols like **DNS** and **HTTP** (application layer protocols) as flags are often hidden there. Checked queries and requests but found nothing unusual.
* Switched focus to the first packet because it stood out. It contained an **[ACK]** without any response (sus).

---

### **Step 2: Investigating the First Packet**

* Looked closer at the  **first packet** , which was  **28 bytes long** , matching the length of the flag (a key clue).
* Extracted its **hexadecimal format** and attempted to decode it with ROT47, but it didn’t work.

---

### **Step 3: Decoding the Flag**

* Decoded the **ASCII format** of the packet data instead, using an online ROT47 decoder.
* The ASCII format worked, revealing the flag:

`SecAI{H&T_is_getting_cl0ser}`

---

### **Key Observations:**

* Avoid opening all packets; instead, focus on understanding protocols and identifying anomalies.
* The **hint** provided crucial information about the encryption method (ROT47).
* The **first packet’s size and lack of response** were strong indicators it contained the flag.

---

### **Tools & Techniques Used**

* **Wireshark** : To analyze packets.
* **ROT47 Decoder** : Online tool for decoding the encrypted flag.

---


### **Lessons Learned**

* Focus on **suspicious packets** rather than checking all packets. Look for anomalies, patterns, and clues within protocols.
* Always read the challenge hint carefully—it often points directly to the solution (e.g., "47 twist" = ROT47).
* Cross-check the data formats (hexadecimal vs. ASCII) when decoding encrypted content.

---
