## Hardware and operating system used in the making of the assignment
  - Computer: Lenovo Yoga Slim 7 pro
  - OS: Microsoft Windows 11 Home
  - Oracle virtual Box with Debian 13-trixie

## x) Read & Summarize
  ### SSH public key - Login wihtout password
  - SSH is a solution for securily logging into servers, and when used correctly, it can make your server more secure
  - SSH enables login without password when you copy the public key to a hosts you can already log in
  ### Hello Ansible
  - Ansible is a open-source automation tool written in Python. It's mainly used for configuration management, application deployment, and infrastructure provisioning.
  - Some of the files and directories used and what they contain:
     - 'hosts.ini', contains all the computers
     - 'site.yml', tells what computers get which roles
     - 'roles' directory has all the configured things we want to do on computers we have selected

## a) Sshecrets. Install SSH-daemon and test it by logging in with SSH
I started by updating the packets and then downloading ssh with the command `sudo apt-get -y install ssh`. After that I made the daemon start on boot and started it with the command `sudo systemctl enable --now ssh`. Then I had to test it that it worked and on the screen shot belowe you can see that i didn´t run into any problems. For now.

<img width="944" height="394" alt="image" src="https://github.com/user-attachments/assets/f6edfb6a-8346-4630-bfb7-4ebe77ab4bc8" />

## b) Pubkey. Automate SSH login with the public key.
As you saw on the previous step I had to insert password when connecting to localhost via SSH. It was time to change that. All I had to do was generate a key pair and copy the pubkey to the host I connected to before. The pubkey is added to .ssh/authorized_keys file on the localhost. Commands used are highlighted with pink.


<img width="1199" height="878" alt="Screenshot 2026-03-31 150844" src="https://github.com/user-attachments/assets/d26c221f-029a-4014-b770-e4181ff86680" />


## Hello Ansible. Make hello world with ansible and try it over SSH.



## Sources:
https://medium.com/@marouanetester/ansible-what-it-is-and-why-you-need-it-853f2a5f5f17
