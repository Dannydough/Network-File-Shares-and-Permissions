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

**Steps to Create the "ACCOUNTANTS" Security Group, Assign Permissions, and Test Access:**

Log in to DC-1:

- Use your domain admin account (mydomain.com\jane_admin).
- Open Active Directory Users and Computers:

- Press Start → Search for Active Directory Users and Computers → Open it.
- Navigate to the Appropriate OU:

- Expand your domain (e.g., mydomain.com).
- Navigate to the Organizational Unit (OU) where you want to create the group.
- If needed, create a new OU by right-clicking the domain → New → Organizational Unit.
- Create the "ACCOUNTANTS" Security Group:

- Right-click on the target OU → Select New → Group.
- In the New Object - Group dialog:
- Group Name: Enter ACCOUNTANTS.
- Group Scope: Select Global (default scope for most use cases).
- Group Type: Select Security.
- Click OK or Apply to create the group.
- Verify the Group Creation:

- Confirm that the "ACCOUNTANTS" group appears in the OU.
- Right-click the group → Select Properties to review settings.

<p>
<img src="https://imgur.com/DC4yLVA.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

**Steps to Set Permissions on the "Accounting" Folder:**

7.) Navigate to the Folder:

- On DC-1, go to C:\accounting.
- Share the Folder:

- Right-click → Properties → Sharing → Advanced Sharing.
- Check "Share this folder" → Permissions → Add ACCOUNTANTS group → Set to Read/Write.
- Set Security Permissions (Optional):

- Go to the Security tab → Edit → Add ACCOUNTANTS → Grant Read/Write access.
- Test Access:
<p>
<img src="https://imgur.com/1JJdE4d.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

  
<p>
<img src="https://imgur.com/XRicxre.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
- From Client-1, log in as an "ACCOUNTANTS" group user and confirm access.
- Verify users not in the group are denied access.

<p>
<img src="https://imgur.com/5JkbFi5.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

**Steps to Add <someuser> to the "ACCOUNTANTS" Group:**

8.) Log out of <someuser> on Client-1.
- On DC-1, open Active Directory Users and Computers.
- Right-click the "ACCOUNTANTS" group → Properties → Members tab → Add <someuser>.
- Click OK and confirm membership.

<p>
<img src="https://imgur.com/U4TnvSB.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

**Steps to Test Access:**

9.) Sign in to Client-1 as <someuser>.
- Navigate to the shared folder: \\DC-1\accounting.
- Check if you can:
- Access the folder.
- Create, edit, or delete files.
- Confirm if access now works as expected after adding <someuser> to the "ACCOUNTANTS" group.

<p>
<img src="https://imgur.com/CURNt4G.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
