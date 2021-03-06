.. _yum-repo:

===========================================
 Percona :program:`yum` Repository
===========================================

The |Percona| :program:`yum` repository supports popular *RPM*-based operating systems, including the *Amazon Linux AMI*.

The easiest way to install the *Percona Yum* repository is to install an *RPM* that configures :program:`yum` and installs the `Percona GPG key <https://www.percona.com/downloads/RPM-GPG-KEY-percona>`_. Installation can also be done manually.

Automatic Installation
=======================

Execute the following command as a ``root`` user, replacing ``x86_64`` with ``i386`` if you are not running a 64-bit operating system: ::

  $ yum install http://www.percona.com/downloads/percona-release/percona-release-0.0-1.x86_64.rpm

The RPMs for the automatic installation are available at http://www.percona.com/downloads/percona-release/ and include source code.

You should see some output such as the following: ::

  Retrieving http://www.percona.com/downloads/percona-release/percona-release-0.0-1.x86_64.rpm
  Preparing...                ########################################### [100%]
     1:percona-release        ########################################### [100%]

The RPMs for the automatic installation are available at http://www.percona.com/downloads/percona-release/ and include source code.

Install XtraDB Cluster
=======================

Make sure to remove existing PXC-5.5 and PS-5.5/5.6 packages before proceeding.

Following command will install Cluster packages: ::

  $ yum install Percona-XtraDB-Cluster-56

Instead of ``Percona-XtraDB-Cluster-56`` you can install ``Percona-XtraDB-Cluster-full-56`` meta-package which will install ``Percona-XtraDB-Cluster-devel-56``, ``Percona-XtraDB-Cluster-test-56``, ``Percona-XtraDB-Cluster-debuginfo-56``, ``Percona-XtraDB-Cluster-galera-3-debuginfo``, and ``Percona-XtraDB-Cluster-shared-56`` packages in addition.

.. warning:: 

   In order to sucessfully install |Percona XtraDB Cluster| ``socat`` package will need to be installed first. ``socat`` package can be installed from the `EPEL <https://fedoraproject.org/wiki/EPEL>`_ repositories.


Percona `yum` Experimental repository
=====================================

Percona offers fresh beta builds from the experimental repository. To subscribe to the experimental repository, install the experimental *RPM*: ::

  yum install http://repo.percona.com/testing/centos/6/os/noarch/percona-testing-0.0-1.noarch.rpm

.. note:: 
 This repository works for both RHEL/CentOS 5 and RHEL/CentOS 6

Resolving package conflicts
===========================

In CentOS ``mysql-libs`` conflicts with ``Percona-XtraDB-Cluster-server-56.x86_64`` package. To avoid this you need to remove the ``mysql-libs`` package before installing |Percona XtraDB Cluster|. Package ``Percona-Server-shared-51.x86_64`` provides that dependency during installation if required.
