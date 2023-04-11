[![CI](https://github.com/de-it-krachten/ansible-role-ufw/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-ufw/actions?query=workflow%3ACI)


# ansible-role-ufw

Installs & configure UFW



## Dependencies

#### Roles
None

#### Collections
- community.general

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 36
- Fedora 37

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Should ssh be allow
ufw_enable_ssh: true

# name of the ssh rule
ufw_ssh_rule: OpenSSH

# Tun on/off logging. Other options include low/medium/high/full
ufw_logging: 'on'
</pre></code>


### vars/family-Debian.yml
<pre><code>
# ufw packages
ufw_packages:
  - ufw
  - procps
  - iproute2
  - netbase
</pre></code>

### vars/family-RedHat.yml
<pre><code>
# ufw packages
ufw_packages:
  - ufw

# name of the ssh rule
ufw_ssh_rule: SSH
</pre></code>

### vars/Fedora.yml
<pre><code>
# ufw packages
ufw_packages:
  - ufw
  - procps-ng

# name of the ssh rule
ufw_ssh_rule: SSH
</pre></code>



## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'ufw'
  hosts: all
  become: "yes"
  vars:
    ufw_logging: high
  roles:
    - deitkrachten.showinfo
    - robertdebock.rsyslog
  tasks:
    - name: Include role 'ufw'
      ansible.builtin.include_role:
        name: ufw
</pre></code>
