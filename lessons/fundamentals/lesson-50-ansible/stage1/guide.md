# **Ansible**

#### **Stage 1: Introduction** #to Devices needed and writing first inventory file


#####What is a control node?

It is any machine/device with ansible installed, prerequisite is that python must be installed on the device as well. Devices that can run ansible include: servers, laptops, desktops. Windows machines cannot be the control node.

```
ansible --version
```
<button type="button" class="btn btn-primary btn-sm" onclick="runSnippetInTab('controller', 0)">Run this snippet</button>
#####What is a managed node?

There are the ‘hosts’ that the control node executes tasks on. Ansible doesn’t need to be installed on these devices.

#####What is an inventory?

It is a file that specifies a list of managed nodes and information such as IP address It is easier to organize hosts, creating and nesting groups so that it is easier to scale.

**Creating inventory file**

1.) First create a file to write in the hosts. The default location ansible looks for your inventory is /etc/ansible/hosts. Navigate to /etc/ansible/ and create the file "hosts".

```
cd /etc/ansible/
touch hosts
```

<button type="button" class="btn btn-primary btn-sm" onclick="runSnippetInTab('controller', 1)">Run this snippet</button>


2.) Edit the inventory file

```
nano hosts
```

<button type="button" class="btn btn-primary btn-sm" onclick="runSnippetInTab('controller', 2)">Run this snippet</button>

```
[targets]
target1 ansible_host=target1 ansible_ssh_pass=antidotepassword
target2 ansible_host=target2 ansible_ssh_pass=antidotepassword
```

<button type="button" class="btn btn-primary btn-sm" onclick="runSnippetInTab('controller', 3)">Run this snippet</button>

`[targets]`

Defines a group which can be refrenced when running an ad-hoc command or within a playbook.  In the next stages we will explore these concepts.

`target1 ansible_host=target1 ansible_ssh_pass=antidotepassword`

This line defines a target called "target1" with a host of "target1".  If you wish to use an IP address here send a ping command to target1 to get it's real IP address.  Finially we define the password ansible needs to control the device.

Now our inventory is setup we can move onto learning about modules and how to use them.
