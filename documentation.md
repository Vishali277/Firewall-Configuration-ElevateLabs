# Firewall Configuration Steps

This document outlines the steps taken to configure and test a firewall rule on Windows 11.

1.  Opened the **Windows Defender Firewall with Advanced Security** application.
2.  Navigated to the **Inbound Rules** section to view the existing configuration.
3.  Initiated the **New Rule...** wizard from the Actions panel.
4.  Configured the rule type as **Port**.
5.  Specified the protocol as **TCP** and the port as **23**.
6.  Set the action to **Block the connection**.
7.  Applied the rule to all network profiles (Domain, Private, Public).
8.  Named the rule `Block Telnet Test` and saved it.
9.  Opened **Windows PowerShell** to test the rule's effectiveness.
10. Ran the command `Test-NetConnection -ComputerName localhost -Port 23`.
11. Verified that the result was `TcpTestSucceeded : False`, confirming the port was successfully blocked.
12. Returned to the firewall application, right-clicked the `Block Telnet Test` rule, and selected **Delete** to clean up the configuration.
