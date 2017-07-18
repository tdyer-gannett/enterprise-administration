# enterprise-ansible
Central Enterprise Ansible Repository

## Playbooks
> Some playbooks have a default group, if one is not hard-coded if one is
> not specified on the command line.  To specify a group, add a variable
> called "group" to the oxtra-vars option to the ansible[-playbook] 
> command line. (-e "group=<value>") The value can be a group name or a
> system name that is in the inventory file>

### Windows Playbooks
 * win-test.yml - Tests access to Windows systems or groups.
 * win-check-updates.yml - Checks for updates to Windows systems.
 * win-update-critsec.yml - Apply Critical and Security updates and reboot
   the servers when needed.
 * win-update-critsec-cron.yml - Cron version of the Critical and Security
   update playbook.
 * win-update-all.yml - Apply ALL AVAILABLE UPDATES and reboot, if necessary.
  
### Linux Playbooks
 * linux-update.yml - Runs the default package manager for the Linux system
   using the ansible package module that auto-detects the system package
   manager.

### Cross-platform Playbooks
   * ping-any.yml - Basic test of ansible connectivity to any system, using 
   the right method for that system.

## Roles

 * ansible-client - Creates the ansible user on all linux systems.  It creates
   the ansible user and group, if needed, copies the authorized_keys and 
   configures sudors for elevated privileges.

## Configuration Files

 * hosts - Default inventory file (override with -i <filename>)

 * ansible.cfg - Local configuration file (overrides /etc/ansible/ansible.cfg)

