# ansible-ssh-keyscan
## Description
Simple role to alert on unknown SSH Fingerprint and allow for import to continue Playbook processing.

This role will record the following SSH Host Keys by default (RSA, DSA, ECDSA, ED25519).
Open an issue to support new/additional formats.

# (WIP)

## Usage
playbook.yaml
```
---
- name: Play Name
  hosts: MyHosts
  become: yes
  gather_facts: no
  
  roles:
    - role: notmycloud.ssh_keyscan
      vars:
        global_known_hosts: no  # Determines if it will save in local (~/.ssh) or global (/etc/ssh) known hosts.
        ssh:
          port: 22              # Defaults to port 22
          host: host.ssh.lan    # We will perform a DNS lookup later so the IP address can be added to known hosts.
```

## Dependencies
Requires the `dig` command.
This can be installed with the `dnsutils` package on Debian

## Support
For support, please raise an issue and provide the following items
- Sample task/playbook to replicate your issue
- Resultant file that is created.
- If modifying an existing file, please provide the unmodified version as well.
