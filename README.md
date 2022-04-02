[![CI](https://github.com/de-it-krachten/ansible-role-ufw/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-ufw/actions?query=workflow%3ACI)


# ansible-role-ufw

Installs & configure UFW


Platforms
--------------

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- CentOS 7
- RockyLinux 8
- AlmaLinux 8<sup>1</sup>
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS

Note:
<sup>1</sup> : no automated testing is performed on these platforms

Role Variables
--------------
<pre><code>
# Should ssh be allow
ufw_enable_ssh: true

# name of the ssh rule
ufw_ssh_rule: OpenSSH

# Tun on/off logging
ufw_logging: 'on'
</pre></code>


Example Playbook
----------------

<pre><code>
- name: sample playbook for role 'ufw'
  hosts: all
  vars:
  tasks:
    - name: Include role 'ufw'
      include_role:
        name: ufw
</pre></code>
