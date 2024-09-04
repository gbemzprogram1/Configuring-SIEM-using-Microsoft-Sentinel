# Configuring-SIEM-using-Microsoft-Sentinel
This is done using a free account

You can create a free account to access the Azure Portal using this link-https://azure.microsoft.com/en-ca/get-started/azure-portal

For this project i will be deploying linux virtual machines, To launch virtual machines there are various steps that come into play such as choosing a subscription, a resource group an availablity zone etc., I will give you a walkthrough of all the steps along the way.

Let's first start with creating a Security group, this is what is used to manage user's permission to azure resources as i want users added to the group to automatically be able to have access to the created virtual machines.

On the home page of the Azure portal search for Microsoft Entra ID

<img width="1440" alt="Screenshot 2024-09-04 at 1 18 03 AM" src="https://github.com/user-attachments/assets/bd8ae4c8-61c9-4569-84fb-8be6c0e6ccf4">


Navigate to Manage Menu on the left side of the screen and from the drop down select "Groups"

<img width="1440" alt="Screenshot 2024-09-04 at 1 19 46 AM" src="https://github.com/user-attachments/assets/f0d3109d-bb90-48df-b125-0817526bf60d">


Select New Group at the top of the screen

<img width="1440" alt="Screenshot 2024-09-04 at 1 21 09 AM" src="https://github.com/user-attachments/assets/8c465509-7190-4e73-a119-ae9e95864d0b">






