# ansible-playbooks

### promote-windows-server-to-domain-controller

Promoting a server to an Active Directory Domain Controller (DC) typically involves several steps, including installing the Active Directory Domain Services (AD DS) role, promoting the server to a domain controller, and configuring the domain. You can use Ansible to automate these tasks using a playbook. 

This playbook assumes that you have already configured Ansible to manage Windows hosts (windows_servers), and you have WinRM set up for communication with Windows hosts.

Make sure to replace the following variables with your own values:

domain_name: The name of the Active Directory domain you want to create.
admin_username: The username of an administrative user on the Windows server.
admin_password: The password of the administrative user.
dns_ip_address: The IP address of the DNS server that will be used by the domain controller.
You can execute this playbook using the ansible-playbook command:

ansible-playbook -i inventory_file promote_dc.yml