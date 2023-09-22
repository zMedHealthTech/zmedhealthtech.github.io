---
title: Network Setup for AV Call and IP Camera Low latency
date: 2023-07-13 21:00:00 +0530
categories: [AV Call, Network]
tags: [av, call, audio, video, low, latency, bandwidth, network, udp, tcp, outbound, inbound, ip camera]
author: zmed
---


# Setup your network for zMed AV Call and IP Camera Low latency

This document is meant for hospital IT administrators to configure and oversee their network to ensure a seamless experience for users during zMed Audio Video Calls and to achieve low-latency IP Camera viewing.

In order to ensure high quality Audio Video calls without drop in zMed, it's crucial to configure your network to enable efficient communication between the Hospital Network that the end user is using to access zMed application and zMed servers. To accomplish this, please consider the following recommendations:

1. Ensure that zMed AV Call traffic has a direct and efficient connection to the public internet.
2. Avoid the use of proxies, packet inspection, protocol analyzers, and quality of service (QoS) measures.
3. Continuously assess and enhance latency, bandwidth, and your Wi-Fi network for optimal performance.

## Setup your Network

### Setup outbound ports for media traffic

Audio video calls and IP Camera Low Latency mode uses STUN and TURN servers. 
Update your firewall settings to facilitate the flow of media traffic to and from your hospital with the following steps:

1. For audio and video communication, configure your firewall to allow outbound `UDP` ports `3478`, `13478`, `5500` and `19302​–19309`.
2. To facilitate web traffic and user authentication, permit outbound `UDP` and `TCP` traffic on port `443`, `13478` and `5500`.

Please ensure that there are no IP restrictions or bandwidth limitations on these ports.

`In cases where UDP ports are blocked, the system will automatically switch to using TCP. However, it's important to be aware that prolonged use of TCP or proxied TCP may lead to a deterioration in overall call quality.`

### Authorize Access to Uniform Resource Locators (URLs)

Ensure that there are no restrictions within your hospital network or the network from which you intend to initiate calls for the following domains:

1. stun.l.google.com
2. *.zmed.tech

It is important to note that there should be no limitations or restrictions, bandwidth and rate limiting, on the mentioned domains for the proper functioning of the `STUN` and `TURN` protocols.

### Review bandwidth requirements for AV Calls

Ensure Adequate Network Capacity for HD Video Calls

Your network should possess sufficient bandwidth to accommodate concurrent HD video calls as well as additional bandwidth to cater to other demands, such as live streaming. It's important to acknowledge that the number of participants, screensharing, and various other factors can influence the utilization of bandwidth.

#### Determine the Minimum Bandwidth Requirements for zMed Calls

To determine the minimum bandwidth your hospitals needs, multiply the average bandwidth per participant by the highest number of participants engaging in calls simultaneously. Keep in mind that several variables, including the number of calls, and screensharing, can impact the bandwidth consumption.

| Average bandwidth per participant for large hospitals |  | |
|--|--|--|
|Call type  | Outbound | Inbound |
|Video  | 2.5 Mbps | 3.5 Mbps |
|Audio only  | 15 Kbps | 20 Kbps |


| Bandwidth per participant for small hospitals or individuals |  | |
|--|--|--|
|Call type  | Outbound | Inbound |
|1080p video  | Up to 5 Mbps | Up to 5 Mbps |
|720p video  | Up to 3 Mbps | Up to 3 Mbps |
|Audio only  | 100 Kbps | 100 Kbps |

`Note : Depending on the resolution sent`
