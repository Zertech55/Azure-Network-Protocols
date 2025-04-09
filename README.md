<p align="center">
<img src="https://github.com/user-attachments/assets/4136273c-c6b5-4a55-b3e3-d8ab8e332127" alt="Traffic Examination"/>
</p>

<h1>Administration using Group Policy and Active Directory</h1>
In this tutorial, we examine a series of scenarios to illustrate the actions a network administrator would take under different circumstances. <br />



<h2Steps</h2>

1. Dealing with Account Lockouts
2. Enabling and Disabling Accounts
3. Observing Logs

<h2>Actions and Observations</h2>

</p>
<p>
1. Dealing with Account Lockouts
</p>
<br />
<p>
<img src="https://github.com/user-attachments/assets/4b15b955-0b63-4d57-a4fa-8904cfe27772" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Dealing with account lockouts using Microsoft Group Policy involves configuring settings to manage lockout thresholds, durations, and reset policies effectively. First, access the Group Policy Management Console on a domain controller or a machine with administrative tools installed. Navigate to the Default Domain Policy or create a new Group Policy Object, then edit it. Under Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Account Lockout Policy, you can define three key settings: "Account lockout threshold" (ex: 5 invalid attempts), which sets the number of failed logon attempts before a lockout; "Account lockout duration" (ex: 15 minutes), which determines how long the account remains locked, and "Reset account lockout counter after" (ex: 15 minutes), which specifies when the failed attempt counter resets. Link the Group Policy Object to the appropriate organizational unit, and use the "gpupdate /force" command to enforce the changes. This approach helps balance security and usability by preventing brute-force attacks while minimizing user disruption.
</p>
<br />

</p>
<p>
2. Enabling and Disabling Accounts
</p>
<br />
<p>
<img src="https://github.com/user-attachments/assets/8a8971e0-5274-4ce4-8991-5194c98cf0fd" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Typically, account status management is performed using Active Directory Users and Computers (ADUC), where administrators can right-click a user account to enable or disable it, or via PowerShell cmdlets such as Enable-ADAccount and Disable-ADAccount. However, for local user accounts on individual computers, Group Policy Preferences offers a solution. By navigating to User Configuration > Preferences > Control Panel Settings > Local Users and Groups in the Group Policy Management Editor, administrators can create policies to manage local accounts, including setting their status to enabled or disabled
</p>
<br />

</p>
<p>
3. Observing Logs
</p>
<br />
<p>
<img src="https://github.com/user-attachments/assets/effaf5c0-2c04-4033-a093-f92ee1031bf0" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Event Viewer is an essential tool for observing detailed logs of system events to monitor system health, troubleshoot issues, and enhance security. To use it effectively, start by accessing Event Viewer through the Administrative Tools section in the Control Panel or by searching for it in the Start menu. Once opened, it presents logs categorized into areas like Application, Security, and System. For example, to investigate a user’s login problems, navigate to the Security log and filter for event ID 4625, which flags failed login attempts—helping determine if the issue is due to incorrect credentials or a potential security threat like a brute-force attack. Similarly, to diagnose a server crash, check the System log for critical errors or hardware-related issues logged around the crash time. You can refine your search by filtering logs using event ID, source, or severity via the "Filter Current Log" option in the right-hand pane. For deeper analysis or auditing, export logs by right-clicking a log category and selecting "Save All Events As...", choosing formats like .evtx or .csv. Regularly reviewing these logs ensures proactive identification of vulnerabilities and maintains system stability.
</p>
<br />

1.![Screenshot 2025-04-08 190831](https://github.com/user-attachments/assets/4b15b955-0b63-4d57-a4fa-8904cfe27772)

2.![image](https://github.com/user-attachments/assets/8a8971e0-5274-4ce4-8991-5194c98cf0fd)

![image](https://github.com/user-attachments/assets/4136273c-c6b5-4a55-b3e3-d8ab8e332127)

3.![Screenshot 2025-04-08 192105](https://github.com/user-attachments/assets/effaf5c0-2c04-4033-a093-f92ee1031bf0)
