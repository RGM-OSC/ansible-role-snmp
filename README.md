Role Name
=========

This role install and configure net-snmpd daemon on Linux hosts (currently supports Red Hat and derivated, and Debian and derivated) and on Windows hosts.

The configuration sets-up a RGM dedicated security context with correct SNMP comunity name.

Requirements
------------

This role don't have any specific requirements except Ansible's prerequisites.

Role Variables
--------------

Default variables:

  - snmpd_conf_template:
specifies the snmpd.conf template file to use. This can be overidden by host variable or playbook variable in case of a specific configuration needs.

	- snmpd_conf_file:
The target snmpd.conf file location. Usually this should be modified

	- rgm_server:
The RGM server IP address. This should be overidden on playbook scope

	- snmp_ro_community:
	- snmp_location:
	- snmp_contact_name:
	- snmp_contact_email:
SNMP customization variables

Dependencies
------------

N/A

Example Playbook
----------------

This example calls the role and override EON IP address and SNMP community:

    - hosts: linux
			vars:
			- rgm_server: 192.168.1.1
			- snmp_ro_community: mycommunity

      roles:
         - snmpd

License
-------

BSD

Author Information
------------------

Eric Belhomme <ebelhomme@fr.scc.com>

