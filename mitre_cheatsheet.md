MITRE ATT&CK (Adversarial Tactics, Techniques, and Common Knowledge) is a framework that provides a comprehensive and up-to-date knowledge base of known adversary tactics and techniques used in cyberattacks. Below is a simplified cheatsheet of some of the key elements and concepts associated with MITRE ATT&CK.

**MITRE ATT&CK Cheatsheet:**

1. **Tactics:** Categories of adversary objectives and goals.
   - **Initial Access:** Gaining initial entry into a system.
   - **Execution:** Techniques for running malicious code.
   - **Persistence:** Maintaining access to a compromised system.
   - **Privilege Escalation:** Increasing access privileges on a system.
   - **Defense Evasion:** Techniques to avoid detection.
   - **Credential Access:** Stealing or obtaining credentials.
   - **Discovery:** Gathering information about the target environment.
   - **Lateral Movement:** Moving laterally within a network.
   - **Collection:** Gathering data of interest to the attacker.
   - **Exfiltration:** Unauthorized transfer of data outside the network.
   - **Impact:** Techniques causing harm or damage to the target.

2. **Techniques:** Specific methods used by adversaries within each tactic.
   - Examples: Phishing, Command-Line Interface, PowerShell, Remote Desktop Protocol (RDP) Exploitation, Kerberoasting, Data Exfiltration, etc.

3. **Sub-Techniques:** Further refinements of techniques, providing more granularity.
   - Example: T1560.001 - Archive Collected Data (Sub-Technique of Data Exfiltration).

4. **Mitigations:** Countermeasures and best practices to defend against techniques.
   - Example: M1036 - Limit Access to Resource Over Network.

5. **Detection:** Guidance on detecting and identifying adversary activity.
   - Example: Detections for specific techniques or behaviors.

6. **Groups:** Threat actor groups and their associated tactics and techniques.
   - Examples: APT29 (Cozy Bear), APT32 (OceanBuffalo), etc.

7. **Software:** Malware, tools, and utilities used by adversaries.
   - Examples: Cobalt Strike, Mimikatz, PowerShell Empire, etc.

8. **Data Sources:** Sources of information that can be used for detection and analysis.
   - Examples: Windows event logs, network traffic data, process monitoring, etc.

9. **References:** External resources and references related to each technique or tactic.

10. **Platforms:** The operating systems and environments where a technique is applicable.
    - Examples: Windows, Linux, macOS, Cloud, etc.

11. **Contributors:** Organizations and individuals that contribute to MITRE ATT&CK.

12. **Notes:** Additional information and context for understanding the framework.

