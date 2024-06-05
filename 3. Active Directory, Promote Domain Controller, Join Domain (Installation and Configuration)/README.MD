<b>Objective: Install and configure active directory onto our server, promote it to a domatin 
controller and configure the target machines to join our newly created domain.</b>

<b>Active Directory (AD) is a Microsoft service that provides centralized authentication and 
authorization to network resources. It’s used in business environments to simplify user 
management, control access to data, and enforce security policies. AD is a key component of 
the Windows Server operating system, and it’s structured as a hierarchical database that stores 
information about objects on the network, such as user accounts, computers, printers, and 
security policies.</b>

<b>Promoting a server to a domain controller (DC) is a process in Active Directory (AD) where a 
server is elevated to have the authority to manage domain resources, such as user accounts, 
computers, and security policies. This process is essential when setting up a new domain or 
adding a DC to an existing domain to improve redundancy and load balancing.</b>

<b>Joining a domain in Active Directory (AD) is the process of adding a computer to a domain, 
allowing it to be managed centrally and to access resources like shared files, printers, and 
applications that are controlled by the domain. When a computer joins a domain, it becomes a 
member of that domain and is subject to its security policies and administrative controls.</b>

<hr>

<b>First of all we need to set-up static IP adress and we can check our IP in 
Command Prompt by typing in 'ipconfig'</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/6c8af9f6-7d8d-4988-8313-2268c0a53e67)

<hr>

<b>Let's head over to Server Manager which is this icon right here:</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/3cd93dc9-7411-4a1a-a0ad-8fe3ce84f288)

<hr>

<b>On the top right corner we get manage we want to select that and select 'Add Roles and Features'</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/c4e13d56-3562-4ff7-a062-da8f69dd59ba)

<hr>

<b>We will select 'next'</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/1e637f1e-c261-4477-a662-81e75b7da5a1)

<hr>

<b>Make sure it is selected as 'Role-based or feature-based installation' and hit 'next'</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/38ebaa98-817e-408d-9971-4265e9335a3a)

<hr>

<b>If you have multiple servers this is where it will be listed but because we only have one 
this is it so we will just select 'next'</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/ca34dc82-e9c5-428d-b93a-e535bcf81569)

<hr>

<b>We want to select 'Active Directory Domain Services'</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/e280fc79-ff07-4dcc-90b7-733eea5ae786)

<hr>

<b>Click on add features and keep on clicking 'next' until we get install</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/c2c271ed-28c5-4214-a02e-043e3df1a7d3)

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/c9212ae9-7deb-4e22-b014-1e1ecec178ca)

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/b653d532-34f4-4099-b39c-c2425e40a58e)

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/c9462c7d-31a6-4545-835e-bfc5b15373cd)

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/67d3f548-21e5-42b4-bfd1-eae55fafe9ab)

<hr>

<b>After couple of minutes we get the configuration required installation succeeded on ADDC01 so we can go 
ahead and close this out</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/6aaf3828-f77d-4f5d-af84-284a7e27b811)

<hr>

<b>The yeallow flag icon beside manage you want to click on that and you will see promote this server to a 
domain controller go ahead and click on</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/fc5a1f1c-4071-48da-b958-813ccfb4df8c)

<hr>

<b>For this option we want to select 'add a new forest' becouse we are creating a brand new domain
as for a domain name I will call it 'homelab.local' domain name must have a top level domain so
in another words my domain name cannot simply be 'homelab' it must be 'homelab' dot something - and hit 'next'</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/171b7f0e-c6c0-4181-8ed9-934f3def8315)

<hr>

<b>I will everything default and put in a password and click 'next'</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/a201e110-984b-4c0b-a544-717e7ff32b9d)

<hr>

<b>'Next'</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/1e70be55-e844-43bf-8e31-79aaf70a31d3)

<hr>

<b>'Next'</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/0f5fc3da-62a1-4d2a-b02e-6183ca87ecfd)

<hr>

<b>This will be the paths used to store our database file named NTDS.dit and as an FYI attackers 
love to target domain controllers not only becouse it has access to everything but also becouse of 
this file as it contains everything related to active directory including password hashes if you 
do notice any unauthoized activity towords this file you can assume your entire domain is unfortunatelly compromised
 - clicl on 'next' and 'next' again</b>

 ![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/b93c4db7-43aa-4c51-b313-2f42c47155d7)

<hr>

<b>Once the setup finishes veryfing prerequisites we can go ahead and click on 'instal'<b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/e783d9fc-17b5-45cb-b611-c423f9adede3)

<hr>

<b>Once the setup is completed the server will automatycally restart so let's log back in to our server</b>

![image](https://github.com/Oureyelet/Active-Directory-Home-Lab-Project/assets/69697624/f181053e-cb2f-489c-a71e-711339b85402)

<hr>

<b></b>
