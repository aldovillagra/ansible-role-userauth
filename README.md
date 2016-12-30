userauth
=========

Define la complegidad de la contraseña a se definida en RHEL5, RHEL6 y RHEL7

Requirements
------------
En el caso de RHEL5, python-simplejson
RHEL6 y RHEL5: nada

Default Role Variables
--------------
# defaults file for userauth
mail_dir: "/var/spool/mail"
# Maximum number of days a password may be used.
pass_max_days: 99999
# Minimum number of days allowed between password changes.
pass_min_days: 0
# Minimum acceptable password length.
pass_min_len: 8
# Number of days warning given before a password expires.
pass_warn_age: 7
# Default variable for RHEL5 and RHEL6
uid_min: 500
uid_max: 60000
gid_min: 500
gid_max: 60000
create_home: "yes"
umask: "077"
usergroups_enab: "yes"
md5_crypt_enab: "no"
encrypt_method: "SHA512"
# Force Capital Characters In Passwords - ucredit
complex_pass_capital: -2
# Force Lower Case Characters In Passwords - lcredit
complex_pass_lower: -2
# Force Numbers In Passwords - dcredit
complex_pass_number: -2
# Force The Use Of Symbols In Passwords - ocredit
complex_pass_symbol: -2
# Limit the users to set a password which is already used in the past
complex_pass_remember: 5
# Reintentos
complex_pass_retry: 3
# Default variable for RHEL76
uid_min_rhel7: 1000
uid_max_rhel7: 60000
sys_uid_min: 201
sys_uid_max: 999
gid_min_rhel7: 1000
gid_max_rhel7: 60000
sys_gid_min: 201
sys_gid_max: 999


Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: aldovillagra.userauth, complex_pass_capital: -4 }

License
-------

GPLv2
