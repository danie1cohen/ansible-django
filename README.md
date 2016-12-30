Django
=========

A re-usable role for deploying django apps

Requirements
------------
This roles is built for running on Ubuntu Trusty boxes




Role Variables
--------------

You'll want to define a few basic variables

    # for the virtualenvironment
    project: yourproject

    django_repo: ssh://git@github.com/you/yourthing.git

The default apps are stored in django_default_apps. This means you only need
to list any ones that are specific to your project

    django_installed_apps:
      - yourapp

    django_secret_key: !super@random#key$woo!
    django_debug: yes
    django_allowed_hosts: []

If you want to add any additional settings you can specify them in the
django_addl_settings variable.  Since we've preserved the ability to
write python in this variable, if you want to represent a string, you'll need
make sure that quotes will be added in translation from yaml to python.

    django_addl_settings:
      FOO: "'?????'"
      BAR: "'PROFIT!!!!!!'"

Dependencies
------------

danie1cohen.virtualen3

Example Playbook
----------------

    - hosts: servers
      roles:
         - danie1cohen.django

License
-------

BSD

Author Information
------------------

[Dan Cohen](www.dancohen.io)
