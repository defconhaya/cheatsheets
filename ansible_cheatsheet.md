**Ansible Basics:**

1. **Inventory:** Define your target hosts in an inventory file (`inventory.ini` by default).

   ```ini
   [web]
   server1 ansible_host=192.168.1.101
   server2 ansible_host=192.168.1.102
   ```

2. **Ad-Hoc Commands:** Run quick commands on remote hosts.

   ```shell
   ansible <host_group> -i <inventory_file> -m <module> -a "<module_arguments>"
   ```

   Example:
   ```shell
   ansible web -i inventory.ini -m ping
   ```

**Playbooks:**

1. **Create Playbook:** Write Ansible playbooks in YAML format.

   ```yaml
   ---
   - name: My Playbook
     hosts: web
     tasks:
       - name: Ensure Nginx is installed
         apt:
           name: nginx
           state: present
   ```

2. **Run Playbook:**

   ```shell
   ansible-playbook -i <inventory_file> <playbook_file>
   ```

   Example:
   ```shell
   ansible-playbook -i inventory.ini my-playbook.yml
   ```

**Modules:**

1. **Common Modules:**

   - `apt` (for Debian/Ubuntu)
   - `yum` (for Red Hat/CentOS)
   - `file` (manage files and directories)
   - `copy` (copy files to remote hosts)
   - `service` (manage services)
   - `template` (template files)

2. **Example Module Usage:**

   ```yaml
   - name: Ensure Nginx is running
     service:
       name: nginx
       state: started
   ```

**Variables and Facts:**

1. **Define Variables:** In playbooks or inventory.

   ```yaml
   vars:
     app_port: 8080
   ```

2. **Use Variables:**

   ```yaml
   - name: Configure Nginx
     template:
       src: nginx.conf.j2
       dest: /etc/nginx/nginx.conf
   ```

3. **Facts:** Gather system information about remote hosts.

   ```yaml
   - name: Display Host Facts
     debug:
       var: ansible_facts['ansible_hostname']
   ```

**Handlers:**

1. **Define Handlers:** Actions to be taken when notified.

   ```yaml
   handlers:
     - name: Restart Nginx
       service:
         name: nginx
         state: restarted
   ```

2. **Notify Handlers:**

   ```yaml
   - name: Configure Nginx
     template:
       src: nginx.conf.j2
       dest: /etc/nginx/nginx.conf
     notify: Restart Nginx
   ```

**Conditionals:**

1. **Use `when` Keyword:**

   ```yaml
   - name: Ensure Apache is installed (if CentOS)
     yum:
       name: httpd
       state: present
     when: ansible_distribution == "CentOS"
   ```

**Loops:**

1. **Use `with_items` for Iteration:**

   ```yaml
   - name: Ensure required packages are installed
     yum:
       name: "{{ item }}"
       state: present
     with_items:
       - package1
       - package2
   ```

**Roles:**

1. **Create Roles:** Organize playbooks and tasks into reusable roles.

   ```shell
   ansible-galaxy init my-role
   ```

2. **Include Roles in Playbooks:**

   ```yaml
   - name: Include My Role
     hosts: web
     roles:
       - my-role
   ```

This Ansible cheat sheet covers some fundamental concepts and commands. Ansible offers a wide range of modules and features, so make sure to consult the documentation for more in-depth information on specific use cases.