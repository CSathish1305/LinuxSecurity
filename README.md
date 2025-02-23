# LinuxSecurity
Performing Linux Security Tasks in Redhat Linux
# 1.Remove Unneeded Functionality
- A ) Use package management tools like apt or yum to list all installed packages. Review the list and remove any packages that are not necessary for your server’s roles or functions.
  ![Screenshot 2025-02-21 094232](https://github.com/user-attachments/assets/e02a2ebf-a017-4677-baf0-1cd4cc74d037)
  ![Screenshot 2025-02-21 094503](https://github.com/user-attachments/assets/d70e9a14-9c01-4db4-b024-6468c07b7c98)
  ![Screenshot 2025-02-21 094547](https://github.com/user-attachments/assets/6f781df8-649e-4a31-b4da-36fb557ceb7f)
  ![Screenshot 2025-02-21 094623](https://github.com/user-attachments/assets/66d15b3a-2ed8-4ad6-8c4b-95a4d73fda12)
- B ) Check running services with commands like systemctl list-units –type=service. Disable services that are not needed for your server’s operation using appropriate commands (systemctl disable <service>).
  ![Screenshot 2025-02-21 095836](https://github.com/user-attachments/assets/eef10501-0dc1-4efe-85db-74ec19f1c5ec)
  ![Screenshot 2025-02-21 100202](https://github.com/user-attachments/assets/0fec1ae9-b6d6-4495-93c6-a055f3f04a54)
- C ) Restrict the loading of kernel modules by blacklisting those that are unnecessary for your server’s functionality.This can be achieved by adding entries to files in /etc/modprobe.d/
  ![Screenshot 2025-02-21 104940](https://github.com/user-attachments/assets/fd44095d-0219-42f8-9218-db3be2150ae8)
  ![Screenshot 2025-02-21 105056](https://github.com/user-attachments/assets/ee1eb1b8-a28a-437d-a034-39d6052adbc6)
  ![Screenshot 2025-02-21 105129](https://github.com/user-attachments/assets/932b195d-4f6a-4966-be07-745f21a9e4fc)
- Then Restart the System to load the Configurations
- D ) Ensure that boot loaders like GRUB2 are password-protected and configured securely to prevent unauthorized modifications during the boot process.(Make sure GRUB2 is installed on your system. If it's not, you can install it using your package manager.)
  ![Screenshot 2025-02-22 161321](https://github.com/user-attachments/assets/23e19a4d-d4f7-4b0b-ac87-47d4f32bb8a7)
  ![Screenshot 2025-02-22 161339](https://github.com/user-attachments/assets/532233ac-6929-44b8-b5fe-de7613b9d35d)
- Use grub2-mkpasswd-pbkdf2 to create a hashed password.
  ![Screenshot 2025-02-22 161712](https://github.com/user-attachments/assets/5057626f-7682-442f-a0a2-5b83fba8fe96)
- Edit GRUB Configuration: Open the GRUB configuration file for editing.
  ![Screenshot 2025-02-22 162536](https://github.com/user-attachments/assets/806dd9bd-9418-4880-b302-742b9489e593)
- Reboot the system to load the configurations
# 2.Minimize Open Ports and Other Network Vulnerabilities 
- Use tools like nmap to identify all open ports on the server. Review the list of open ports and determine which services are associated with each port.
  ![image](https://github.com/user-attachments/assets/275d6370-4a3c-4cf1-b160-586de13256ce)
- For any service that is not required, disable the service or configure it to stop listening on the network. This can usually be done within the service’s configuration file or by stopping and disabling the service using systemd commands (systemctl stop <service> and systemctl disable <service>).
  ![image](https://github.com/user-attachments/assets/968fc30b-ca35-4b70-a8c3-90f84af9bb5c)


  


