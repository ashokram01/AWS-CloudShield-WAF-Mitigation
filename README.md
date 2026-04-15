# CloudShield: AWS WAF SQLi Mitigation & Infrastructure Hardening

## 📌 Project Overview
This project demonstrates the identification and mitigation of **SQL Injection (SQLi)** vulnerabilities within a serverless AWS infrastructure. By deploying **AWS WAF (Web Application Firewall)**, I successfully secured an API Gateway and backend Lambda functions, preventing unauthorized data extraction and hardening the cloud environment against OWASP Top 10 threats.

---

## 🏗️ 1. Infrastructure Architecture
Visualizing the security layers and request flow within the AWS Cloud.

![Network Topology](network_topology.png)
**Technical Detail:** This topology illustrates the "Defense-in-Depth" strategy. The AWS WAF is positioned at the edge to inspect all incoming traffic before it reaches the API Gateway and processing layers.

---

## 🔓 2. Vulnerability Assessment (Pre-Mitigation)
Demonstrating the security gap in an unprotected API.

![Vulnerability Proof](vulnerability_proof.png)
**Technical Detail:** Without security rules, the system was susceptible to a basic SQLi payload (`' OR '1'='1`). The screenshot proves that sensitive database information (`User_ID_101, Balance: $5000`) was leaked in the API response.

---

## ⚙️ 3. Security Implementation (WAF Configuration)
Enforcing strict traffic filtering and rule customization.

![WAF Config Rules](waf_config_rules.png)
**Technical Detail:** I implemented the **AWSManagedRulesSQLiRuleSet** and configured the action to **"Block"**. I ensured granular inspection across Query Arguments, Body, and Cookies to prevent bypass attempts.

---

## ✅ 4. Attack Mitigation Validation (The Result)
Verifying that the security implementation successfully blocks the threat.

![Attack Blocked](Attack%20Blocked%20(Success).png)
**Technical Detail:** Re-testing the same SQLi attack vector now results in an **HTTP 403 Forbidden** status. This confirms that the WAF is successfully intercepting and terminating malicious requests.

---

## 📊 5. Real-Time Observability & Monitoring
Analyzing attack telemetry through CloudWatch metrics.

![Traffic Monitoring](traffic_monitoring_graph.png)
**Technical Detail:** The monitoring dashboard displays real-time spikes in blocked traffic. The logs specifically tag the **SQLiRuleSet** as the terminating rule, providing full visibility into the attack attempt.

---

## 🛠️ Tech Stack & Methodology
* **Cloud Platform:** Amazon Web Services (WAF, API Gateway, Lambda, CloudWatch)
* **Security Testing:** Kali Linux (Penetration Testing), cURL
* **Security Standards:** OWASP Top 10 Mitigation
* **Logic:** Serverless Security Architecture

---

### 🚀 How to Set Up this Repository:
1. **Upload Images:** Upload all 5 screenshots (`network_topology.png`, `vulnerability_proof.png`, `waf_config_rules.png`, `Attack Blocked (Success).png`, `traffic_monitoring_graph.png`) to the main folder of your repository.
2. **Create File:** Click on **Add file** -> **Create new file**.
3. **Name it:** Name the file exactly `README.md`.
4. **Paste & Save:** Paste the code above and click **Commit changes**.
