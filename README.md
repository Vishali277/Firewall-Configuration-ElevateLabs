# Task 4: Firewall Configuration
# 🛡️ Windows Firewall Configuration 🛡️
A hands-on exercise in configuring and testing host-based firewall rules on a Windows 11 machine using the built-in Windows Defender Firewall.

## 🚀 Project Overview
The objective of this task was to gain practical experience with a fundamental cybersecurity tool: the host-based firewall. The project involved navigating the Windows Firewall interface to create, test, and remove a rule that filters network traffic. This exercise demonstrates the core principles of network security at the endpoint level, showing how to explicitly block unwanted traffic to reduce a system's attack surface.

## ✨ Key Actions Performed
* **Rule Auditing:** Inspected the existing list of inbound rules to understand the default configuration.
* **Rule Creation:** Built a new inbound rule to explicitly **block** all TCP traffic on port 23 (Telnet).
* **Live Testing:** Used the `Test-NetConnection` cmdlet in PowerShell to scientifically verify that the new firewall rule was active and effectively blocking the connection.
* **Configuration Cleanup:** Properly removed the temporary rule to restore the system to its original state, a key practice in system administration.

## 📊 Demonstration Results
The firewall was successfully configured to block traffic on port 23. The "before" and "after" screenshots show the rule being added to the top of the inbound list. The PowerShell test provided definitive proof of success, returning `TcpTestSucceeded : False`, which confirms that the connection was blocked as intended. The screenshots detailing these steps are included in this repository.

## 💡 Key Concepts & Learnings
* **Principle of Least Privilege:** By creating a "Block" rule, I applied the security principle of only allowing necessary traffic and denying everything else by default.
* **Host-Based Firewalls:** I learned that a host-based firewall is a critical last line of defense, protecting a single machine from malicious traffic even if the network's main firewall is compromised.
* **Stateful Inspection:** Windows Firewall is a stateful firewall, meaning it tracks the state of network connections and makes decisions based on the context of the traffic, which is far more secure than simple packet filtering.
* **Practical Network Testing:** I learned that you must always test your security configurations. Using a tool like PowerShell's `Test-NetConnection` provides concrete proof that a rule is working as expected.

## 📁 Files in This Repository
* **`README.md`**: This detailed project report.
* **`documentation.md`**: A step-by-step log of the commands and GUI actions performed.
* **`1_initial_rules.jpg`**: A screenshot showing the inbound firewall rules before any changes were made.
* **`2_rule_added.jpg`**: A screenshot showing the new "Block Telnet Test" rule in the list.
* **`3_test_result.jpg`**: A screenshot of the PowerShell output confirming the block was successful.
