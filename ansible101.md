## Intro:
Configuration management is the process of handling changes to a system in a way that assures integrity over time, typically involving tools and processes that facilitate automation and observability.
"Make sure a system's state matches the state described by a set of proviosning scripts"

## Benefits of using Configuration Management Tool
Same benefits of using IaC - version control, Idempotent behaiovr, sharing scripting, streamline process.
+Configuration management offer a way to control multiple serves from cenralized location.

## Ansible
- Modern-Minimal tool of setting uo and maintaining remote servers, playbooks (scripts) are written in YAML.
- Ansible communicates with nodes using SSH, no need extra installation.
- Before each proviosioning the system keeps the Desired State.
- You can use variables, conditions and loops.
- Ansible collecet info from the managed nodes - *System facts* , the facts can be usedf in a playbook.
- Templates - uses Python templating system, to allow dynamic expressions and access to variables.
- Support for Extensions and Modules 

### Ansible Concepts
#### Control Node
A system where Ansible is installed and set up to connect to the servers, can't be installed on Windows.
#### Managed Nodes
The system you actually control - Must be reachable via SSH, Python >= 2.6 || Python >= 3.5.
Ansible supports a variety of operating systems including Windows servers as managed nodes.
#### Inventory
An inventory file contains a list of the hosts you’ll manage using Ansible. 
Static inventories are usually created as .ini files, 
but you can also use dynamically generated inventories written in any programming language able to return JSON.
#### Tasks
An individual unit of work to execute on managed node, each action is a task, can be one-off action via ad-hoc commands or in the playbook.
#### Playbook
A playbook contains an ordered list of tasks, and a few other directives to indicate which hosts are the target of that automation, whether or not to use a privilege escalation system to run those tasks, and optional sections to define variables or include files. Ansible executes tasks sequentially, and a full playbook execution is called a play. Playbooks are written in YAML format.
#### Handlers
Handlers are used to perform actions on a service. Handlers are typically triggered by tasks, and their execution happens at the end of a play, after all tasks are finished.
It is also possible to force immediate handler execution if that is required by a task.
 #### Roles:
 A role is a set of playbooks and related files organized into a predefined structure that is known by Ansible. Roles facilitate reusing and repurposing playbooks into shareable packages of granular automation for specific goals, such as installing a web server, installing a PHP environment, or setting up a MySQL server.
