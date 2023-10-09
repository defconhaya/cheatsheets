The Common Vulnerability Scoring System (CVSS) is a framework for assessing and rating the severity of security vulnerabilities. It provides a standardized way to communicate the characteristics and impact of a vulnerability. The CVSS scoring system assigns a score to vulnerabilities on a scale from 0 to 10, with 10 being the most severe. Below is a cheat sheet for understanding CVSS:

**CVSS Version 3.1 Metrics:**

1. **Base Score Metrics:**
   - **Attack Vector (AV):** How the vulnerability is exploited.
     - `N` (Network) - Remotely exploitable.
     - `A` (Adjacent) - Requires local access.
     - `L` (Local) - Requires physical access.
     - `P` (Physical) - Requires physical interaction.

   - **Attack Complexity (AC):** How complex the attack is.
     - `H` (High) - Specialized conditions or advanced techniques needed.
     - `L` (Low) - Easy to exploit.

   - **Privileges Required (PR):** Level of privileges an attacker needs.
     - `N` (None) - No privileges required.
     - `L` (Low) - Low-level privileges.
     - `H` (High) - High-level privileges.

   - **User Interaction (UI):** Whether user interaction is required.
     - `N` (None) - No user interaction.
     - `R` (Required) - User interaction required.

   - **Scope (S):** Whether the vulnerability impacts the system's confidentiality, integrity, or availability.
     - `U` (Unchanged) - Does not change privileges or resources.
     - `C` (Changed) - Changes privileges or resources.

   - **Confidentiality (C), Integrity (I), Availability (A) Impact (I):**
     - `N` (None) - No impact.
     - `L` (Low) - Limited impact.
     - `H` (High) - High impact.

2. **Temporal Score Metrics:**
   - **Exploit Code Maturity (E):** The likelihood of the vulnerability being actively exploited.
     - `X` (Not defined) - Unknown.
     - `H` (High) - Proven exploits available.
     - `F` (Functional) - Functional exploits exist.
     - `P` (Proof-of-Concept) - Proof-of-concept code available.

   - **Remediation Level (RL):** The level of available fixes or mitigations.
     - `U` (Unavailable) - No known fix.
     - `W` (Workaround) - Temporary fix or workaround.
     - `T` (Temporary) - Official fix planned but not yet available.
     - `O` (Official) - Official fix available.

   - **Report Confidence (RC):** The confidence level in the assessment.
     - `X` (Not defined) - Unknown.
     - `U` (Unknown) - Uncorroborated.
     - `R` (Reasonable) - Some confidence.
     - `C` (Confirmed) - High confidence.

3. **Environmental Score Metrics:**
   - **Confidentiality (CR), Integrity (IR), Availability (AR) Impact (I):**
     - `X` (Not defined) - Unknown.
     - `L` (Low) - Limited impact.
     - `M` (Medium) - Moderate impact.
     - `H` (High) - High impact.

**CVSS v3.1 Scoring Formula:**

The formula for calculating the CVSS score is as follows:

```
CVSS Score = (Base Score * Impact Factor) + ((1 - Impact Factor) * Exploitability Factor)
```

- **Base Score:** Calculated from the Base Score Metrics.
- **Impact Factor:** Derived from the Environmental Score Metrics.
- **Exploitability Factor:** A constant value set to 8.22 by default for CVSS v3.1.

**Example CVSS Score:**

Let's say you have a vulnerability with the following metrics:
- AV:N/AC:L/PR:L/UI:N/S:U/C:L/I:L/A:L
- E:U/RL:W/RC:R
- CR:M/IR:M/AR:M

You would calculate the CVSS score as follows:
1. Calculate Base Score: 4.8
2. Calculate Impact Factor: 6.8
3. Calculate Exploitability Factor: 8.22

Then, plug these values into the scoring formula to get the final CVSS score.

