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
I started by updating the packets and then downloading ssh with the command ´sudo apt-get -y install ssh´.


## Sources:
https://medium.com/@marouanetester/ansible-what-it-is-and-why-you-need-it-853f2a5f5f17
