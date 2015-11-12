Ansible-PostGIS3D
=================

[![Shippable](https://img.shields.io/shippable/561e5c991895ca44741dc1c7.svg?style=flat&label=%C3%A7a%20passe%20ou%20%C3%A7a%20casse%20?)](https://app.shippable.com/projects/561e5c991895ca44741dc1c7)

This role will install PostGIS with 3D support (sfcgal) and
pointcloud extension.

Target Platform: tested on debian (jessie and sid) and ubuntu trusty

Versions installed:

- postgresql **9.4.4** from the official postgresql repository
- sfcgal **1.2.1** compiled release from github
- pointcloud **1.0.1** compiled release from github
- pdal **1.0.1** compiled release from github
- postgis **2.2.0** compiled release from osgeo

Requirements
------------

- None

Role Variables
--------------

- build_directory: location to where the sources will be downloaded and compiled
(should be a non superuser directory)

The next variables could be overrided if you need some specific versions:

    - postgis_version
    - sfcgal_version
    - pointcloud_version
    - pdal_version

Dependencies
------------

- None

How to use it
-------------

* Testing the role with vagrant is as simple as:

        $ vagrant up jessie

That's all folks ! you will have a debian jessie with postgis ready for 3D and pointcloud support.

Now, it's your task to configure postgresql, pg_hba.conf etc...

* Another example to provision your local machine :

        ansible-playbook -i 'localhost,' -e "build_directory=/home/me/apps/postgis3d" --ask-become -c local test.yml

* If you want to checkout the role into your ansible role path for remote provisioning:

        ansible-galaxy install ldgeo.postgis3d

License
-------

GPLv3

Author Information
------------------

www.oslandia.com
