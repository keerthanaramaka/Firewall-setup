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
Purpose: Ensure the firewall is active and enforcing rules.
Command
'''powershell
Set-NetFirewallProfile -Profile Domain,Public,Private -Enabled True
### Allow Inbound HTTP Traffic (Port 80)
Purpose: Permit web server traffic (HTTP) to your system.
Command
'''powershell
New-NetFirewallRule -DisplayName "Allow HTTP" -Direction Inbound -LocalPort 80 -Protocol TCP -Action Allow
### Block Inbound Telnet Traffic (Port 23)
Purpose: Prevent insecure remote access attempts.
Command
'''powershell
New-NetFirewallRule -DisplayName "Block Telnet" -Direction Inbound -LocalPort 23 -Protocol TCP -Action Block
### View Existing Firewall Rules
Purpose: Review all configured rules.
Command
'''powershell
Get-NetFirewallRule
### Delete a Specific Firewall Rule
Purpose: Remove an unnecessary or incorrect rule.
Command
'''powershell
Remove-NetFirewallRule -DisplayName "Block Telnet"
### Test Network Connection
Purpose: Verify if a specific port is open or blocked.
Command
'''powershell
Test-NetConnection -ComputerName localhost -Port 80
### Returns connection success if port 80 is allowed.
To test a blocked port (should fail)
'''powershell
Test-NetConnection -ComputerName localhost -Port 23
## Purpose
- Control access to your system's network services.
- Prevent unauthorized inbound connections.
- Allow only trusted and necessary traffic.
- Improve system security posture through enforced policies.
#### Command
```powershell
dism /online /Enable-Feature /FeatureName:TelnetClient



