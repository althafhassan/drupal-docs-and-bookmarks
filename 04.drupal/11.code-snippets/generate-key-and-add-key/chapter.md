---
title: 'Generate SSH Key and add key'
---

* Generate Key

ssh-keygen -b 4096

* Will generate file id_rsa and id_rsa.pub (can be modified)

* Copy the public id_rsa.pub content and add to host key

That's it. Next connect to host.

* First connect to hosting agent

eval `ssh-agent -s'  

This should return and agent id.

* If you have multiple key you can just ssh-add the key path like

ssh-add /c/Users/{USERNAME}/.ssh/id_rsa_abc. 

* Now you can ssh to the container. 

ssh {server details}

You can also add extra rules by creating a config file. 

