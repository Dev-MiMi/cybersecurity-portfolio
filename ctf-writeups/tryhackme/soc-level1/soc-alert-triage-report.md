# Incident Response Report: Authorized Port Scan (Benign Alert)

## 📌 Executive Summary
**Date of Investigation:** April 16, 2026
**Analyst:** Miracle
**Alert Type:** Network Port Scan
**Severity:** Low
**MITRE ATT&CK:** T1046 - Network Service Discovery
**Resolution:** False Positive (Authorized Activity)

During routine monitoring, the SIEM generated an alert regarding rapid, multi-port connection attempts targeting an internal host. Upon analyzing the logs and cross-referencing internal communications, the activity was verified as an authorized network sweep conducted by the internal Vulnerability Assessment Team. No malicious breach occurred, and the alert was closed as a False Positive.

---

## 🔍 Investigation Details (The 5 Ws)

* **What:** Port Scanning Activity. A single source IP attempted to connect to multiple destination ports (including 443, 53, 22, 21, 25, 143, and 80) in rapid succession.
* **When:** The scanning activity spiked and occurred concurrently on June 12, 2024, at 17:24.
* **Where:** The targeted destination host was `10.0.0.3` (Hostname: JOE PC).
* **Who:** The scanning originated from Source IP `10.0.0.8`. The associated hostname was identified as `NESSUS`, a known industry-standard vulnerability scanning tool. 
* **Why:** The activity was intended. It was a scheduled internal audit, not a malicious external threat actor.

---

## 🛠️ Analyst Notes & Artifacts

**Log Analysis Findings:**
* **Pattern Recognition:** The SIEM successfully correlated the rapid connection attempts to various service ports within the same minute, accurately flagging the behavior of a reconnaissance scan.
* **Host Response:** Log analysis confirmed that the target machine (`10.0.0.3`) did send traffic back to the scanner (`10.0.0.8` on port 56927), indicating the host was online and responding to the TCP handshake attempts. 
* **Verification:** A standing note from the Vulnerability Assessment Team confirmed they were operating from host `10.0.0.8` on the network during this timeframe.

## ✅ Conclusion
The alert behaved as expected, successfully identifying reconnaissance-style network traffic. Because the source of the traffic was a verified internal team utilizing a legitimate tool (Nessus), the incident was categorized as intended behavior. The ticket was closed as a **False Positive**, and no further remediation or escalation was required. 

<img width="1080" height="1822" alt="XRecorder_20260416_08" src="https://github.com/user-attachments/assets/3ba70213-d24c-43ed-9f0d-35c28ca360af" />
