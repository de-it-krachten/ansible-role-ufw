[![CI](https://github.com/de-it-krachten/ansible-role-ufw/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-ufw/actions?query=workflow%3ACI)


# ansible-role-ufw

Installs & configure UFW on Debian systems


Platforms
--------------

Supported platforms

- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Debian 10 (Buster)
- Debian 11 (Bullseye)



Role Variables
--------------
<pre><code>


# ufw packages
ufw_packages:
  - ufw

# Should ssh be allow
ufw_enable_ssh: true

# Tun on/off logging
ufw_logging: 'on'
</pre></code>


Example Playbook
----------------

<pre><code>

- name: Converge
  hosts: all
  tasks:

    - name: "Include role 'ansible-role-ufw'"
      include_role:
        name: "ansible-role-ufw"
</pre></code>
