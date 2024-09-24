# Ansible

## Introduction
Ansible is an open-source automation tool used for configuration management, application deployment, and task automation. It uses a simple, human-readable language (YAML) to describe automation jobs.

## Basic Syntax
```yaml
# Example of an Ansible playbook
- name: Install and start Apache
  hosts: webservers
  become: yes
  tasks:
    - name: Ensure Apache is installed
      apt:
        name: apache2
        state: present

    - name: Ensure Apache is running
      service:
        name: apache2
        state: started
```

## Common Use Cases
- Configuration management
- Application deployment
- Task automation
- Orchestration

## Advanced Features
- **Roles**: Organize playbooks into reusable components.
- **Vault**: Encrypt sensitive data.
- **Dynamic Inventory**: Generate inventory dynamically from various sources.
- **Modules**: Extend Ansible's functionality with custom modules.

## Code Snippets
### Using Roles
```yaml
# Directory structure
roles/
  common/
    tasks/
      main.yml
  webservers/
    tasks/
      main.yml

# Playbook using roles
- name: Configure webservers
  hosts: webservers
  roles:
    - common
    - webservers
```

### Using Vault
```bash
# Encrypt a file
ansible-vault encrypt secrets.yml

# Decrypt a file
ansible-vault decrypt secrets.yml

# Edit an encrypted file
ansible-vault edit secrets.yml
```

## Tips & Best Practices
- **Idempotency**: Ensure tasks are idempotent to avoid unintended changes.
- **Modular Playbooks**: Use roles and includes to keep playbooks modular and maintainable.
- **Version Control**: Store playbooks in version control systems like Git.
- **Testing**: Test playbooks in a staging environment before applying to production.

## External Resources
- [Ansible Official Documentation](https://docs.ansible.com/)
- [Ansible Galaxy](https://galaxy.ansible.com/)
- [Ansible Best Practices](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html)