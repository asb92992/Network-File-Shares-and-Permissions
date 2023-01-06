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
