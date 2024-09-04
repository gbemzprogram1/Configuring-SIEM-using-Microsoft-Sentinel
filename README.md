# Configuring-SIEM-using-Microsoft-Sentinel
This is done using a free account

You can create a free account to access the Azure Portal using this link-https://azure.microsoft.com/en-ca/get-started/azure-portal


As this account has been created you are automatically granted the owner role, which means you can access all azure resources, there are other roles such as contributor or reader role, for the contributor role you would have access to all azure resources but would be unable to assign roles for role-based access control and for the reader role as the name implies you would only be able to  view all resources within the scope that access was granted to you, same for the contributor, but for this the role that i would be granting is the Virtual Mchine User Login role to allow those with this role view virtual machines and login as a regular user

For this project i will be deploying linux virtual machines, To launch virtual machines there are various steps that come into play such as choosing a subscription, a resource group an availablity zone etc., I will give you a walkthrough of all the steps along the way.

Let's first start with creating a Security group, this is what is used to manage user's permission to azure resources as i want users added to the group to automatically be able to have access to the created virtual machines.

On the home page of the Azure portal search for Microsoft Entra ID.

<img width="1440" alt="Screenshot 2024-09-04 at 1 18 03 AM" src="https://github.com/user-attachments/assets/bd8ae4c8-61c9-4569-84fb-8be6c0e6ccf4">


Navigate to Manage Menu on the left side of the screen and from the drop down select "Groups".

<img width="1440" alt="Screenshot 2024-09-04 at 1 19 46 AM" src="https://github.com/user-attachments/assets/f0d3109d-bb90-48df-b125-0817526bf60d">


Select New Group at the top of the screen.

<img width="1440" alt="Screenshot 2024-09-04 at 1 21 09 AM" src="https://github.com/user-attachments/assets/8c465509-7190-4e73-a119-ae9e95864d0b">


For Group Type please select Security as this group is for access to Azure resources not for collaboration between users with Microsoft 365, for the Group name you could call it Virtual Machine Login Users,, for the description you could use allows users to log in to virtual machines, for the owners and members you can leave that blank, select create at the bottom of the screen. Owners of groups have full permissions to delete the group, add users, remove users, elevate other users to owners as well, select create at the bottom of the screen.

<img width="1440" alt="Screenshot 2024-09-04 at 1 40 11 AM" src="https://github.com/user-attachments/assets/bbfca510-7b64-43a7-a02a-8c16d21e8e45">

You would recieve a notification with a green tick mark once the group has been successfully created, please resfresh the page and the newly created group should appear on the screen.

<img width="1440" alt="Screenshot 2024-09-04 at 1 44 34 AM" src="https://github.com/user-attachments/assets/cb2aab85-7ddf-4e9a-81d2-c450e1722830">









