<p align="center">
  <img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1> Unlocking Accounts and Resetting Passwords using Active Directory Deployed in the Cloud (Azure)</h1>
<p>In this home lab, I simulate a locked-out user account after multiple failed login attempts and demonstrate how to unlock it within Active Directory as an admin. Additionally, I configure the Account Lockout Threshold in Group Policy and analyze logs for troubleshooting and auditing purposes.</p>


<h2>Environments and Technologies Used</h2>
<ul>
  <li>Microsoft Azure (Virtual Machines/Compute)</li>
  <li>Remote Desktop</li>
  <li>Active Directory Domain Services</li>
  <li>PowerShell</li>
</ul>

<h2>Operating Systems Used</h2>
<ul>
  <li>Windows Server 2022</li>
  <li>Windows 10 (21H2)</li>
</ul>

<h2>Key Takeaways and Skills Developed</h2>
<ul>
  <li><strong>Active Directory Management:</strong> Demonstrated proficiency in managing user accounts, including account recovery and troubleshooting locked-out accounts in Active Directory.</li>
  <li><strong>Policy Configuration:</strong> Configured and enforced Account Lockout Thresholds using Group Policy to enhance security and mitigate brute-force attacks.</li>
  <li><strong>Incident Resolution:</strong> Successfully unlocked user accounts, reset passwords, and restored access, showcasing effective problem-solving skills in user account administration.</li>
  <li><strong>Advanced Account Control:</strong> Gained experience disabling and re-enabling accounts, improving understanding of user lifecycle management in an enterprise environment.</li>
  <li><strong>Log Analysis and Auditing:</strong> Analyzed logs on both the Domain Controller and client machine to identify and resolve login issues, demonstrating critical thinking and attention to detail.</li>
  <li><strong>Cloud Administration:</strong> Leveraged Azure Virtual Machines and Remote Desktop for secure, cloud-based Active Directory management and troubleshooting.</li>
  <li><strong>Security Best Practices:</strong> Applied security principles in configuring account lockout policies and performing account recovery, enhancing organizational security posture.</li>
</ul>

<h2>High-Level Deployment and Configuration Steps</h2>

<h3>Dealing with Account Lockouts</h3>
<ol>
  <li>Log in to DC-1 and pick a user account you created previously (bak.gog).</li>

  <li>Configure Group Policy to lock out an account after 5 failed login attempts, and login to client 1 to force a group policy update on jane_admin account with the gpupdate /force command in command prompt:</li>
  <p align="center">
    
  ![Screenshot (124)](https://github.com/user-attachments/assets/f0d3e9f1-d884-4ba3-850e-e8daa41c098e)
![Screenshot (125)](https://github.com/user-attachments/assets/b17fda9f-da51-487a-9dfe-06a7e75f031d)


  </p>

  <li>Attempt to log in 6 times with an incorrect password. The account will be locked out.</li>

  <li>Unlock the account and reset the password. Attempt to log in again to bak.gog.</li>
  <p align="center">
   
  ![Screenshot (127)](https://github.com/user-attachments/assets/5b746fca-e12e-4286-a310-373dc6c0e9f3)
  ![Screenshot (129)](https://github.com/user-attachments/assets/5e996cac-f0a5-4ba3-824d-d8514c456cb5)
![Screenshot (131)](https://github.com/user-attachments/assets/343c1e59-4bed-448f-b64f-5ba6a574b57e)

  

  </p>
</ol>


<h3>Observing Logs</h3>
<ol>
  <li>Observe the logs in the Domain Controller.</li>
  <li>Observe the logs on the client machine.</li>
  <p align="center">
    
  ![Screenshot (133)](https://github.com/user-attachments/assets/6ea91aa1-7b15-4370-89b7-9a69c574e52d)

  </p>
</ol>



