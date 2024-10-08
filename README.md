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

Now let's gp back to th ehome page and select the plus sign thst says crreate a resource as we are about to go through thr steps involved in launhing a virtual machine.

<img width="1440" alt="Screenshot 2024-09-04 at 1 51 11 AM" src="https://github.com/user-attachments/assets/0cece361-54eb-42b5-8002-1f8a39f84728">

Select Create under the virtual machine tab to get started

<img width="1440" alt="Screenshot 2024-09-04 at 1 54 55 AM" src="https://github.com/user-attachments/assets/7a7e6853-9de5-4108-83cf-b13f1d25d377">

The Subscription being used here is the Azure for Students which offers free credits so that i do not have to spend money for this, subcriptions are used for billing, a resource group is a collection of resources, like a little family as an entity, if the resource group is deleted all the resources in the resource group would be deleted as well, i will be creating a new resource group and choosing canada central for my region, I'll also only be choosing no infrazstructure redudancy required for this, availability zones are seperate physical locations, Security type would be Trusted Launch virtual machines ans the image being used here would be Ubuntu Pro 24.04 LTS -x64 Gen2

<img width="1440" alt="Screenshot 2024-09-04 at 2 12 10 AM" src="https://github.com/user-attachments/assets/4c8a7912-3dab-4254-a654-8e6086a86692">

Select the size of the Virtual machine you would like to use, i will be choosing ssh public key for the Authentication Type, in general try to avoid using the default of anything like passwords and etc

<img width="1440" alt="Screenshot 2024-09-04 at 2 25 41 AM" src="https://github.com/user-attachments/assets/87291e0c-b9a3-462e-8408-a6c85bd2b0a7">


You would have to name the key pair, for the inbound port rules i will be choosing ssh since i plan to connect to the vm using SSH.

<img width="1440" alt="Screenshot 2024-09-04 at 2 28 09 AM" src="https://github.com/user-attachments/assets/91448548-e739-4f59-8c1a-ac82c67068e3">

<img width="1440" alt="Screenshot 2024-09-04 at 2 33 35 AM" src="https://github.com/user-attachments/assets/a8fcda11-9d84-4ca9-82fb-1f45f3701013">



<img width="1440" alt="Screenshot 2024-09-04 at 2 36 47 AM" src="https://github.com/user-attachments/assets/c8009a89-e4a4-47a9-a215-90a3da8abb7b">


<img width="1440" alt="Screenshot 2024-09-04 at 2 43 57 AM" src="https://github.com/user-attachments/assets/975bd271-d5fc-4b35-a463-c7cce7dc306a">

<img width="1440" alt="Screenshot 2024-09-04 at 2 48 03 AM" src="https://github.com/user-attachments/assets/dbc108ed-e8cc-447b-88f9-dd24398b49ef">

<img width="1440" alt="Screenshot 2024-09-04 at 2 51 28 AM" src="https://github.com/user-attachments/assets/3fa8677c-7f32-49e6-9c72-51c594ef3dca">

<img width="1440" alt="Screenshot 2024-09-04 at 3 09 59 AM" src="https://github.com/user-attachments/assets/8d96530f-68e9-429b-a9c7-e4ecfdb52d18">

<img width="1440" alt="Screenshot 2024-09-04 at 3 11 26 AM" src="https://github.com/user-attachments/assets/579a4715-49bf-4b7b-9be2-4df125432e6a">

<img width="1440" alt="Screenshot 2024-09-04 at 3 12 24 AM" src="https://github.com/user-attachments/assets/4bca0d19-575b-4000-bcf1-fe5de8770519">

<img width="1440" alt="Screenshot 2024-09-04 at 3 13 03 AM" src="https://github.com/user-attachments/assets/4a9ea426-3bf7-4f63-9686-234686e06862">

<img width="1439" alt="Screenshot 2024-09-04 at 3 13 41 AM" src="https://github.com/user-attachments/assets/797bfe4c-139a-403a-9dd7-fe82793897cf">

<img width="1378" alt="Screenshot 2024-09-04 at 3 14 37 AM" src="https://github.com/user-attachments/assets/3f20b672-b4f2-4fbd-8915-657299f5a48a">

<img width="1440" alt="Screenshot 2024-09-04 at 3 15 44 AM" src="https://github.com/user-attachments/assets/d40fca5e-fd06-47bf-8064-b685fd348626">

<img width="1440" alt="Screenshot 2024-09-04 at 3 16 35 AM" src="https://github.com/user-attachments/assets/7227ddd0-286a-46f3-8a6a-527f396f3158">
<img width="1440" alt="Screenshot 2024-09-04 at 3 17 15 AM" src="https://github.com/user-attachments/assets/33468161-ff66-4085-af8d-16cd0acef6e3">
<img width="1440" alt="Screenshot 2024-09-04 at 3 19 19 AM" src="https://github.com/user-attachments/assets/303ae5d3-07b1-4671-8dec-2095da20a5d2">
<img width="1440" alt="Screenshot 2024-09-04 at 3 20 05 AM" src="https://github.com/user-attachments/assets/cdea2e55-eec1-4f96-81f3-fed611b9cb97">
<img width="1440" alt="Screenshot 2024-09-04 at 3 21 33 AM" src="https://github.com/user-attachments/assets/131ef8ff-d335-43c3-8ccf-f1f566e47d97">

<img width="1440" alt="Screenshot 2024-09-04 at 3 22 26 AM" src="https://github.com/user-attachments/assets/35aa5c0b-97a1-4987-b9fe-ce03278c442e">

































