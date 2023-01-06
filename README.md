# Network-File-Shares-and-Permissions
- Sharing out resources over the network
- Creating file shares to allow read,write, or deny access to individual users or groups

# Overview
- Talk about files shares (What, when, where, why, and how) 
- Create and test some files shares
- Talk about security groups (windows and active directory)
- Create and test some security groups
- Clean up resources!

# Definitions 
- file shares: Folder on desktop that is shared to the network. You can assign permissions by individual, but you'll usually see them assigned by group 

- Internet defintion of file share: the practice of or ability to transmit files from one computer to another over a network or the internet.

# Create some sample file shares with various permissions

![file share part 1](https://user-images.githubusercontent.com/58159183/210940933-ae5d0598-7aa0-48e2-be33-2b493799587e.gif)

- Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin)
- Connect/log into Client-1 as a normal user (mydomain\<someuser>)

![file share part 2](https://user-images.githubusercontent.com/58159183/210942036-dbad594c-17c7-425f-94a8-41fd697580b4.gif)

- On DC-1, on the C:\ drive, create 4 folders: “read-access”, “write-access”, “no-access”, “accounting”
- Set the following permissions (share the folder) for the “Domain Users” group:
- Folder: “read-access”, Group: “Domain Users”, Permission: “Read”
- Folder: “write-access”,  Group: “Domain Users”, Permissions: “Read/Write”
- Folder: “no-access”, Group: “Domain Admins”, “Permissions: “Read/Write”
- (Skip accounting for now)

# Attempt to access file shares as a normal user

![file share part 3](https://user-images.githubusercontent.com/58159183/210943356-f3b8ab86-47e6-4093-83af-0e06f0f81202.gif)

- On Client-1, navigate to the shared folder (start, run, \\dc-1)
- Try to access the folders you just created. Which folders can you access? Which folders can you create stuff in? Does it make sense?

# Create an “ACCOUNTANTS” Security Group, assign permissions, an test access

![file share part 4](https://user-images.githubusercontent.com/58159183/210944333-d8d0fd05-61ce-47d8-a7a1-043687d7a986.gif)


- Go back to DC-1, in Active Directory, create a security group called “ACCOUNTANTS”
- On the “accounting” folder you created earlier, set the following permissions:
- Folder: “accounting”, Group: “ACCOUNTANTS”, Permissions: “Read/Write”

![file share part 5](https://user-images.githubusercontent.com/58159183/210945706-26f6936b-202a-40f6-8723-2e31630ce1a6.gif)

- On Client-1, as  <someuser>, try to access the accountants folder. It should fail. 
- Log out of Client-1 as  <someuser>
- On DC-1, make <someuser> a member of the “ACCOUNTANTS”  Security Group
- Sign back into Client-1 as <someuser> and try to access the “accounting” share in \\DC-1\ - Does it work now?







