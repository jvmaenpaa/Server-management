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
I started by updating the packets and then downloading ssh with the command `sudo apt-get -y install ssh`. After that I made the daemon start on boot and started it with the command `sudo systemctl enable --now ssh`. Then I had to test it that it worked and on the screenshot below you can see that i didn´t run into any problems. For now.

<img width="944" height="394" alt="image" src="https://github.com/user-attachments/assets/f6edfb6a-8346-4630-bfb7-4ebe77ab4bc8" />

## b) Pubkey. Automate SSH login with the public key.
As you saw on the previous step I had to insert password when connecting to localhost via SSH. It was time to change that. All I had to do was generate a key pair and copy the pubkey to the host I connected to before. The pubkey is added to .ssh/authorized_keys file on the localhost. Commands used are highlighted with pink.


<img width="1199" height="878" alt="Screenshot 2026-03-31 150844" src="https://github.com/user-attachments/assets/d26c221f-029a-4014-b770-e4181ff86680" />


## Hello Ansible. Make hello world with ansible and try it over SSH.
I first made the directories needed in this part of the assignment with the command `mkdir -p ansible/roles/hello/tasks/`. In the instructions these were made separately in stages but I just thought by making these all first would be easier. Then I made the hosts.ini file and added localhost in it. After these I tested ansible and it seem like it was working (screenshot below).

<img width="1901" height="324" alt="image" src="https://github.com/user-attachments/assets/52d13f5a-9c54-4b4b-92a6-176122f8899b" />

Tero mentioned the warning after the `ansible all -a 'uptime' -i hosts.ini` command. And what it means is that Ansible is using Python interpreter (version 3.13) and this might change if I would install another Python version. So I don´t want to see the warning everytime I run the command so I added it as a variable to the hosts.ini -file. And when I ran the command again the warning was gone and the output much nicer to look at. 

<img width="474" height="141" alt="Screenshot 2026-03-31 152829" src="https://github.com/user-attachments/assets/0cf27cb8-9f1d-48f1-93a6-eed42f9b0d69" />
<img width="627" height="101" alt="Screenshot 2026-03-31 152911" src="https://github.com/user-attachments/assets/c7c4ebad-e1ec-4665-b0bd-0809fba4c48a" />

After I took care of the warning I created the site.yml -file to determine what computers get which roles. Content of the file are below: 

      - hosts: all
          roles:
            - hello




## Sources:
https://medium.com/@marouanetester/ansible-what-it-is-and-why-you-need-it-853f2a5f5f17
