Ansible Role Python
===================

|Build Status| |Ansible Galaxy| |GitHub issues| |GitHub license|

:Version: 0.2.2
:Web: https://github.com/equipindustry/ansible-role-python
:Download: http://github.com/equipindustry/ansible-role-python
:Source: http://github.com/equipindustry/ansible-role-python
:Keywords: ansible-role-python

.. contents:: Table of Contents:
    :local:

Ansible Galaxy role for `Python`_.

Requirements:
-------------

List of applications:

- `Pyenv`_
- `Docker`_

Install
-------

Install it with the following command:

.. code-block:: bash

    $ ansible-galaxy install equipindustry.python

Role Variables
--------------

The default role variables in ``defaults/main.yml`` are:

.. code-block:: yaml

        python_pyenv_path: "{{ ansible_env.HOME }}/pyenv"
        python_pyenv_owner: "{{ ansible_env.USER }}"
        python_pyenv_python_versions: ["3.6.0"]
        python_pyenv_delete_virtualenvs: [{ venv_name: "latest" }]
        python_pyenv_virtualenvs: [{ venv_name: "latest", py_version: "3.6.0" }]
        python_pyenv_update_git_install: no

- Deploy code

.. code-block:: yaml

    - role: equipindustry.python
      python_pyenv_install: no
      python_pyenv_update_git_install: no

Dependencies
------------

None

Example Playbook
----------------

See the `examples <./examples/>`__ directory.

To run this playbook with default settings, create a basic playbook like
this:

.. code:: yaml

        - hosts: servers
          roles:
            - equipindustry.python

To install a specific version:

.. code:: yaml

      - hosts: servers
        roles:
          - { role: equipindustry.python }

.. code:: yaml

        - hosts: servers
          roles:
             - role: equipindustry.python
               python_pyenv_path: "{{ home }}/pyenv"
               python_pyenv_owner: "{{ instance_owner }}"
               python_pyenv_update_git_install: no
               python_pyenv_python_versions:
                 - "3.5.1"
                 - "2.7.9"
               python_pyenv_delete_virtualenvs:
                 - venv_name: "delete_venv_name"
               python_pyenv_virtualenvs:
                 - venv_name: "latest_v3"
                   py_version: "3.5.1"
                 - venv_name: "latest_v2"
                   py_version: "2.7.9"

License
-------

The code in this repository is licensed under the Apache unless
otherwise noted.

Please see LICENSE_ for details.

Changelog
---------

Please see `CHANGELOG`_ for more information what
has changed recently.

Contributing
============

Please see `CONTRIBUTING`_ for details.


Versioning
----------

Releases are managed using bitbucket release feature. We use [Semantic Versioning](http://semver.org) for all
the releases. Every change made to the code base will be referred to in the release notes (except for
cleanups and refactorings).

Credits
-------

-  `author`_
-  `contributors`_

Made with :heart: :coffee: and :pizza: by `author`_ and `company`_.

.. Badges:

.. |Build Status| image:: https://travis-ci.org/equipindustry/ansible-role-python.svg
   :target: https://travis-ci.org/equipindustry/ansible-role-python
.. |Ansible Galaxy| image:: https://img.shields.io/badge/galaxy-equipindustry.python-blue.svg
   :target: https://galaxy.ansible.com/equipindustry/ansible-role-python/
.. |GitHub issues| image:: https://img.shields.io/github/issues/equipindustry/ansible-role-python.svg
   :target: https://github.com/equipindustry/ansible-role-python/issues
.. |GitHub license| image:: https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square
   :target: LICENSE

.. Links
.. _`changelog`: CHANGELOG.rst
.. _`contributors`: AUTHORS
.. _`contributing`: docs/source/CONTRIBUTING.rst
.. _`LICENSE`: LICENSE

.. _`company`: https://github.com/equipindustry
.. _`author`: https://github.com/luismayta

.. dependences
.. _Python: https://www.python.org
.. _Pyenv: https://github.com/pyenv/pyenv
.. _Docker: https://www.docker.com/
