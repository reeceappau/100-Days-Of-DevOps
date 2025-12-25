# Day 2: Temporary User Setup with Expiry
## Task

As part of the temporary assignment to the  `Nautilus`  project, a developer named  `ammar`  requires access for a limited duration. To ensure smooth access management, a temporary user account with an expiry date is needed. Here's what you need to do:  
Create a user named  `ammar`  on  `App Server 1`  in Stratos Datacenter. Set the expiry date to  `2023-12-07`, ensuring the user is created in lowercase as per standard protocol.

## Solution

```bash
# Create user with expiry date sudo  
useradd -e 2023-12-07 ammar 

#Verify user created
id ammar

# Verify user expiry 
sudo chage -l ammar 
```

**Explanation:** 
-  `useradd` creates a new user account 
-  `-e 2023-12-07` sets account expiry date (YYYY-MM-DD format) 
-  `chage -l` displays account aging information including expiry 

**Key Learnings** 
- Account expiry vs password expiry are different:
	- Account expiry (`-e`): User completely locked out 
	- Password expiry (`-f`): User must change password 
- Date format matters: YYYY-MM-DD is the standard format
