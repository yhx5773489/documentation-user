:banner: banners/odoo-sh.jpg

==================================
Settings
==================================

Overview
========

The settings allow you to manage the configuration of your project.

.. image:: ./media/interface-settings.png
   :align: center

Project name
============

The name of your project.

.. image:: ./media/interface-settings-projectname.png
   :align: center

This is the domain that will be used to access your production database.

The domain to access your staging and development builds will contain this name as well.
However, when you change your project name, only future builds will use the new name.

Collaborators
=============

Manage the Github users who can access your project.

.. image:: ./media/interface-settings-collaborators.png
   :align: center

There are two levels of users:
 * Admin: has access to all features of Odoo.sh.
 * User: does not have access to the project settings nor to the production and staging databases.

The user group is meant for developers who can make modifications in your code but are not allowed to access the
production data.
Users of this group cannot connect to the production and staging databases using the *1-click connect* feature,
but they can of course use their regular account on these databases if they have one, using their regular credentials.

In addition, they cannot use the webshell nor have access to the server logs.

+---------------------+-----------------+-----------+-----------+
|                     |                 | User      | Admin     |
+=====================+=================+===========+===========+
|Development          | History         |     X     |     X     |
+---------------------+-----------------+-----------+-----------+
|                     | 1-click connect |     X     |     X     |
+---------------------+-----------------+-----------+-----------+
|                     | Logs            |     X     |     X     |
+---------------------+-----------------+-----------+-----------+
|                     | Shell           |     X     |     X     |
+---------------------+-----------------+-----------+-----------+
|                     | Mails           |     X     |     X     |
+---------------------+-----------------+-----------+-----------+
|Production & Staging | History         |     X     |     X     |
+---------------------+-----------------+-----------+-----------+
|                     | 1-click connect |           |     X     |
+---------------------+-----------------+-----------+-----------+
|                     | Logs            |           |     X     |
+---------------------+-----------------+-----------+-----------+
|                     | Shell           |           |     X     |
+---------------------+-----------------+-----------+-----------+
|                     | Mails           |           |     X     |
+---------------------+-----------------+-----------+-----------+
|Status               |                 |     X     |     X     |
+---------------------+-----------------+-----------+-----------+
|Settings             |                 |           |     X     |
+---------------------+-----------------+-----------+-----------+

Public Access
=============

Allow public access to your development builds.

.. image:: ./media/interface-settings-public.png
   :align: center

Expose the Builds page publicly, allowing visitors to connect to your development builds.

In addition, visitors have access to the logs, shell and mails of your development builds.

Production and staging builds are excluded, visitors can only see their status.

Modules installation
====================

Choose the modules to install automatically for your development builds.

.. image:: ./media/interface-settings-modulesinstallation.png
   :align: center

* *Install only my modules* will install the modules of the branch only.
  The ` submodules <https://git-scm.com/book/en/v2/Git-Tools-Submodules>`_ are excluded.
* *Full installation (all modules)* will install the modules of the branch, the modules included in the submodules
  and all standard modules of Odoo.
* *Install a list of modules* will install the modules specified in the input just below this option.
  The names are the technical name of the modules, and they must be comma-separated.

All installed modules will be tested.
The tests in the standard Odoo modules suite can take up to 1 hour.
This setting applies to development builds only.
Staging builds duplicate the production build and the production build only installs base.

Custom domains
==============

Configure your own domain name.

.. image:: ./media/interface-settings-customdomains.png
   :align: center
