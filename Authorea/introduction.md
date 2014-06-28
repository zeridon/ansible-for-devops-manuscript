# Introduction

## In the beginning, there were sysadmins

Deploying and managing servers reliably and efficiently has been a challenge since the beginning of networked computing. Historically, system administrators---walled off organizationally from the developers and users who interacted with the systems they administered---have managed servers by hand, installing software, changing configurations, and administering services on individual servers.

As data centers grew, and as the applications they hosted became more complex, administrators realized they couldn't scale their manual systems management as fast as the applications they were enabling. Thus server provisioning and configuration management tools began to flourish.

Server virtualization brought large-scale infrastructure management to the fore, and the number of servers managed by one admin, or a small team of admins, has grown by an order of magnitude. Instead of deploying, patching, and destroying every server by hand, admins are expected to be able to bring up new servers either automatically, or with minimal intervention. Many large-scale IT deployments involve hundreds or thousands of servers, and in many of the largest environments, server provisioning, configuration, and decommissioning is entirely automated.

## Modern infrastructure management

As the systems that run applications become an ever more complex and integral part of the software they run, application developers themselves have begun to integrate their work more fully with operations personnel, and in many companies, development and operations work is almost fully integrated. Indeed, this can be a requirement for modern test-driven application design, as well as continuous integration.

As a software developer by trade, and a sysadmin by necessity, I have seen the power in uniting development and operations---more commonly referred to nowadays as DevOps. When developers begin to think of infrastructure as *part of their application*, stability and performance become normative. When sysadmins (most of whom have intermediate to advanced knowledge of the applications and languages being used on servers they manage) work tightly with developers, development velocity is improved, and more time can be spent doing 'fun' activities like performance tuning, experimentation, and getting things done (and less time is spent putting out fires).

W> *DevOps* is a loaded word; some people argue using the word to identify both the *movement* of development and operations becoming integrated, and the *personnel* who skew slightly more towards the system administration side of the equation, dilutes the word's meaning. I think the word has simply come to be a rallying cry for the employees who are dragging their startups, small businesses, and enterprises into a new era of infrastructure growth and stability. I'm not too concerned that the term has become more of a catch-all for modern infrastructure management. Spend less time arguing over the definition of the word, and more time making it mean something *to you*.

## Ansible and Ansible, Inc.

Ansible was released in 2012 by Michael DeHaan ([@laserllama](https://twitter.com/laserllama) on Twitter), a developer who has been working with configuration management and infrastructure orchestration in one form or another for many years. Through his work with Puppet Labs and RedHat (where he worked on [Cobbler](http://www.cobblerd.org/), a configuration management tool and [Func](https://fedorahosted.org/func/), a tool for communicating commands to remote servers), and [some other projects](http://blog.ansibleworks.com/2013/12/08/the-origins-of-ansible/), he experienced the trials and tribulations of many different organizations and individual sysadmins on their quest to simplify and automate their infrastructure management operations.

Additionally, Michael found [many shops were using separate tools](http://highscalability.com/blog/2012/4/18/ansible-a-simple-model-driven-configuration-management-and-c.html) for configuration management (Puppet, Chef, cfengine), server deployment (Capistrano, Fabric), and ad-hoc task execution (Func, plain SSH), and wanted to see if there was a better way. Ansible wraps up all three of these features into one tool, and does it in a way that's actually *simpler* and more consistent than any of the other task-specific tools!

Ansible aims to be:

  1. **Clear** - Ansible uses a simple syntax (YAML) and is easy for anyone (developers, sysadmins, managers) to understand. APIs are simple and sensible.
  2. **Fast** - Fast to learn, fast to set up---especially considering you don't need to install extra agents or daemons on all your servers!
  3. **Complete** - Ansible does three things in one, and does them very well. Ansible's 'batteries included' approach means you have everything you need in one complete package.
  4. **Efficient** - No extra software on your servers means more resources for your applications. Also, since Ansible modules work via JSON, you can easily extend Ansible with modules in a programming language you already know.
  5. **Secure** - Ansible uses SSH, and requires no extra open ports or potentially-vulnerable daemons on your servers.

Ansible also has a lighter side that gives the project a little personality. As an example, Ansible's major releases are named after Van Halen songs (e.g. 1.4 was named after 1980's "Could This Be Magic", and 1.5 after 1986's "Love Walks In"). Additionally, Ansible will use `cowsay`, if installed, to wrap output in an ASCII cow's speech bubble (this behavior can be disabled in Ansible's configuration).

[Ansible, Inc.](http://www.ansible.com/) was founded by Saïd Ziouani ([@SaidZiouani](https://twitter.com/SaidZiouani) on Twitter) and Michael DeHaan, and oversees core Ansible development and provides support (such as [Ansible Guru](http://www.ansible.com/guru)) and extra tooling (such as [Ansible Tower](http://www.ansible.com/tower)) to organizations using Ansible. Hundreds of individual developers have contributed patches to Ansible, and Ansible is the most starred infrastructure management tool on GitHub (with over 6,000 stars as of this writing). Ansible, Inc. has proven itself to be a good steward and promoter of Ansible so far, and I see no indication of this changing in the future.

## Other resources

We'll explore all aspects of using Ansible to provision and manage your infrastructure in this book, but there's no substitute for the wealth of documentation and community interaction that make Ansible great. Check out the links below to find out more about Ansible and discover the community:

  - [Ansible Documentation](http://docs.ansible.com/) - Covers all Ansible options in depth. There are few open source projects with documentation as clear and thorough.
  - [Ansible Mailing List](https://groups.google.com/forum/#!forum/ansible-project) - Discuss Ansible and submit questions with Ansible's community via this Google group.
  - [Ansible on GitHub](https://github.com/ansible/ansible) - The official Ansible code repository, where the magic happens.
  - [Ansible Example Playbooks on GitHub](https://github.com/ansible/ansible-examples) - Many examples for common server configurations.
  - [Getting Started with Ansible](http://www.ansible.com/get-started) - A simple guide to Ansible's community and resources.
  - [Ansible Blog](http://blog.ansibleworks.com/)
  - [Ansible Weekly](http://devopsu.com/newsletters/ansible-weekly-newsletter.html) - A newsletter about Ansible, including notable cowsay quotes!