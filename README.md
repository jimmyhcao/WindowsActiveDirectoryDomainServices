<h1>Windows Active Directory Domain Services</h1>



<h2>Description</h2>
Windows Active Directory Domain Services (AD DS) is a critical component of many organizations' IT infrastructure, serving as the backbone for user authentication, access control, and group policies. With the increasing sophistication of cyber threats and the growing importance of data security, it is imperative to continuously enhance the cybersecurity posture of AD DS. This project aims to strengthen the security of AD DS to safeguard critical assets and data.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Windows Active Directory</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> 
- <b>Windows RDP Host Machine</b> 
- <b>Windows Server Machine</b> 

<h2>Program walk-through:</h2>
<h3>Creating Organizational Units(OU)</h3>

OUs are logical groupings of an organization's assets and accounts, used to manage these assets together. For example, all the computers in the Marketing department of a company should be grouped together in an organizational unit (OU). This OU might be called GC Users > Marketing. All of the computers in this OU have the same policy, which is set by the Group Policy.

Steps:
<li>Open Active Directory Users and Computers (ADUC) tool
<li>Right-click GOODCORP.NET, go to New, then Organizational Unit.
<li>Name this OU GC Users (short for Good Corp, Inc.)</li>
<br/>
<img src="https://i.imgur.com/HMqGfqD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<i>Create the Marketing sub-organizational unit</i>  <br/>
<li>Right-click GC Users, then click New, then Organizational Unit.
<li>Name this sub-OU Marketing and click OK.</li><br/>
<img src="https://i.imgur.com/OGsj2fO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
This will give us a sub-OU for the Marketing team. This will include the Marketing team users, who will all have hte same policies applied to them <br/>
<br/><img src="https://i.imgur.com/26PTGWh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<h3>Creating Users</h3>
Users are the accounts that people use to log in with. In this section we will create the user <b>Caroline</b> under the <b>Marketing</b> organizational unit we created in the previous section<br />

<br />Steps:
<li>Click to expand the GC Users organizational unit, right-click Marketing, then New > User. The New Object - User window will appear.
<li> Enter in user name Caroline into first name field 
</li>
<br/><img src="https://i.imgur.com/jHBr2As.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<li>The next screen will have fields for setting Caroline's password and a few password settings for sysadmins to set.
<li>After clicking Finish, Double-click on the GC Users > Marketing organizational unit (the folder icon), and check to see if the created user, Caroline, in the right pane.</li><br />
<br /><img src="https://i.imgur.com/wboJhRr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>









<br />
Wait for process to complete (may take some time):  <br/>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />












Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>







<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
