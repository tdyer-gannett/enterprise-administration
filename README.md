# enterprise-ansible
Central Enterprise Ansible Repository

## Playbooks
    > Some playbooks have a default group, if one is not hard-coded if one is
    > not specified on the command line.  To specify a group, add extra-vars
    > option to the ansible[-playbook] command line. (-e "variable=value")

 * win_test.yml - Tests access to Windows systems or groups.
    ```
    ansible-playbook win_test.yml -e "group=<group/system name>"
    ```

 * win-check-updates.yml - Checks for updates to Windows systems.
    ```
    ansible-playbook win-check-updates.yml -e "group=<group/system name>"
    ```

## Roles

 * ansible-client - Creates the ansible user on all linux systems.  It creates
   the ansible user and group, if needed, copies the authorized_keys and 
   configures sudors for elevated privileges.

## Configuration Files

 * hosts - Default inventory file (override with -i <filename>)

 * ansible.cfg - Local configuration file (overrides /etc/ansible/ansible.cfg)

