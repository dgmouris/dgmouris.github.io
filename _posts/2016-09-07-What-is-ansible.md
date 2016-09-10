---
layout: post
title:	"What is Ansible?"
date:	 2016-09-07
desc: "My First Post"
keywords: "Ansible, cloud, what is ansible, automation"
categories: [ansible]
tags: [First post,welcome]
icon: icon-cloud
---

### What is Ansible?

Ansible is a platform for automation, configuration management as well deployments of your web/cloud infrastructure. Ansible uses playbooks to deploy manage and configure anything that has an ssh connection.

Configuration management of your infrastructure is one of the most essential parts of DevOps to ensure continous delivery of your code. Ansible makes configuration management a lot easier, since you can keep all of your configuration for an envrionment in a single git repository.

### What are the benefits of Ansible?

One of the greatest benefits of ansible is that it can be responsible for everything that is related to your servers, but gives you the flexibility to do manual configuration later on. As well it does not depend on a single "Master Server" because it sends the same configuration to all servers.

Another great benefit from Ansible is that the barrier to entry is fairly low. If you've read a yml file before or if you haven't it's pretty easy to follow (if you know xml/html/json it should be pretty easy to follow)

{% highlight yml%}
---
- name: dan
	cats:
		- ghost
		- gambit
- name: amber
	cats:
	- mocha
	- topaz
{% endhighlight%}


### What are other tools in the Ansible space?
This list includes deployment configuration management tools like Ansible:
	- Jenkins
	- Salt
	- Puppet
	- Chef
	- Fabric

These tools are in the same space as Ansible but can also be used in conjunction with these tools, and many times it is.

### How does Ansible differ to these tools?
Puppet and Chef.
	- Puppet and Chef contain a centralized master/controller server setup that is responsbile for the deployments. Since Ansible only uses ssh, any server/machine at any time can assume that role.
	- Ansible uses the "push" method for configuration management. There are two benefits to this.
		1. Doesn't need any client-side installs.
		2. Again, does not need a mater server.
	- Ansible uses a top to bottom approach (executes sequentially), unlike puppet which does not execute commands as they appear in the manifest.
	- Syntax is based on Yaml, unlike puppet that uses custom DSL. This make configurations easier to read.
	- Ansible is built with Python, where chef and puppet 
	- Chef breaks it's deployment process into two steps. The first is the compilation phase and the second is execution. By default state is stored during compilation phase unless the "lazy" option is used.
