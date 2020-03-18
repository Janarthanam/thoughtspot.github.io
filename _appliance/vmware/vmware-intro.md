---
title: [VMware configuration overview]
keywords: vmware
tags: [vm, performance]
last_updated: 3/18/2020
sidebar: mydoc_sidebar
permalink: /:collection/:path.html
---
This section is an overview of the ThoughtSpot AI-Driven analytics platform hosted on the VMware vSphere Hypervisor (ESXi) 6.5 environment.

## About ThoughtSpot on VMware

The VMware virtualization platform provides highly scalable and efficient memory
and CPU resources management that can be used by ThoughtSpot instances.
Additionally, the VMware virtualization environment is an easy transition
between development and production environments. The following diagram shows
the components of a VMware and ThoughtSpot architecture:

![]({{ site.baseurl }}/images/vmware-components.png)

{% include note.html content="This is a generic representation; Only CentOS-based
virtual machines are supported with ThoughtSpot." %}

Your database capacity will determine the number of ThoughtSpot instances and
the instance network/storage requirements. In addition, you can scale your
ThoughtSpot VMs as your dataset size grows.

## Configuration (minimum)

ThoughtSpot Engineering has performed extensive testing of the ThoughtSpot
platform on VMware for the best performance, load balancing, scalability,
and reliability. Based on this testing, ThoughtSpot recommends the following
_minimum specifications_ for an individual VMware ESXi host machine:

* 512GB Memory
* 200GB SSD for each node
* 3X 2TB Hard disks (6TB in total in hard disk space)
* 72 Hyper-threaded Cores (Additional spare cores can also be added).
* Intel Xeon 2600 series operating at clock frequencies 2.1GHz (Faster is better).

Locally attached storage provides the best performance.

SAN can be used, but must comply with the following requirements:
* 136 MBps minimum random read bandwidth
* 240 random IOPS (~4ms seek latency)

NAS/NFS is not supported since its latency is so high that it tends to be unreliable.

All virtualization hosts should have VMware vSphere Hypervisor (ESXi) 6.5 installed.

ThoughtSpot provides a VMware template (OVF) together with a VMDK (Virtual
Machine Disk) file for configuring a VM. VMDK is a file format that describes
containers for virtual hard disk drives to be used in virtual machines like
VMware Workstation or VirtualBox. OVF is a platform-independent, efficient,
extensible, and open packaging distribution format for virtual machines.

The ThoughtSpot VM configuration uses thin provisioning and sets the recommended
reserved memory, among other important specifications. You can obtain these
files from your ThoughtSpot Customer Success Engineer.

## Questions or comments?

We hope your experience with ThoughtSpot is excellent. Please let us know how it
goes, and what we can do to make it better. You can [contact ThoughtSpot]({{
site.baseurl }}/appliance/contact.html) by phone, mail, email, or by filing a
support ticket.
