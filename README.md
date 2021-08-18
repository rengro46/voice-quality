# Voice Quality Reporting

This is a development project to perform simple voice quality measurement


## Description

This project consist of a number of AWS platforms and components as follows:
1. Multiple VPC's (VPC-A - Shared Services), (VPC-B - Unified Comms), (VPC-C - Client Connectivity Unit) 
3. Multiple EC2 instances (SIP App host, Strongswan Host, NAT64 Hosts, Grafana Host)
4. a Transit Gateway - to interconnect VPC's via IPV6 only!
5. an Aurora MySQL instance - for storing Voice CDR record

## Architecture

The System Architecure is depicted below:

(./spi-voice.jpg)



The system works as follows:
1. The SIP Application 

## Extra Credit: Keep on building!

Change the placeholder Octocat gif on your GitHub Pages website by [creating your own personal Octocat emoji](https://myoctocat.com/build-your-octocat/) or [choose a different Octocat gif from our logo library here](https://octodex.github.com/). Add that image to line 12 of your `index.html` file, in place of the `<img src=` link.

Want to add even more code and fun styles to your GitHub Pages website? [Follow these instructions](https://github.com/github/personal-website) to build a fully-fledged static website.

![octocat](./images/create-octocat.png)

## Everything you need to know about GitHub

Getting started is the hardest part. If there’s anything you’d like to know as you get started with GitHub, try searching [GitHub Help](https://help.github.com). Our documentation has tutorials on everything from changing your repository settings to configuring GitHub from your command line.
