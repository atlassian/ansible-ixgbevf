Ansible Galaxy role - atlassian.ixgbevf
=======================================

This Ansible Galaxy role provides a modern Intel ixgbevf driver for AWS Enhanced Networking (SR-IOV) and 10Gbit connectivity using DKMS.

Usage
=====

In this example we configure a newer driver for our r3.4xlarge hosts in AWS EC2.

    - hosts: r3.4xlarge
      roles:
         - { role: atlassian.ixgbevf, ixgbevf_version: 2.16.4, ixgbevf_tar_sha1_hash: 110fa89c30b029e946ed73105c471cf03f1767be }

The SHA1 hash is manually supplied to ensure validation for the driver package out of band. Alternatively you can supply a binary directly in **atlassian.ixgbevf/files/ixgbevf-$VERSION.tar.gz**.

You can find the upstream source at [https://sourceforge.net/projects/e1000/files/ixgbevf%20stable/](https://sourceforge.net/projects/e1000/files/ixgbevf%20stable/)

Installation
============

Typically Galaxy roles will be included in your **roles/requirements.yml**. Your path may vary.

      - src: atlassian.ixgbevf
        version: 1.1.0

Install all of your Galaxy roles using **ansible-galaxy**, further documentation on the [Galaxy](https://galaxy.ansible.com/intro#download) intro page.

      $ ansible-galaxy install -r roles/requirements.yml -p roles/

Tests
=====

Ansible Galaxy has basic integration with TravisCI for testing, alternatively you can run the tests yourself.

      $ ansible-playbook tests/test.yml -i tests/inventory --syntax-check

![https://travis-ci.org/atlassian/ansible-ixgbevf.svg](https://travis-ci.org/atlassian/ansible-ixgbevf.svg)

Contributors
============

Pull requests, issues and comments welcome. For pull requests:

* Add tests for new features and bug fixes
* Follow the existing style
* Separate unrelated changes into multiple pull requests

See the existing issues for things to start contributing.

For bigger changes, make sure you start a discussion first by creating
an issue and explaining the intended change.

Atlassian requires contributors to sign a Contributor License Agreement,
known as a CLA. This serves as a record stating that the contributor is
entitled to contribute the code/documentation/translation to the project
and is willing to have it used in distributions and derivative works
(or is willing to transfer ownership).

Prior to accepting your contributions we ask that you please follow the appropriate
link below to digitally sign the CLA. The Corporate CLA is for those who are
contributing as a member of an organization and the individual CLA is for
those contributing as an individual.

* [CLA for corporate contributors](https://na2.docusign.net/Member/PowerFormSigning.aspx?PowerFormId=e1c17c66-ca4d-4aab-a953-2c231af4a20b)
* [CLA for individuals](https://na2.docusign.net/Member/PowerFormSigning.aspx?PowerFormId=3f94fbdc-2fbe-46ac-b14c-5d152700ae5d)

License
========

Copyright (c) 2016 Atlassian and others.
Apache 2.0 licensed, see [LICENSE.txt](LICENSE.txt) file.
