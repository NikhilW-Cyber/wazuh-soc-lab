# Incident Report – Failed Login Detection

## 1. Incident Summary
Multiple failed login attempts were detected on a Windows 10 endpoint monitored by Wazuh SIEM.

## 2. Alert Information
- Windows Event ID: 4625
- Wazuh Rule ID: 60105
- Alert Level: 5 (Medium Severity)
- Target Username: fakeuser
- Source IP Address: ::1 (Local Machine)
- Number of Attempts: 9

## 3. Investigation Findings
The failed authentication attempts originated from the local machine (::1), indicating local credential testing rather than a remote brute-force attack.

The username targeted ("fakeuser") does not exist on the system.

## 4. Risk Assessment
Although this activity was generated for testing purposes, similar patterns in a production environment could indicate:
- Brute-force attack attempts
- Credential stuffing
- Unauthorized access attempts

## 5. Recommended Actions
- Implement account lockout policy
- Monitor repeated failed login patterns
- Review authentication logs regularly
- Enable enhanced logging (Sysmon)

## 6. Skills Demonstrated
- SIEM log investigation
- Rule analysis
- Event correlation
- Basic incident documentation
