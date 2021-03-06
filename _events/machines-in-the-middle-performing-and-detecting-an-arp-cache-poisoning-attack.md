---
title: "Machines in the Middle: Performing and Detecting an ARP Cache Poisoning Attack"
startDate: &startDate 2019-12-14 20:00:00 -0500
endDate: 2019-12-14 20:45:00 -0500
date: *startDate
location: 20 Jay Street, Suite 317, Brooklyn, NY, 11201, United States
speakers:
    - anarchotechnyc
teaser: Solidify your understanding of the data-link layer (OSI Layer 2) at this hands-on workshop that will walk you through the process of performing a classic ARP spoofing attack, a fundamental NetSec technique that is still used in many real-life hacking scenarios today.
conference: "2019"
redirect_from:
    - /events/machines-in-the-middle-performing-and-detecting-an-arp-cache-poisoning-attack
---

Before there was &ldquo;The Internet,&rdquo; there was <a href="https://simple.wikipedia.org/wiki/Ethernet">Ethernet</a>. First developed in the mid 1970&rsquo;s, Ethernet takes its name from the erroneous belief first postulated in the late 19<sup>th</sup> century that an omnipresent yet invisible material known as &ldquo;ether&rdquo; permeated everything and everyone. Today, in a kind of self-fulfilling prophecy, ethernet is the near-ubiquitous link-layer networking technology that underpins almost every modern telecommunications network.

By examining Ethernet network frames, we will see how Internet communications, such as data sent to one IP address or another, is carried from one physical device to another, thus traversing &ldquo;the ether.&rdquo; This process is facilitated by the <a href="https://simple.wikipedia.org/wiki/Address_Resolution_Protocol">Address Resolution Protocol (ARP)</a>, a simple mechanism that maps IP addresses to hardware device addresses. But ARP has a fundamental flaw: its own messages cannot be authenticated.

This lack of authentication can be exploited for both legitimate and illegitmate purposes, allowing for increased resiliency, or enabling a malicious attacker to pretend to be someone that they are not. In this latter case, an attacker can perform network-based Denial-of-Service (DOS) or Machine-in-the-Middle (MITM) attacks regardless of whether or not some higher-level encryption (like Wi-Fi passwords) is used. By performing what is known as an ARP cache poisoning attack, attackers are able to masquerade as any other device on &ldquo;the ethernet.&rdquo; This session will demonstrate how this attack works and what you can do to detect, prevent, and remediate such attacks on your networks.
