# Cross Site Scripting
## Introduction

Cross-site scripting (XSS) is a type of computer security vulnerability typically found in web applications. This vulnerability makes it possible for attackers to inject malicious code (e.g. JavaScripts) into victim's web browser. Using this malicious code, the attackers can steal the victim's credentials, such as cookies. The access control policies (i.e., the same origin policy) employed by the browser to protect those credentials can be bypassed by exploiting the XSS vulnerability. Vulnerabilities of this kind have been exploited to craft powerful phishing attacks and browser exploits.

## Task

We need to exploit a XSS vulnerability in the vulnerable web application named Elgg. Elgg is a very popular open-source web application for social network, and it has implemented a number of countermeasures to remedy the XSS threat.


This is in a way that is similar to what Samy Kamkar did to MySpace in 2005 through the notorious Samy worm. The ultimate goal of this attack is to spread an XSS worm among the users, such that whoever views an infected user profile will be infected, and whoever is infected will add you (i.e., the attacker) to his/her friend list.  




*Credit: SEED Labs - https://seedsecuritylabs.org/Labs_20.04/Web/Web_XSS_Elgg/*
