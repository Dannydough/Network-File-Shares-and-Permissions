# Network-File-Shares-and-Permissions

**Create sample file shares with different permission levels**

1.) Log in to DC-1 using your domain admin account (mydomain.com\jane_admin).

<p>
<img src="https://imgur.com/Bg0eppT.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

2.) Log in to Client-1 as a standard user (mydomain<someuser>).

<p>
<img src="https://imgur.com/nGoSv9r.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

3.) On DC-1, create the following four folders on the C:\ drive: "read-access", "write-access", "no-access", and "accounting".

<p>
<img src="https://imgur.com/DjRpUiu.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

4.) Set the following permissions and share the folders:

- Folder: "read-access", Group: "Domain Users", Permission: "Read"
- Folder: "write-access", Group: "Domain Users", Permissions: "Read/Write"
- Folder: "no-access", Group: "Domain Admins", Permissions: "Read/Write"
- (Leave the "accounting" folder for now.)

<p>
<img src="https://imgur.com/t9ILiUN.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://imgur.com/dq3eR72.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://imgur.com/sYyDdVT.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

**As a normal user, attempt the following steps:**

5.) On Client-1, open the Run dialog (Start → Run). Navigate to the shared folder path: \\dc-1.

<p>
<img src="https://imgur.com/7WQPmSh.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
6.) Attempt to access each of the folders you just created:

- read-access
- write-access
- no-access
  **Test the following:**

- *Can you open and view the contents of the folders?*
- *Can you create or modify files within the folders?*
- *Which folders can you access?*
- *Which folders allow you to create files?*
- *Does the observed behavior align with the permissions set earlier?*

<p>
<img src="https://imgur.com/XSzUEaX.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://imgur.com/e6uUZTk.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://imgur.com/Yz0ZnC2.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
