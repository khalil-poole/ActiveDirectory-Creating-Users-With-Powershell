# ActiveDirectory-Creating-Users-With-Powershell
In this section, we're going to create users with Windows Powershell to setup Group Policy for a fictional organization.

***Environments and Utilities Used***

Microsoft Azure

Virtual Machines

Remote Desktop Connection

Active Directory

Windows Powershell

***Operating Systems Used***

Windows Server

Windows 10

First, turn on the Azure VMs if they are not on already. Then log into client-1 as "mydomain.com\jane_admin".

Right click on the start menu (the bottom left of the screen) and click "System" and then click "Remote Desktop" upon the new pop-up window opening. You may have to maximize the VM window to see it if you haven't done so already.

<img width="1910" height="732" alt="image" src="https://github.com/user-attachments/assets/c7d1d4ae-fa82-4a23-a299-180b929925f2" />

Next, scroll down until you see "Select users that can remotely access this PC" and click it.

<img width="994" height="900" alt="image" src="https://github.com/user-attachments/assets/8cc704d7-7f02-492f-a249-ac37f41ff3fb" />

In the next window, "Remote Desktop Users" click "Add".

So inside the new window that says "Select Users or Groups" inside the white text area we are going to type "domain users" exactly like that with no extra spaces after, and then click "Check Names" followed by clicking "Ok" and "Ok" again. Essentially what this means is that all users within the organization now has access within the domain without having an administrative role for Group Policy (more on that later :) ).

<img width="629" height="316" alt="image" src="https://github.com/user-attachments/assets/f6e39e78-00d9-4520-87f0-6bf70ab1d79f" />


**Create a bunch of additional users with Powershell in Active Directory**

Begin by logging in to the domain controller VM as jane_admin. In the bottom search bar, type in "Powershell_ise" and open as an administrator by right clicking on the icon and then click "Yes".


<img width="1035" height="845" alt="image" src="https://github.com/user-attachments/assets/da02182e-e20d-485d-9ee4-8915f4116d57" />


Next, we'll create a new File and paste the contents of this -> [script](https://github.com/joshmadakor1/AD_PS/blob/master/Generate-Names-Create-Users.ps1) <- into it.

After clicking the link to the script, we are going to copy the contents and paste it inside Powershell ISE. Following the screenshots below will help moreso than trying to explain it by text.

<img width="1902" height="762" alt="image" src="https://github.com/user-attachments/assets/1e173e62-c4b3-4d86-ad92-16cdd79c3c47" />

<img width="1039" height="804" alt="image" src="https://github.com/user-attachments/assets/8617ae12-7605-48c4-93df-95b2be70e5f4" />

Paste the contents from the link into the white text area as shown below

<img width="1085" height="829" alt="image" src="https://github.com/user-attachments/assets/99849466-8a00-4e47-92a3-aa9d616eaa33" />

*Save the file just in case something goes haywire.*

Time to run the script!

<img width="1083" height="825" alt="image" src="https://github.com/user-attachments/assets/a01781b2-5c70-4379-9211-6596f3975d5c" />

After about 5 minutes, feel free to stop the script as shown below.

<img width="1088" height="884" alt="image" src="https://github.com/user-attachments/assets/137833ee-0a19-4607-b3ce-efa197ae169c" />


After stopping the script, we are going to go back into Active Directory, observe the change we made inside of the "_EMPLOYEES" Organizational Unit (OU), and then attempt to login as one of the users inside of the client VM.

*Note --- All users will have a password of "Password1" no quotations*

First, let's go to the Start Menu, the go to "Windows Administrative Tools", then scroll down and click on "Active Directory Users and Computers". Expand "mydomain.com" and then click "_EMPLOYEES" and you should see a bunch of users that were generated with the script that we just used.


<img width="942" height="656" alt="image" src="https://github.com/user-attachments/assets/577e774c-6f00-40f1-b2fb-6f75f607063f" />


<img width="510" height="677" alt="image" src="https://github.com/user-attachments/assets/8b142002-e884-4498-a958-a96d435b6740" />

Notice when you double click on a user and go to the "Member Of" tab, they are all a part of the Users domain OU.

Pick any user or use the one I selected in the screenshot demonstration, write down the first name and last name, let's attempt login to the client vm with the user you selected.


Login: mydomain.com\<firstname.lastname>

Password: Password1

The next screenshot just observe only, but as you can see, the user has successfully logged in with Jane Admin also having access to the user shown below

<img width="1408" height="745" alt="image" src="https://github.com/user-attachments/assets/efe01d10-8e2a-4751-b68d-16e403c358fa" />


This section is now complete, and now it's time to tackle the final part of this Active Directory lab, [Group Policy](https://github.com/khalil-poole/Group-Policy-And-Managing-Accounts)







