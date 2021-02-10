Role Name
=========

This role installs certbot on RedHat machines (can be extended other distros as well). This role is created taken sectigo on account with current limitations with agreement and apis.

Role Variables
--------------

When using vault, use 'vault_sectigo_' prefix with variables otherwise just 'sectigo_' prefix is used with variables (except with variable sectigo_domains which is not vaulted variable).
```
vault_sectigo_account: Account directory under /etc/letsencrypt/accounts/acme.sectigo.com/v2/OV/

vault_sectigo_meta:
  creation_dt: 
  creation_host: 

vault_sectigo_regr:
  body: {}
  uri: API uri

vault_sectigo_private_key:
  e: AQAB
  d:
  n:
  q:
  p:
  kty: RSA
  qi:
  dp:
  dq:

sectigo_domains: Which domain(s) to request if needed.
```

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: CSCfi.certbot, sectigo_cron: '30 6 * * * certbot renew --post-hook "systemctl reload httpd"'}

License
-------

MIT

Author Information
------------------

CSC.fi
