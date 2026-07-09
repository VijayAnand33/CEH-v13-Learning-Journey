# Module 06: System Hacking

> **Status:** ✅ Completed
>
> **Difficulty:** ⭐⭐⭐⭐⭐
>
> **Labs Completed:** 6
>
> **Tools Covered:** *(To be updated after completing all labs.)*

---

# Module Summary

This module focuses on System Hacking, one of the most critical phases of the ethical hacking methodology, where information collected during footprinting, scanning, enumeration, and vulnerability analysis is used to compromise target systems. Throughout this module, I learned how ethical hackers gain unauthorized access, escalate privileges, maintain persistent access, perform Active Directory attacks, and remove evidence of compromise while understanding the defensive measures used to detect and mitigate these techniques.

The practical labs covered password attacks, reverse shell access, buffer overflow exploitation, privilege escalation, persistence mechanisms, log clearing, Active Directory attacks, and AI-assisted system hacking using various penetration testing tools and Windows administrative features. Rather than focusing solely on individual tools and commands, this documentation explains the methodology, attack lifecycle, security implications, and defensive perspective associated with each phase of system hacking.

---

# Overview

System Hacking is performed after completing the information gathering phases of a penetration test. Information collected during footprinting, scanning, enumeration, and vulnerability analysis is leveraged to gain access to target systems, elevate privileges, establish persistence, and accomplish the objectives of a security assessment.

This module demonstrates how attackers and ethical hackers exploit weaknesses in authentication mechanisms, operating systems, applications, and Active Directory environments to obtain and maintain unauthorized access. It also explores common post-exploitation activities, persistence techniques, and methods used to evade detection by clearing forensic evidence. Additionally, the module introduces AI-assisted system hacking to improve productivity during penetration testing activities.

Throughout the practical labs, I learned not only how various system hacking techniques are performed, but also why each phase is important, how they contribute to the overall attack lifecycle, and what defensive controls can be implemented to detect, prevent, and respond to such attacks.

---

# Learning Objectives

After completing this module, I was able to:

- Understand the complete methodology of system hacking.
- Gain unauthorized access using multiple attack techniques.
- Perform password attacks and exploit authentication weaknesses.
- Establish remote access to compromised systems.
- Perform privilege escalation using operating system weaknesses.
- Understand persistence mechanisms used to maintain access.
- Remove forensic evidence by clearing system logs.
- Perform Active Directory attacks using common penetration testing techniques.
- Understand post-exploitation activities performed after gaining access.
- Utilize AI-assisted tools during system hacking activities.
- Recognize the security risks associated with compromised systems and Active Directory environments.
- Understand defensive measures used to detect and mitigate system hacking attacks.

---

# Key Concepts

- System Hacking
- Gaining Access
- Password Attacks
- Buffer Overflow
- Reverse Shell
- Privilege Escalation
- User Account Control (UAC)
- Persistence
- Registry Run Keys
- Keylogging
- Clearing Logs
- Post-Exploitation
- Active Directory Attacks
- Kerberoasting
- AS-REP Roasting
- Pass-the-Hash
- Credential Access
- Lateral Movement
- Artificial Intelligence in System Hacking

---

# Tools Used

*(To be updated after completing all labs.)*

---

# Labs Covered

| Lab | Description |
|------|-------------|
| Lab 1 | Gain Access to the System |
| Lab 2 | Perform Privilege Escalation to Gain Higher Privileges |
| Lab 3 | Maintain Remote Access and Hide Malicious Activities |
| Lab 4 | Clear Logs to Hide the Evidence of Compromise |
| Lab 5 | Perform Active Directory (AD) Attacks Using Various Tools |
| Lab 6 | Perform System Hacking Using AI |

---

# Lab 1: Gain Access to the System

## Objective

To gain unauthorized access to a target system by exploiting weaknesses in authentication mechanisms using credential interception, password cracking, reverse shell access, and buffer overflow techniques.

---

## Background

Gaining access is the first phase of system hacking, where attackers leverage information collected during reconnaissance, scanning, enumeration, and vulnerability analysis to compromise target systems. Common techniques include password attacks, exploitation of vulnerable services, and authentication attacks that allow attackers to obtain valid user credentials without directly compromising the operating system.

This lab demonstrates several techniques used to gain initial access to a target system, beginning with an active online attack that exploits Windows name resolution protocols to capture authentication hashes and recover user credentials.

---

## Task 1: Perform Active Online Attack to Crack the System's Password Using Responder

### Tools Used

- [Responder](../../Tools/Responder.md)
- [John the Ripper](../../Tools/John-the-Ripper.md)

---

### Activity Performed

An active online password attack was performed using Responder to exploit the Link-Local Multicast Name Resolution (LLMNR) and NetBIOS Name Service (NBT-NS) protocols enabled by default on Windows systems. These protocols provide fallback name resolution when DNS resolution fails, making them susceptible to spoofing attacks within local networks.

Responder was configured to listen on the network interface and poison LLMNR and NBT-NS broadcast requests originating from the target Windows 11 system. When the victim attempted to access a network resource, Responder impersonated the requested server and successfully captured the NTLMv2 authentication challenge-response transmitted by the target.

The captured authentication hash was extracted and supplied to John the Ripper, which performed offline password cracking and successfully recovered the user's plaintext password. This demonstrated how insecure name resolution protocols combined with weak passwords can lead to credential compromise without directly attacking the target system.

---

### Observations

- Successfully poisoned LLMNR/NBT-NS name resolution requests.
- Captured the NTLMv2 authentication hash of the logged-in Windows user.
- Extracted the captured authentication hash for offline analysis.
- Successfully recovered the user's plaintext password using John the Ripper.
- Demonstrated the security risks associated with legacy name resolution protocols in Windows environments.

---

### Responder Listening

![Responder Listening](Images/Lab1-Responder-Listening.png)

**Figure 1.1:** Responder was configured to monitor the network interface and poison LLMNR/NBT-NS requests, allowing authentication attempts from the target system to be intercepted.

---

### Captured NTLM Authentication Hash

![Captured NTLM Hash](Images/Lab1-Responder-NTLM-Hash-Captured.png)

**Figure 1.2:** Responder successfully intercepted the NTLMv2 authentication challenge-response of the target user, demonstrating how LLMNR/NBT-NS poisoning can expose credential hashes within an internal network.

---

### Password Successfully Recovered

![Password Cracked](Images/Lab1-John-Password-Cracked.png)

**Figure 1.3:** John the Ripper successfully recovered the plaintext password from the captured NTLM authentication hash, illustrating the effectiveness of offline password cracking against weak credentials.

---

### Learning Outcome

This task demonstrated how insecure Windows name resolution protocols such as LLMNR and NBT-NS can be exploited to capture NTLM authentication hashes and recover user credentials. It reinforced the importance of disabling unnecessary legacy protocols, enforcing strong password policies, and implementing network protections to mitigate credential interception attacks.

---

### Attack Flow

```mermaid
flowchart TD

    A[Victim Requests Network Resource]
    --> B[LLMNR / NBT-NS Broadcast]
    --> C[Responder Spoofs Requested Server]
    --> D[Victim Sends NTLM Authentication]
    --> E[Capture NTLMv2 Hash]
    --> F[Offline Password Cracking]
    --> G[Recover User Credentials]

    classDef start fill:#1f2937,color:#fff,stroke:#2563eb
    classDef process fill:#374151,color:#fff,stroke:#2563eb
    classDef decision fill:#7c3aed,color:#fff,stroke:#8b5cf6
    classDef success fill:#059669,color:#fff,stroke:#10b981

    class A start
    class B,C,D,E,F process
    class G success
```

---

## Task 2: Gain Access to a Remote System Using Reverse Shell Generator

### Tools Used

- [Reverse Shell Generator](../../Tools/Reverse-Shell-Generator.md)
- [Metasploit](../../Tools/Metasploit.md)

---

### Activity Performed

A reverse shell payload was generated using Reverse Shell Generator to automate the creation of reverse shell payloads and listener configurations. Instead of manually constructing payloads and Metasploit listener commands, the tool generated the required MSFVenom payload and corresponding Meterpreter listener based on the specified local IP address and listening port.

The generated payload was transferred to the target Windows system and executed, establishing a Meterpreter reverse shell connection with the attacking machine. The active session was verified using Meterpreter commands, confirming successful remote access to the compromised host.

In addition to Meterpreter, Reverse Shell Generator was used to create a HoaxShell PowerShell payload. After configuring the HoaxShell listener and executing the generated PowerShell script on the target system, a second reverse shell session was successfully established. The active session was verified by identifying the logged-on user through remote command execution.

This task demonstrated how automated payload generation simplifies reverse shell deployment while illustrating multiple methods of establishing remote command execution on a compromised Windows system.

---

### Observations

- Successfully generated a Windows Meterpreter reverse shell payload.
- Established a Meterpreter session with the target Windows system.
- Verified successful remote access using Meterpreter commands.
- Generated a HoaxShell PowerShell reverse shell payload.
- Successfully established a PowerShell-based reverse shell session.
- Verified remote command execution by identifying the logged-on user.

---

### MSFVenom Payload Generated

![MSFVenom Payload](Images/Lab1-ReverseShellGenerator-MSFVenom-Payload.png)

**Figure 1.4:** Reverse Shell Generator automatically generated the MSFVenom payload command based on the configured listener IP address and port, simplifying reverse shell payload creation.

---

### Meterpreter Session Established

![Meterpreter Session](Images/Lab1-Meterpreter-Session-Established.png)

**Figure 1.5:** Execution of the generated payload established a Meterpreter session with the target Windows system, providing interactive remote access to the compromised host.

---

### HoaxShell Payload Generated

![HoaxShell Payload](Images/Lab1-HoaxShell-Payload-Generated.png)

**Figure 1.6:** Reverse Shell Generator produced a PowerShell-based HoaxShell payload, enabling remote access using native Windows PowerShell capabilities.

---

### HoaxShell Session Established

![HoaxShell Session](Images/Lab1-HoaxShell-Session-Established.png)

**Figure 1.7:** The generated PowerShell payload successfully established a HoaxShell session, allowing remote command execution and verification of the active user on the compromised system.

---

### Learning Outcome

This task demonstrated how reverse shell payload generation and automated listener configuration can streamline remote access during penetration testing. It also highlighted the effectiveness of multiple reverse shell techniques, including Meterpreter and PowerShell-based sessions, while emphasizing the importance of endpoint protection, application control, and network monitoring in detecting and preventing unauthorized remote access.

---

### Attack Flow

```mermaid
flowchart TD

    A[Configure Listener IP and Port]
    --> B[Generate Reverse Shell Payload]
    --> C[Deploy Payload to Target]
    --> D[Execute Payload]
    --> E[Establish Reverse Shell Session]
    --> F[Verify Remote Access]

    classDef start fill:#1f2937,color:#fff,stroke:#2563eb
    classDef process fill:#374151,color:#fff,stroke:#2563eb
    classDef success fill:#059669,color:#fff,stroke:#10b981

    class A start
    class B,C,D,E process
    class F success
```

---

## Task 3: Perform Buffer Overflow Attack to Gain Access to a Remote System

### Tools Used

- [Immunity Debugger](../../Tools/Immunity-Debugger.md)
- [Netcat](../../Tools/Netcat.md)
- [Spike](../../Tools/Spike.md)
- [Mona](../../Tools/Mona.md)
- [Metasploit](../../Tools/Metasploit.md)

---

### Activity Performed

A buffer overflow attack was performed against a vulnerable server application to gain remote access by manipulating the application's execution flow. The exploitation process followed a structured methodology consisting of vulnerability identification, exploit development, instruction pointer control, shellcode generation, and payload execution.

**Vulnerability Identification:**  
The vulnerable server was attached to Immunity Debugger, allowing its execution to be monitored throughout the attack. Initial interaction with the service using Netcat identified the available functions, after which Spike templates were used to perform spiking against individual commands. The TRUN function caused the application to crash and overwrite stack registers, confirming the presence of a buffer overflow vulnerability.

**Fuzzing and Offset Identification:**  
Python fuzzing scripts were executed to determine the approximate number of bytes required to crash the application. Pattern generation and offset calculation utilities from the Metasploit Framework were then used to determine the exact offset at which the Extended Instruction Pointer (EIP) register could be overwritten.

**Instruction Pointer Control:**  
Custom Python scripts verified that the EIP register could be reliably overwritten with controlled values. Additional testing identified the absence of problematic characters within the payload, ensuring that the generated shellcode would execute correctly without corruption during transmission.

**Exploit Development:**  
Mona was used within Immunity Debugger to enumerate loaded modules and identify a module lacking modern memory protection mechanisms. The appropriate `JMP ESP` return address was located and incorporated into the exploit to redirect program execution toward the injected shellcode.

**Shellcode Generation and Exploitation:**  
A Windows reverse TCP shell payload was generated using MSFVenom and embedded into the exploit script. After configuring Netcat to listen for incoming connections, the completed exploit was executed against the vulnerable server. Successful execution redirected program control to the injected shellcode, resulting in a reverse shell connection from the target system and providing remote command execution.

This task demonstrated the complete exploit development lifecycle, from identifying a vulnerable function to achieving remote code execution through a successfully crafted buffer overflow exploit.

---

### Observations

- Identified the TRUN function as vulnerable to buffer overflow attacks.
- Determined the approximate crash size through fuzzing.
- Successfully calculated the precise offset required to overwrite the EIP register.
- Verified complete control over the EIP register using controlled input values.
- Confirmed that the payload contained no bad characters affecting shellcode execution.
- Identified a suitable module without memory protection using Mona.
- Located a valid `JMP ESP` return address for exploit redirection.
- Successfully generated reverse shell payload using MSFVenom.
- Established a reverse shell connection to the target vulnerable system.
- Verified successful remote command execution after exploitation.

---

### Vulnerable Server Attached to Immunity Debugger

![Vulnerable Server](Images/Lab1-Vulnserver-Running.png)

**Figure 1.8:** The vulnerable server was attached to Immunity Debugger and executed under controlled conditions, enabling runtime analysis and exploit development throughout the buffer overflow assessment.

---

### Buffer Overflow Triggered through the TRUN Function

![TRUN Buffer Overflow](Images/Lab1-TRUN-Buffer-Overflow.png)

**Figure 1.9:** Executing the vulnerable `TRUN` function caused the application to pause within Immunity Debugger and overwrite critical processor registers, confirming the presence of a controllable buffer overflow vulnerability.

---

### Fuzzing Identified the Crash Point

![Fuzzing Crash](Images/Lab1-Fuzzing-Crash.png)

**Figure 1.10:** Fuzzing progressively increased the input size until the vulnerable application crashed, allowing the approximate buffer size required for exploitation to be identified.

---

### EIP Register Successfully Controlled

![EIP Overwrite](Images/Lab1-EIP-Control-Verified.png)

**Figure 1.11:** The EIP register was successfully overwritten with a controlled value, confirming that execution flow could be redirected to attacker-controlled shellcode.

---

### Bad Character Analysis

![Bad Characters](Images/Lab1-No-Bad-Characters.png)

**Figure 1.12:** Examination of the injected payload confirmed the absence of problematic characters that could interfere with shellcode execution during exploitation.

---

### Vulnerable Module Identified Using Mona

![Mona Modules](Images/Lab1-Mona-Vulnerable-Module.png)

**Figure 1.13:** Mona identified a module without modern memory protection mechanisms, providing a suitable target for reliable exploitation.

---

### JMP ESP Return Address Identified

![JMP ESP](Images/Lab1-JMP-ESP-Return-Address.png)

**Figure 1.14:** Mona located a valid `JMP ESP` instruction within the vulnerable module, enabling execution to be redirected toward the injected shellcode.

---

### Reverse Shell Successfully Established

![Reverse Shell](Images/Lab1-Reverse-Shell-Established.png)

**Figure 1.15:** Successful execution of the exploit established a reverse shell connection, providing remote command execution on the compromised target system.

---

### Learning Outcome

This task demonstrated the complete methodology of buffer overflow exploitation, including vulnerability discovery, fuzzing, offset calculation, instruction pointer control, shellcode generation, and payload execution. It reinforced how insecure memory handling can lead to arbitrary code execution and highlighted the importance of modern exploit mitigation techniques such as DEP, ASLR, and secure software development practices.

---

### Attack Flow

```mermaid
flowchart TD

    A[Launch Vulnerable Server]
    --> B[Identify Vulnerable Function]
    --> C[Perform Fuzzing]
    --> D[Calculate Offset]
    --> E[Overwrite EIP]
    --> F[Identify Bad Characters]
    --> G[Locate Vulnerable Module]
    --> H[Find JMP ESP Address]
    --> I[Generate Shellcode]
    --> J[Inject Exploit]
    --> K[Establish Reverse Shell]

    classDef start fill:#1f2937,color:#fff,stroke:#2563eb
    classDef process fill:#374151,color:#fff,stroke:#2563eb
    classDef exploit fill:#7c3aed,color:#fff,stroke:#8b5cf6
    classDef success fill:#059669,color:#fff,stroke:#10b981

    class A start
    class B,C,D,E,F,G,H,I,J process
    class K success
```

---

## Overall Learning Outcome

This lab demonstrated multiple techniques used to gain initial access to target systems through credential interception, reverse shell deployment, and memory corruption exploitation. It provided practical experience in capturing and cracking authentication credentials, establishing remote access using automated reverse shell payloads, and developing a complete buffer overflow exploit to achieve remote code execution. Overall, the lab reinforced the importance of secure authentication mechanisms, robust memory protection techniques, secure software development practices, and continuous monitoring to defend against common system hacking attacks.

---

# Lab 2: Perform Privilege Escalation to Gain Higher Privileges

## Objective

To obtain higher privileges on a compromised Windows system by bypassing User Account Control (UAC) mechanisms and exploiting built-in accessibility features to gain persistent SYSTEM-level access.

---

## Background

Privilege escalation is the second phase of system hacking, performed after successfully gaining initial access to a target system. Attackers attempt to elevate their privileges from a standard user account to administrative or SYSTEM-level access in order to execute privileged operations, disable security controls, access restricted resources, and establish long-term persistence.

Windows provides several security mechanisms, such as User Account Control (UAC), to restrict unauthorized privilege elevation. However, attackers can exploit operating system misconfigurations, trusted applications, registry-based bypass techniques, and built-in accessibility features to circumvent these protections. Once elevated privileges are obtained, persistence mechanisms can be implemented to retain privileged access even after system reboots or user logouts.

This lab demonstrates privilege escalation through a UAC bypass using the FodHelper Registry Key technique and persistence through exploitation of the Sticky Keys accessibility feature, illustrating how attackers can obtain and maintain SYSTEM-level access on Windows systems.

---

## Task 1: Escalate Privileges by Bypassing UAC and Exploiting Sticky Keys

### Tools Used

- [Metasploit](../../Tools/Metasploit.md)

---

### Activity Performed

A privilege escalation attack was performed by bypassing Windows User Account Control (UAC) and exploiting the Sticky Keys accessibility feature to obtain persistent SYSTEM-level access to the target machine. Initially, an MSFVenom Meterpreter payload was generated and delivered to the target system, establishing a Meterpreter session with the compromised host.

After verifying the active session, a Metasploit local privilege escalation module exploiting the FodHelper Registry Key was executed to bypass UAC restrictions without prompting the user for administrative approval. Once the bypass succeeded, the Meterpreter session was elevated to the **NT AUTHORITY\SYSTEM** account, granting unrestricted administrative privileges on the target system.

To demonstrate persistence, the Sticky Keys accessibility feature was replaced using the Metasploit Sticky Keys post-exploitation module. After locking the target system, pressing the **Shift** key five times launched a command prompt instead of the normal Sticky Keys dialog, providing SYSTEM-level command execution directly from the Windows logon screen without requiring user authentication.

This task demonstrated how privilege escalation combined with persistence techniques enables attackers to maintain privileged access even after the initial compromise.

---

### Observations

- Successfully generated and deployed a Meterpreter payload.
- Established a Meterpreter session with the target Windows system.
- Bypassed Windows User Account Control (UAC) using the FodHelper Registry Key technique.
- Successfully elevated privileges to the **NT AUTHORITY\SYSTEM** account.
- Configured the Sticky Keys accessibility feature to obtain persistent SYSTEM-level access.
- Verified SYSTEM privileges from the Windows logon screen without authenticating to the operating system.

---

### MSFVenom Payload Generated

![MSFVenom Payload](Images/Lab2-MSFVenom-Payload-Generated.png)

**Figure 2.1:** MSFVenom successfully generated a Windows Meterpreter reverse TCP payload, which was later executed on the target system to establish an initial Meterpreter session.

---

### Meterpreter Session Established

![Meterpreter Session](Images/Lab2-Meterpreter-Session-Established.png)

**Figure 2.2:** Execution of the generated payload established a Meterpreter session with the target Windows system, allowing reconnaissance commands such as `sysinfo` to verify the compromised host.

---

### UAC Bypass and SYSTEM Privileges

![UAC Bypass](Images/Lab2-UAC-Bypass-Success.png)

**Figure 2.3:** The Metasploit FodHelper UAC bypass module successfully elevated the Meterpreter session to **NT AUTHORITY\SYSTEM**, providing unrestricted administrative privileges on the compromised system.

---

### Sticky Keys Persistence

![Sticky Keys Persistence](Images/Lab2-Sticky-Keys-Persistence.png)

**Figure 2.4:** Exploiting the Sticky Keys accessibility feature opened a command prompt at the Windows logon screen with SYSTEM privileges, demonstrating how persistence can be maintained without user authentication.

---

### Learning Outcome

This task demonstrated how attackers can escalate privileges by bypassing Windows User Account Control and maintain persistent SYSTEM-level access by abusing built-in accessibility features. It reinforced the importance of protecting privileged accounts, restricting unauthorized modifications to operating system components, and monitoring post-exploitation activities that may establish long-term persistence.

---

### Attack Flow

```mermaid
flowchart TD

    A[Generate Meterpreter Payload]
    --> B[Execute Payload on Target]
    --> C[Establish Meterpreter Session]
    --> D[Bypass UAC]
    --> E[Escalate to SYSTEM]
    --> F[Exploit Sticky Keys]
    --> G[Persistent SYSTEM Access]

    classDef start fill:#1f2937,color:#fff,stroke:#2563eb
    classDef process fill:#374151,color:#fff,stroke:#2563eb
    classDef success fill:#059669,color:#fff,stroke:#10b981

    class A start
    class B,C,D,E,F process
    class G success
```

---

## Overall Learning Outcome

This lab demonstrated how attackers can escalate privileges on a compromised Windows system by bypassing User Account Control (UAC) and exploiting built-in accessibility features to obtain persistent SYSTEM-level access. It provided practical experience in elevating privileges using the FodHelper Registry Key technique and maintaining privileged access through the Sticky Keys mechanism. Overall, the lab reinforced the importance of protecting privileged accounts, securing operating system components, monitoring persistence mechanisms, and implementing defense-in-depth strategies to detect and prevent unauthorized privilege escalation.

---

# Lab 3: Maintain Remote Access and Hide Malicious Activities

## Objective

To maintain persistent access to a compromised system and monitor user activities using authorized surveillance software, demonstrating how attackers can observe victim behavior while remaining active on the target machine.

---

## Background

After obtaining administrative or SYSTEM-level privileges, attackers often establish persistence and deploy monitoring mechanisms to retain long-term access to compromised systems. These techniques enable continuous observation of user activities, collection of sensitive information, and maintenance of control even after the initial compromise has occurred.

System monitoring software and spyware can record keystrokes, capture screenshots, track application usage, monitor visited websites, and log file operations without the user's knowledge. Although these capabilities are intended for legitimate administrative and parental control purposes, attackers may misuse them to gather sensitive information and maintain surveillance over compromised systems.

This lab demonstrates how monitoring software can be deployed on a target Windows system to collect user activity data and transmit it to a centralized dashboard. It highlights the risks associated with unauthorized surveillance while emphasizing the importance of endpoint protection, application control, and continuous monitoring to detect persistence mechanisms and spyware.

---

## Task 1: User System Monitoring and Surveillance

### Tools Used

- [Refog Personal Monitor](../../Tools/Refog-Personal-Monitor.md)

---

### Activity Performed

Refog Personal Monitor was deployed on the target Windows system to demonstrate user activity monitoring and surveillance. After establishing remote desktop access to the target machine, the monitoring agent was installed, linked to an online Refog account, and configured to record user activities.

Once deployed, the target system was restarted and used as a legitimate user to perform common activities such as web browsing and application usage. These activities were automatically synchronized with the online Refog dashboard, allowing real-time monitoring of the compromised system.

The dashboard successfully displayed information including visited websites, application usage, and overall computer activity, demonstrating how surveillance software can collect and centralize user activity without requiring continued physical access to the target machine.

This task highlighted how attackers can maintain visibility into a compromised system through monitoring software while reinforcing the importance of detecting unauthorized surveillance tools and persistence mechanisms.

---

### Observations

- Successfully deployed Refog Personal Monitor on the target system.
- Linked the monitoring agent to an online dashboard.
- Established persistent monitoring of the compromised machine.
- Captured user browsing activity through the Refog dashboard.
- Successfully monitored user activity remotely.
- Demonstrated how surveillance software can maintain visibility into a compromised system.

---

### Refog Dashboard Connected

![Refog Dashboard](Images/Lab3-Refog-Online-Dashboard.png)

**Figure 3.1:** The target Windows system successfully synchronized with the Refog online dashboard, confirming that the monitoring agent had been deployed and was actively communicating with the management portal.

---

### User Activity Monitoring

![User Activity Monitoring](Images/Lab3-Refog-User-Activity-Monitoring.png)

**Figure 3.2:** The Refog dashboard displayed the victim's recorded web activity, demonstrating successful collection and remote monitoring of user behavior through the deployed surveillance software.

---

### Learning Outcome

This task demonstrated how monitoring software can be deployed to maintain visibility into a compromised system by recording user activities and transmitting them to a centralized dashboard. It reinforced the importance of endpoint protection, application control, continuous monitoring, and detecting unauthorized surveillance software to prevent long-term compromise.

---

### Attack Flow

```mermaid
flowchart TD

    A[Deploy Monitoring Agent]
    --> B[Install on Target System]
    --> C[Link to Online Dashboard]
    --> D[Monitor User Activity]
    --> E[Collect Activity Data]
    --> F[Review Activity Remotely]

    classDef start fill:#1f2937,color:#fff,stroke:#2563eb
    classDef process fill:#374151,color:#fff,stroke:#2563eb
    classDef success fill:#059669,color:#fff,stroke:#10b981

    class A start
    class B,C,D,E process
    class F success
```

---

## Task 2: Maintain Persistence by Modifying Registry Run Keys

### Tools Used

- [Metasploit](../../Tools/Metasploit.md)
- [Registry Editor](../../Tools/Registry-Editor.md)

---

### Activity Performed

A Windows persistence mechanism was established by creating a malicious entry within the **Run** registry key. Initially, two Meterpreter payloads were generated using MSFVenom: one to obtain an initial Meterpreter session and another to serve as the persistent payload executed during system startup.

After gaining access to the target system, Windows User Account Control (UAC) was bypassed using the **SilentCleanup** privilege escalation technique available in Metasploit. Once elevated to **NT AUTHORITY\SYSTEM**, a command shell was opened and a new registry value was created under the **HKLM\Software\Microsoft\Windows\CurrentVersion\Run** key, referencing the malicious payload stored on the target system.

A second Meterpreter listener was configured to receive incoming connections from the persistence payload. After restarting the Windows system, the operating system automatically executed the payload configured within the Run registry key, establishing a new Meterpreter session without requiring additional exploitation.

This task demonstrated how attackers can leverage Windows startup registry keys to maintain persistent remote access across system reboots while automatically reconnecting to attacker-controlled infrastructure whenever an authorized user logs into the system.

---

### Observations

- Successfully generated Meterpreter persistence payloads using MSFVenom.
- Established an initial Meterpreter session with the target system.
- Bypassed User Account Control (UAC) using the SilentCleanup technique.
- Elevated privileges to **NT AUTHORITY\SYSTEM**.
- Successfully created a malicious Run registry key entry.
- Verified automatic execution of the persistence payload after system restart.
- Successfully re-established a Meterpreter session through the configured Run registry key.

---

### Registry Persistence Payload Generated

![Registry Payload](Images/Lab3-Registry-Payload-Generated.png)

**Figure 3.3:** MSFVenom successfully generated the executable payload that was later configured within the Windows Run registry key to establish persistence.

---

### Run Registry Key Modified

![Registry Run Key](Images/Lab3-Run-Registry-Modified.png)

**Figure 3.4:** A new value was successfully added to the Windows Run registry key, configuring the operating system to automatically execute the malicious payload during user logon.

---

### Persistent Meterpreter Session Established

![Persistent Session](Images/Lab3-Persistent-Meterpreter-Session.png)

**Figure 3.5:** After restarting the target system, the payload configured within the Run registry key executed automatically and established a new Meterpreter session, demonstrating successful persistence.

---

### Learning Outcome

This task demonstrated how Windows startup registry keys can be abused to maintain persistent remote access after the initial compromise. It reinforced the importance of monitoring registry modifications, restricting unauthorized privilege escalation, implementing endpoint protection, and auditing startup locations commonly targeted by attackers.

---

### Attack Flow

```mermaid
flowchart TD

    A[Generate Persistence Payload]
    --> B[Gain Initial Access]
    --> C[Bypass UAC]
    --> D[Obtain SYSTEM Privileges]
    --> E[Modify Run Registry Key]
    --> F[Restart Target System]
    --> G[Automatic Payload Execution]
    --> H[Re-establish Meterpreter Session]

    classDef start fill:#1f2937,color:#fff,stroke:#2563eb
    classDef process fill:#374151,color:#fff,stroke:#2563eb
    classDef success fill:#059669,color:#fff,stroke:#10b981

    class A start
    class B,C,D,E,F,G process
    class H success
```

---

## Overall Learning Outcome

This lab demonstrated multiple techniques used to maintain long-term access to compromised Windows systems through user activity monitoring and persistence mechanisms. It provided practical experience in deploying surveillance software to observe user behavior remotely and configuring Windows Run registry keys to automatically execute malicious payloads after system startup. Overall, the lab reinforced the importance of monitoring persistence mechanisms, protecting registry startup locations, detecting unauthorized monitoring software, and implementing endpoint security controls to prevent long-term compromise.