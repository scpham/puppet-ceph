ceph
====

#### Table of Contents

1. [Overview - What is the ceph module?](#overview)
2. [Module Description - What does the module do?](#module-description)
3. [Setup - The basics of getting started with ceph](#setup)
4. [Implementation - An under-the-hood peek at what the module is doing](#implementation)
5. [Limitations - OS compatibility, etc.](#limitations)
6. [Development - Guide for contributing to the module](#development)
7. [Contributors - Those with commits](#contributors)
7. [Integration - Apply the module and test restults](#integration-tests)
8. [Release Notes - Notes on the most recent updates to the module](#release-notes)

Overview
--------

The ceph module is intended to leverage all [Ceph](http://ceph.com/) has to offer and allow for a wide range of use case. Although hosted on the OpenStack infrastructure, it does not require to sign a CLA nor is it restricted to OpenStack users. It benefits from a structured development process that helps federate the development effort. Each component is unit tested and an integration test shows that it performs as expected when used with a realistic scenario.

Module Description
------------------

The ceph module deploys a [Ceph](http://ceph.com/) cluster ( MON, OSD ), the [Cephfs](http://ceph.com/docs/next/cephfs/) file system and the [RadosGW](http://ceph.com/docs/next/radosgw/) object store. It provides integration with various environments ( OpenStack ... ) and components to be used by third party puppet modules that depend on a Ceph cluster.

Setup
-----

Implementation
--------------

A [blueprint](https://wiki.openstack.org/wiki/Puppet-openstack/ceph-blueprint) contains an inventory of what is desirable. It was decided to start from scratch and implement one module at a time.

Limitations
-----------

Use Cases
---------

* [I want to try this module, heard of ceph, want to see it in action] (USECASES.md#i-want-to-try-this-module,-heard-of-ceph,-want-to-see-it-in-action)
* [I want to operate a production cluster] (USECASES.md#i-want-to-operate-a-production-cluster)

Development
-----------

    git clone https://github.com/stackforge/puppet-ceph.git
    cd puppet-ceph
    # nokogiri dependencies
    sudo apt-get install ruby-dev libxml2-dev libxslt-dev
    sudo gem install bundler
    bundle install

The developer documentation of the puppet-openstack project is the reference:

* https://wiki.openstack.org/wiki/Puppet-openstack#Developer_documentation

Mailing lists:

* (puppet-openstack)[https://groups.google.com/a/puppetlabs.com/forum/#!forum/puppet-openstack]
* (ceph-devel)[http://ceph.com/resources/mailing-list-irc/]

IRC channels:

* irc.freenode.net#puppet-openstack
* irc.oftc.net#ceph-devel

Integration Tests
-----------------

Relies on
[rspec-system-puppet](https://github.com/puppetlabs/rspec-system-puppet)
and tests are in spec/system. It runs virtual machines and requires
4GB of free memory and 10GB of free disk space.

* [Install Vagrant and Virtualbox](http://docs-v1.vagrantup.com/v1/docs/getting-started/)

* BUNDLE_PATH=/tmp/vendor bundle install
* BUNDLE_PATH=/tmp/vendor bundle exec rake lint
* BUNDLE_PATH=/tmp/vendor bundle exec rake spec
* BUNDLE_PATH=/tmp/vendor bundle exec rake spec:system

On success it should complete with

    ...
    =end=============================================================
    Finished in 4 minutes 1.7 seconds
    1 example, 0 failures


Contributors
------------

* https://github.com/stackforge/puppet-ceph/graphs/contributors

Release Notes
-------------
