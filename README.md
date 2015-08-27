OS Branding
=========

This role is used for branding openstack to your needs

Requirements
------------

There is no role as requirement, per se. Although you should have openstack deployed.

Role Variables
--------------

Here are the variables introduced in the role:
* horizon_site_name
* horizon_local_settings_path
* horizon_static_folder
* horizon_custom_uploads

All rhese variables (except the last one) are defined in the defaults/main.yml file.

The standard variables should work and brand openstack to the standard openstack style (so, there is NO change at first sight). Therefore if you want to give your openstack a special look,
you should override these variables with what you need.

* Fill in the horizon_site_name variable to replace the name of your cloud (the name is used in the title, you can see it in your browser)
* The horizon_custom_uploads is a dict that you can fill with your files, by setting their name, source (on the deployment host) and destination (on the horizon host)

Here is an example:

  horizon_custom_uploads:
    file1:
      src: /etc/openstack_deploy/files/logo.png
      dest: "{{horizon_static_folder}}dashboard/img/logo.png"

Dependencies
------------

No dependency. Ansible 1.5 should be enough.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: horizon_all
      roles:
         - { role: os_branding, horizon_site_name: 'My OpenStack Cloud' }

License
-------

Apache2

Author Information
------------------

Copyright 2015, Jean-Philippe Evrard
