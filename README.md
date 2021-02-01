Role Name
=========
This role is not yet tested!

This role installs certbot on RedHat machines (can be extended other distros as well). This role is created taken sectigo on account with current limitations with agreement and apis.

Role Variables
--------------

When using vault, use 'vault_sectigo_' prefix with variables.
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

domain: Which domains to request if needed.
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: CSCfi.certbot, apache: True }

License
-------

MIT

Author Information
------------------

CSC.fi
