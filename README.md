# ansible-storm
[Ansible](https://www.ansible.com/) playbook for deploying an [Apache Storm](http://storm.apache.org/) cluster

Requires Ansible 2.8 or above.

Use _ssh-add_ to load the SSH key needed to connect to the server, e.g. `ssh-add ~/.ssh/mykey.pem`

Edit the _hosts_ file to specify the IP addresses of the servers then run

```
ansible-playbook -i hosts storm-playbook.yml -u username
```

where _username_ is the name of the user on the remote server. If the servers use different user names, specify them individually in the _hosts_ file.

This installs Zookeeper and Storm running as services. After the command above, you should be able to see the Storm UI on the master node's port 8080.


There is also a crawler-playbook which creates a _stormcrawler_ user on the master node and installs curl, git and maven on the master node. This is useful for checking out the stormcrawler code and run the topologies under it.


Video tutorial
---------------------

[![Video tutorial](https://i.ytimg.com/vi/Wsau0wu7T74/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLARqbyJ04B3jJloroOebIVQxBtvWg)](https://youtu.be/Wsau0wu7T74)
