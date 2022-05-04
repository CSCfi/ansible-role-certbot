Role Name
=========

This role installs certbot on RedHat machines (can be extended other distros as well). This role is created taken sectigo on account with current limitations with agreement and apis.

Role Variables
--------------

When using vault, use 'vault_sectigo_' prefix with variables otherwise just 'sectigo_' prefix is used with variables (except with variable sectigo_domains which is not vaulted variable).
```
sectigo_domains: Which domain(s) to request if needed.
sectigo_san_domains: If SAN domain(s) is needed on certificate.
```

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: CSCfi.certbot, sectigo_cron: '30 6 * * * certbot renew --post-hook "systemctl reload httpd"'}


Example Playbook when requesting certificate with SAN
----------------

    - hosts: servers
      roles:
         - { role: CSCfi.certbot, sectigo_cron: '30 6 * * * certbot renew --post-hook "systemctl reload httpd"', sectigo_san_domains: " --domain server1.domain.example --domain server2.domain.example"}
         

License
-------

MIT

Author Information
------------------

CSC.fi
