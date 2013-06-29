Vagrant boxes for AWS
=====================

This project generates various Vagrant ".box" files, suitable for use with [vagrant-aws](https://github.com/mitchellh/vagrant-aws).

Boxes are based on the official Ubuntu AMIs (64-bit, EBS-backed).

To generate the boxes run `rake build`.

To generate the boxes and import them into Vagrant, run `rake add`.
