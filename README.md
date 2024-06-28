---
feature: mdmclient
start-date: 2024-06-28
author: Yoann GINI
co-authors: Tasia ?
shepherd-team: ?
shepherd-leader: ?
related-issues: (will contain links to implementation PRs)
---

# Summary
[summary]: #summary

Specify the MDM Protocol used to manage NixOS endpoint in an organization. 
This MDM Protocol is built in NixOS for the client side and have to be supported by Mobile Device Management Solution to be functionnal.

# Motivation
[motivation]: #motivation

Modern use of computer, tablet and smartphone in all kind of organization, from small business to large corporation as well as non profit and education needs to manage a large fleet of devices nowadays.

And with the scale of the fleet, most people having at least a smartphone and a computer for work, if not a tablet on top of it, each organization face the needs of managing their fleet at scale and in mobility.

As the COVID-19 world wide lockdown taught us, there is two kind of organization: the one who had designed their information system to work from anywhere, and the one who hadn't yet.

From an organization point of view, it is now critical to have their fleet managed centrally but remotely too. Being able to quickly push at scale a VPN config change it critical, as well as collecting real time compliance status for endpoint encryption for example when you are under a PCI DSS audit.

Endpoint management have always been a thing, but historically built for local network, where a managing solution can reach out the endpoint using a management protocol. Or where some of the settings are polled by the endpoint via a directory service.

Nowadays, endpoint are mostly out of the organization, behind a lot of CG-NAT, with the management server hosted in the cloud, and directory service barely speak LDAP.

In 2011 Apple initiated a change that the whole industry followed since: the introduction of the MDM protocol.

And Mobile Device Management Protocol is a protocol made to allow some Internet exposed management solution to manage an infinite fleet of device, regardless of where they are.

Since then, all OS vendors followed and it's not the expected method to manage a fleet at scale.

So far, only Linux endpoint are missing from the MDM landscape.

This RFC aim for an MDM Protocol and Client for NixOS, handling the MDM needs for Linux via the help of NixOS already existing declarative system.
