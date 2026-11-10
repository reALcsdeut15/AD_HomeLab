# Active Directory Key Concepts

Plain language explanations of the core concepts behind this lab.

## What does a Domain Controller do?
A Domain Controller is the central server that holds the master list of all users and computers in the company. It authenticates each user by checking that their password is correct, and it can lock an account after too many failed attempts. It stores each user's group memberships, which decide what files and programs they can access. It also uses Group Policy to apply company rules, like minimum password length and how long a computer can sit idle before it locks.

## Why does Active Directory break when DNS isn't working?
Active Directory needs DNS because DNS knows the address that connects a computer to the Domain Controller. When DNS isn't working, computers can't find the Domain Controller. Users can't sign in with their domain accounts, new computers can't join the domain, and Group Policy rules can't be delivered.

## What's the difference between a forest, a domain, and an OU?
A forest is the entire organization. A domain is a group inside the forest with its own list of users and computers. An OU is like a department within a domain, such as HR, Logistics, or the sales floor. Each OU holds its own users and computers and can have different Group Policy rules. I think of it like my experience as a store manager at Target, where each department had its own team and its own rules within the larger company.
