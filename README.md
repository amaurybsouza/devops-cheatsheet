# DevOps Cheat-sheet
This DevOps cheatsheet helps you with the most commonly and used commands, for easy reference like Linux, Ansible, Terraform, Docker, Kubernetes, AWS Cloud, Git, Gitlab and olthers (constantly updating).

Cheat sheets are designed to help users memorize and recall essential information quickly, making them an efficient way to learn and use new technologies. Cheat sheets are available for various technologies, including programming languages, operating systems, databases, network protocols, and software applications. 

## Ansible Ad-Hoc Commands
- Ping all hosts: `ansible all -m ping`
- Run a shell command on all hosts: `ansible all -a "/bin/echo hello"`
- Get information about all hosts: `ansible all -m setup`
- Copy a file to all hosts: `ansible all -m copy -a "src=file.txt dest=/tmp/"`
- Install a package on all hosts: `ansible all -m yum -a "name=nginx state=present"`

## Ansible Playbooks
### Basics
A playbook consists of a list of plays, where each play is a list of tasks to be executed on hosts that match a certain pattern.
Playbooks are written in YAML format. Playbooks are executed with the `ansible-playbook` command.

### Example of Playbook
```yml
---
- name: Example playbook
  hosts: webservers
  become: true
  vars:
    http_port: 80
    max_clients: 200
  tasks:
  - name: Install web server
    yum:
      name: httpd
      state: present
  - name: Copy index.html
    copy:
      src: index.html
      dest: /var/www/html/
    notify:
    - restart apache
  handlers:
    - name: restart apache
      service:
        name: httpd
        state: restarted
```

## Playbook Structure
- name: The name of the playbook.
- hosts: The pattern that matches the hosts to be targeted by this playbook.
- become: If true, Ansible will become root on the remote host before executing tasks.
- vars: Variables that can be used throughout the playbook.
- tasks: A list of tasks to be executed on the targeted hosts.
- handlers: A list of handlers that are notified by tasks.

## Task Structure
- name: The name of the task.
- module: The Ansible module to be used for this task.
- args: The arguments to be passed to the module.

## Handlers
- Handlers are a special type of task that are only executed when notified by other tasks.
- Handlers are defined at the bottom of a playbook, after all tasks have been defined.
- Handlers are notified by tasks using the `notify` keyword.

## Usage
You can update the cheatsheet following the model below. Feel free to add a command in portuguese mode or in english. Make sure you have matched with the model below and apply your commands.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests on commands as appropriate.

## License
[GNU General Public License v3.0](https://github.com/amaurybsouza/devops-cheatsheet/blob/main/LICENSE)
