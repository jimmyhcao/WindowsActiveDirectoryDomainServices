<h1>Windows Active Directory Domain Services</h1>



<h2>Description</h2>
Windows Active Directory Domain Services (AD DS) is a critical component of many organizations' IT infrastructure, serving as the backbone for user authentication, access control, and group policies. With the increasing sophistication of cyber threats and the growing importance of data security, it is imperative to continuously enhance the cybersecurity posture of AD DS. This project aims to deomnstrate how to configure AD DS and complete basic tasks, such as creating Organizational Units, Users, Groups, Group Policies, and Group Policy Objects.<br />
<br />The following steps illustrates configuration of AD DS for the organization GOODCORP

<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Windows Active Directory</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> 
- <b>Windows RDP Host Machine</b> 
- <b>Windows Server Machine</b> 

<h2>Program walk-through:</h2>
<h3>Creating Organizational Units (OU)</h3>

OUs are logical groupings of an organization's assets and accounts, used to manage these assets together. For example, all the computers in the Marketing department of a company should be grouped together in an OU. This OU might be called GC Users > Marketing. All of the computers in this OU have the same policy, which is set by the Group Policy.

Steps:
<li>Open Active Directory Users and Computers (ADUC) tool
<li>Right-click <b>GOODCORP.NET</b>, go to <b>New</b>, then <b>Organizational Unit</b>.
<li>Name this OU <b>GC Users</b> (short for Good Corp, Inc.)</li>
<br/>
<img src="https://i.imgur.com/HMqGfqD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<i>Create the Marketing sub-organizational unit</i>  <br/>
<li>Right-click <b>GC Users</b>, then click <b>New</b>, then <b>Organizational Unit</b>.
<li>Name this sub-OU <b>Marketing</b> and click <b>OK</b>.</li><br/>
<img src="https://i.imgur.com/OGsj2fO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

This will give us a sub-OU for the Marketing team. This will include the Marketing team users, who will all have the same policies applied to them <br/>
<br/><img src="https://i.imgur.com/26PTGWh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

<h3>Creating Users</h3>
Users are the accounts that people use to log in with. In this section we will create the user <b>Caroline</b> under the <b>Marketing</b> OU we created in the previous section<br />

<br />Steps:
<li>Click to expand the <b>GC Users</b> OU, right-click <b>Marketing</b>, then <b>New>User</b>. The New Object - User window will appear.
<li> Enter in user name Caroline into first name field 
</li>
<br/><img src="https://i.imgur.com/jHBr2As.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br /><img src="https://i.imgur.com/rGGTFcb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<li>The next screen will have fields for setting Caroline's password and a few password settings for sysadmins to set.
<li>After clicking Finish, Double-click on the GC Users > Marketing organizational unit (the folder icon), and check to see if the created user, Caroline, appears in the right pane.</li><br />
<br /><img src="https://i.imgur.com/wboJhRr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<h3>Creating Groups </h3>
Groups are collections of objects that require authorization to access resources. Groups are for managing permissions to resources, while organizational units are for linking policies to a set of objects, and for administration purposes. Users can belong to many groups, but are only part of one OU. OUs are organizational tools. <br />
<br />Steps:

<li> Right-click the <b>GC Users > Marketing</b> OU, then go to <b>New</b>, then <b>Group</b>.
<li> Set the group name to <b>Marketing</b>. Leave group scope as Global and group type as Security. <br />
<br /><img src="https://i.imgur.com/Aol8RKm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<br /><li>The new group Marketing will now appear in the GC Users > Marketing OU</li><br />
<br /><img src="https://i.imgur.com/wnvaojV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />

<br /><i> We can add user Caroline to Marketing now</i><br />
<li>Right-click Caroline and go to <b>Add to a group....</b></li><br />



<img src="https://i.imgur.com/PKa5FPe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


<br /><li> In Select Groups window, type "Marketing" in the "Enter the object names to select" field. <br />
<br /><img src="https://i.imgur.com/eYZYUZE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<br /><li>Click <b>"Check Names"</b>--if "Marketing" becomes underlined, the system has found the group<br />
<li>Click <b>OK</b><br />
<br /><img src="https://i.imgur.com/pC4KF4w.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<br />Caroline is now part of the Marketing group in our domain. 
</p>
<br/>
<hr>

<h3>Create New Group Policy Object</h3>
A Group Policy Object (GPO) is a package of policy settings applied to OUs in our domain. GPOs are the cornerstone of policy management in Active Directory. Multiple Group Policies are often combined into one GPO.<br/>
<br/>Steps:
<li>Open <b>Group Policy Management</b> tool
<li>Click on <b>Tools</b> on the top-right of the window
<li>Select the <b>Group Policy Management</b> tool
</li>
<br /><img src="https://i.imgur.com/uuROXxY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<li>In the Group Policy Management window, click on <b>Forest: GOODCORP.NET</b>. Move through <b>GOODCORP.NET</b>. Right click <b>Group Policy Objects</b> and click <b>New</b>
</li>
<br /><img src="https://i.imgur.com/YFLpbNv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />
<li>In the New GPO window, type "No Control Panel" for the name.
<li>Click OK
</li>
<br /><img src="https://i.imgur.com/4Gk5fqp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />

<h3>Add Group Policies to Group Policy Object</h3>

Now that we have created a Group Policy Object, we can not add policies to it to enforce
<li>Right-click the No Control Panel GPO and click Edit. The Group Policy Management Editor window will open. This is where you select the policies to add to your GPO
<li>Navigate to User Configuration, then click Policies >  Administrative Templates > Control Panel. On the right-side pane are default policies you can edit
</li>

<br /><img src="https://i.imgur.com/TcCYp7h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />


<li>Double-click the Prohibit access to Control Panel and PC settings policy. It will open the Prohibit access to Control Panel and PC settings window. This policy will deny access to the Control Panel on Windows systems.
<li>Select Enable, then press Apply > OK.</li>
<br /><img src="https://i.imgur.com/a1JdsIr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />

<h3>Link and Apply the Group Policy Object</h3><br/>
Now that we have created a Group Policy Object and a policy that will deny access to the Control Panel, we can apply the policy to the Sales team OU. <br/>
<br/>Steps:
<li>Navigate to the Group Policy Management window so that we can link the Group Policy Objects to the organizational unit.
<li>With the Group Policy Management window open, move through the following: Group Policy Management > Forest > Domains > GOODCORP.NET > GC Users.
<li>Right-click the Sales Organizational Unit under GC Users and select Link an Existing GPO.... The Select GPO window will appear.
</li>

<br /><img src="https://i.imgur.com/oi0QL7p.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br />

<i>We can now apply the No Control Panel GPO we created</i>
<li>Click No Control Panel 
<li> Click OK
</li>
<br /><img src="https://i.imgur.com/n3wQSwC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />We have now applied the No Control Panel GPO to the GC Users > Sales OU.









<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
