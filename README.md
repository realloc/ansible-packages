realloc.packages
=========

This role ensures the state of packages from the list given in variable.

I was missing
[platform_packages](https://supermarket.chef.io/cookbooks/platform_packages)
cookbook from Chef and didn't find a way to insert task execution between two
roles without ugly kludges.

Be aware that packages are not always have same name on different platforms and
you have to take care about providing a list according to the platform used.

Role Variables
--------------

Just a list of packages to be processed.

```yaml
packages: []

```

Example Playbook
----------------

```yaml
  roles:
    - role: realloc.packages
    packages:
      - tar
      - name: vim
        state: absent
      - name: emacs
        state: latest
```

License
-------

GPLv3

Author Information
------------------

Stanislav Bogatyrev <realloc@realloc.spb.ru>
