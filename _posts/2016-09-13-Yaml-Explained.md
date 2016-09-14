---
layout: post
title:  "Yaml Explained"
date:   2016-09-13
desc: "How to create and write Yaml files."
keywords: "Ansible, cloud, what is Ansible, automation,Yaml"
categories: [blog]
tags: [First post,welcome,Ansible,Yaml]
icon: icon-python
---

Yaml stands for "Yaml Ain't Markup Language" and is the core of Ansible and writing playbooks. Almost all of Ansible "code" for configuration management is written in Yaml, so I wanted to use this blog post to cover the basics.

In this tutorial I will cover how files are formatted, and how to use lists, key value pairs and other data structures in a Yaml file.

To begin a file in Yaml you need to create a simple text file with three dashes at the top of the page and save it with the ".yml" file extension. Congratulations, you've just created your first Yaml file!

To create a comment in Yaml (where a comment is purely a note for yourself in the code) you need to use the # sign. The below code snippet shows an example of the beginning of a file with a comment in it:

{% highlight yaml%}
--- #Yay my first Yaml file!
{% endhighlight%}

Next, let's create a key value pair in Yaml. A key value pair can be as simple as setting my name, age and the current date as it looks like below:

{% highlight yaml%}
--- #Yay my first Yaml file!
Name: Daniel Mouris
Age: 26
CurrentDate: 13/09/2016
{% endhighlight %}


To create a key with a multiline value, you need to add a "|" (normally named pipe) after the key value. Below is an example of this:

{% highlight yaml %}
--- #Yay my first Yaml file!
Name: Daniel Mouris
Age: 26
CurrentDate: 13/09/2016
Interests: |
  Daniel loves to code and learn new things.
  Daniel also loves his wonderfully cute kittes,
  whose names are Ghost and Gambit.
{% endhighlight %}

Ansible does a great job at detecting Yaml datatypes, but you might want to be specific. Below are examples of datatypes that you can specify in Yaml:


{% highlight yaml %}
--- #Yay my first Yaml file!
integer-example: 97list
string-exmpale: "97"
float-example: 97.0
string-non-ambiguous: !!str 97
float-non-ambiguous: !!float 97
boolean-true: Yes #treats yes like a true statement in code
another-string-example: No sir, the oilers lost today. # treats yes and no like a string
{% endhighlight %}

As you can see, Yaml tries to be as intuitive as possible when evaluating your variable names.

Next we can look at lists. Lists in Yaml are pretty intuitive and are denoted with a "-" before your key value pairs. Below shows an example of multiple lists:

{% highlight yaml %}
---
- name: dan
  cats:
    - ghost
    - gambit
- name: amber
  cats:
    - mocha
    - topaz
{% endhighlight %}

As you can see above, there are dashes in front of _name_ as well as  below _cats_. The dashes in front of _name_ show that everthing with that indentation level will be in that list item. This means that _ghost_ and _gambit_ are _cats_, that are in the same group as _dan_. Ansible uses lists like the above (except with more meaningful values) to perform all of the tasks to create your configuration on your server/database/networking service that you're using.

The final thing that I will be covering in this short tutorial is including files in Yaml. Below shows a Yaml file that includes two files, _a-different-Yaml
-file.yml_ and _another-Yaml-file.yml_.

{% highlight yaml %}
---
- include: a-different-Yaml-file.yml
- include: another-Yaml-file.yml
{% endhighlight %}

Hopefully you have enjoyed my overview of Yaml; the above should give you enough to begin to understand the Yaml formatting. In the future, I will be looking at how to use Yaml variables from other filenames (for when you come across them in Ansible). Now, if you go look at an Ansible Yaml file, you might not be able to understand all of the modules but you should be able to follow along. Hopefully, by keeping up with future blog posts for this tutorial, you'll learn more how Ansible is great and how it will help you.