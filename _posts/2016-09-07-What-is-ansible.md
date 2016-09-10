---
layout: post
title:  "What is Ansible?"
date:   2016-09-07
desc: "Short description of ansible"
keywords: "Ansible, cloud, what is ansible, automation"
categories: [ansible]
tags: [First post,welcome]
icon: icon-python
---

### What is Ansible?

Ansible is a platform for automation, configuration management and deployments of your web/cloud infrastructure. Ansible uses playbooks to deploy, manage and configure anything that has an ssh connection.

Configuration management of your infrastructure is one of the most essential parts of DevOps to ensure continous delivery of your code. Ansible makes configuration management a lot easier, since you can keep all of your configuration for an envrionment in a single git repository.

### What are the benefits of Ansible?

One of the greatest benefits of Ansible is that it can be made responsible for everything that is related to your servers, databases and networking infrastructure. Ansible also gives you the flexibility to do manual configuration later on. It does not depend on a single "Master Server" because it sends the same configuration to all servers.

Another great benefit of Ansible is that the barrier to entry is fairly low. If you've read a yaml file before, or even if you haven't, it's pretty easy to follow. Below is an example of a yaml file. 

{% highlight yaml%}
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


### What are the other tools in the Ansible space?
The following list includes deployment configuration management tools like Ansible:

	- Jenkins
	- Salt
	- Puppet
	- Chef
	- Fabric

Although the tools in the above list compete with Ansible in some respect, they can also be used with Ansible for an infrastructure deployment. Many times Ansible is used in tandem with these tools for a deployment.

### How does Ansible differ to these tools?
Here's how Ansible differs from Puppet and Chef.

	- Puppet and Chef contain a centralized master/controller server setup that is responsbile for the deployments. Since Ansible only uses ssh, any server/machine at any time can assume that role.
	- Ansible uses the "push" method for configuration management. There are two benefits to this.
		1. Does not need any client-side installs.
		2. Does not need a master server.
	- Ansible uses a top to bottom approach (executes sequentially), unlike puppet which does not execute commands as they appear in the manifest.
	- Syntax is based on yaml, unlike Puppet that uses custom DSL. This makes configurations easier to read.
	- Ansible is built with Python, where Chef and Puppet are built with Ruby.
	- Chef breaks it's deployment process into two steps. The first is the compilation phase and the second is execution. By default, state is stored during compilation phase unless the "lazy" option is used.*****

In future posts, I will go into more elaboration about how Ansible differs from Salt, Jenkins and Fabric.

In conclusion this is a short introduction to what ansible is, and what are similar technologies to ansible. I hope you enjoyed my post, if you want to reach out please contact me via email or linkedin.