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

So inside the new window that says "Select Users or Groups" inside the white text area we are going to type "domain users" exactly like that with no extra spaces after, and then click "Check Names" followed by clicking "Ok" and "Ok" again. Essentially what this means is that all users within the organization now has access within the domain.

<img width="629" height="316" alt="image" src="https://github.com/user-attachments/assets/f6e39e78-00d9-4520-87f0-6bf70ab1d79f" />










