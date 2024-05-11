# Network-File-Shares-and-Permissions
<img src="https://i.imgur.com/AeiqMDZ.png" alt="Traffic Examination"/>
</p>

<h1>Network File Shares and Permissions</h1>
In this guide, we explore network file sharing and permissions on Azure Virtual Machines, utilizing Wireshark for traffic examination and experimenting with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Domain Controller/Client Machine)
- Remote Desktop
- Shared Network Files

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)

</p>
<p>
<h2> Tutorial Overview </h2>
</p>
<p>
This lab focuses on setting up shared network files and permissions. We'll create folders on the DC-1 VM and configure access restrictions. Start by navigating to the C:/ drive on DC-1 and creating four folders: "read-access", "read/write-access", "no-access", and "accounting".
</p>
<br />

<p>
<img src="https://i.imgur.com/k70dozS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After creating the folders, share them on the network to enable access from the client-1 machine. Then, customize permissions for each folder on DC-1. For instance, grant read-only access to domain users for the "read-access" folder, provide read/write permissions for domain users to the "read/write-access" folder, and restrict access to the "no-access" folder to domain admins only.
</p>
<br />

<p>
<img src="https://i.imgur.com/wcpB5Ex.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/hku11Pt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
To verify the configurations, log in to the client machine with a regular user account and test accessing the shared files. The permissions should enforce the specified access levels correctly.
</p>
<br />
<p>
<img src="https://i.imgur.com/CGQ8yaO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/f9TldBO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
Next, return to the DC-1 VM and create a security group called "Accountants" in Active Directory. Only users added to this group will have access to the "Accountants" folder. Share the folder accordingly, ensuring that regular users are restricted from accessing it unless they are part of the "Accountants" security group.
</p>
<br />
<p>
<img src="https://i.imgur.com/QADy92Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/BUm3L2Q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/fH8fU7b.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
