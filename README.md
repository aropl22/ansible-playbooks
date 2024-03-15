# ansible-playbooks

### cisco-asa5505-delete-user

To delete a user on a Cisco ASA device using Ansible, you can utilize the ios_config module to send the necessary configuration commands to the device.
Replace "user_to_delete" with the username you want to delete.
Make sure you have SSH access enabled on your ASA device and that Ansible is able to connect to it using SSH.

### cisco-asa5505-new-user

To create a new user on a Cisco ASA 5505 device using Ansible, you can utilize the ios_config module to send the necessary configuration commands to the device.
Replace "newuser" with the username you want to create.
Replace "newpassword" with the password for the new user.
Adjust the privilege level (asa_privilege_level) as necessary. The example sets it to 15, which is the maximum privilege level.
Make sure you have SSH access enabled on your ASA device and that Ansible is able to connect to it using SSH.

Also, ensure that you have defined your ASA device(s) under the inventory file hosts and have configured the connection details appropriately in your Ansible configuration file (ansible.cfg).

### windows-promote-server-to-domain-controller

Promoting a server to an Active Directory Domain Controller (DC) typically involves several steps, including installing the Active Directory Domain Services (AD DS) role, promoting the server to a domain controller, and configuring the domain. You can use Ansible to automate these tasks using a playbook. 

This playbook assumes that you have already configured Ansible to manage Windows hosts (windows_servers), and you have WinRM set up for communication with Windows hosts.

Make sure to replace the following variables with your own values:

domain_name: The name of the Active Directory domain you want to create.
admin_username: The username of an administrative user on the Windows server.
admin_password: The password of the administrative user.
dns_ip_address: The IP address of the DNS server that will be used by the domain controller.
You can execute this playbook using the ansible-playbook command:

ansible-playbook -i inventory_file promote_dc.yml

### windows-iis-server

In this playbook:

Replace windows_servers with the group of your Windows servers in your Ansible inventory.
Update the iis_website_name variable with the name you want to assign to your IIS website.
Update the iis_website_path variable with the path where you want to store your website files.
Update the iis_app_pool_name variable with the name you want to assign to your IIS application pool.
Update the iis_app_pool_framework variable with the .NET Framework version you want to use for your application pool.
This playbook performs the following tasks:

Installs the IIS Web Server role.
Creates a directory for the website files.
Creates an application pool with the specified .NET Framework version.
Creates a website that listens on port 80, points to the specified directory, and uses the created application pool.`