# enterprise-ansible
Central Enterprise Ansible Repository

## Playbooks
Some playbooks have a default group, if one is not hard-coded if one is
not specified on the command line.  To specify a group, add a variable
called "group" to the oxtra-vars option to the ansible[-playbook] 
command line. (-e "group=<value>") The value can be a group name or a
system name that is in the inventory file>

### Windows Playbooks
> All windows playbooks now rely on the local user's Kerberos tickets for 
> authentication on the remote server.  To ensure tickets are current, run
> __kinit__ after logging into the system.  This will ask for the domain
> password and fetch a current ticket, replacing any expired ticket.  Use
> __klist__ to list the user's principal and tickets.
```
prompt> kinit
Password for dmaple@GMTI.GBAHN.NET:

prompt> klist
Ticket cache: FILE:/tmp/krb5cc_149813743
Default principal: dmaple@GMTI.GBAHN.NET

Valid starting       Expires              Service principal
07/18/2017 10:06:54  07/18/2017 20:06:54  krbtgt/GMTI.GBAHN.NET@GMTI.GBAHN.NET
	renew until 07/25/2017 10:06:49
```

 * __win-test.yml__ - Tests access to Windows systems or groups.
 * __win-check-updates.yml__ - Checks for updates to Windows systems.
 * __win-update-critsec.yml__ - Apply Critical and Security updates and 
 reboot the servers when needed.
 * __win-update-critsec-cron.yml__ - Cron version of the Critical and 
 Security update playbook.
 * __win-update-all.yml__ - Apply ALL AVAILABLE UPDATES and reboot, if 
 necessary.
  
### Linux Playbooks
 * __linux-update.yml__ - Runs the default package manager for the Linux 
 system using the ansible package module that auto-detects the system package 
 manager.
 * __ansible-client.yml__ - Runs the ansible-client role to install (see 
         below.)

### Cross-platform Playbooks
 * __ping-any.yml__ - Basic test of ansible connectivity to any system, using 
 the right method for that system.

## Roles

 * __ansible-client__ - Creates the ansible user on all linux systems.  It 
 creates the ansible user and group, if needed, copies the authorized_keys 
 and configures sudors for elevated privileges.

## Configuration Files

 * __hosts__ - Default inventory file (override with -i <filename>)

 * __ansible.cfg__ - Local configuration file (overrides /etc/ansible/ansible.cfg)

