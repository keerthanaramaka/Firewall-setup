# Firewall-setup
## Objective
Configure and test firewall rules to allow or block specific network traffic on a Windows system. Demonstrate understanding of traffic filtering for security.
## Tools Used
- Windows PowerShell (with administrative privileges)
- Windows Defender Firewall
- Test-NetConnection (built-in)
- Optional: Telnet client
## Windows Implementation
### Enable Windows Firewall
Ensure the firewall is active and enforcing rules.
### Block Inbound Telnet Traffic (Port 23)
Prevent insecure remote access attempts.
### View Existing Firewall Rules
Review all configured rules.
### Delete a Specific Firewall Rule
Remove an unnecessary or incorrect rule.
### Test Network Connection
Verify if a specific port is open or blocked.
## Purpose
- Control access to your system's network services.
- Prevent unauthorized inbound connections.
- Allow only trusted and necessary traffic.
- Improve system security posture through enforced policies.
#### Command
```powershell
dism /online /Enable-Feature /FeatureName:TelnetClient



