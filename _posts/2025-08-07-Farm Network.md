---
title: Farm Network
date: 2025-08-07 2:00:00
categories: [networking]
tags: [ubiquiti,farm,networking]
---

## Research

So I have been tasked with deploying a system to surveil our family farm. It is a small working cattle farm with the capacity for a couple hundred head of cattle. It is super remote, I installed Starlink recently as an upgrade to our NBN Skymuster connection which was pretty rubbish. The job has come after we realised we had been robbed of some cattle, which cost us quite a pretty penny.

So the goal is to deploy a network of cameras to capture footage of the boundary gates and tag events (cars, wildlife, people) and send notifications to me! The cameras need to be waterproof, night vision enabled, and of high enough quality to capture small details like dust covered number plates. I also wanted to build out the network at the house, as we would like Wi-Fi in the shed, and cameras watching the house, especially after we were broken into.

So for this task I split it up into a couple of stages, first I wanted to test out a couple of systems locally at the house where there is internet and electricity, and see what worked, what was on offer and see if requirements would change.

So I looked into trail cameras, but we would need to go out and manually check the sd cards, and charge up the batteries... also no live notifications, so that wasn't going to work.

Dad purchased a Nextech QC3890, which was a Wi-Fi camera which was a bit more promising, but the quality wasn't good enough for what we needed, and the process for getting footage was still too manual.

After doing a bit of research online I stumbled upon Ubiquiti, I watched a lot of YouTube videos on Ubiquiti and their products, mostly their Wi-Fi stuff, like UniFi and AmpliFi. After watching this [LTT video](https://www.youtube.com/watch?v=NkjD4xIhfTw) I was quite interested, firstly the price was reasonable, a one-off purchase was what I wanted, I didn't want to pay a subscription, or license fees, and secondly the quality, their cameras could easily do 4K and seemed to have good night vision. I also figured that the UniFi gear was also good and if I bought into one ecosystem, then everything might go a bit smoother.

## The Plan

So I did a bit more research on it all, looked into the whole Ubiquiti Range, from UniFi to UISP and more, I used this cool [tool](https://ispdesign.ui.com/#) from Ubiquiti to map out where everything would go, and then what I would need to make it work.

So my plan was to setup a PtP link between the house and a high point on the property, this high point on the property would be used as a central link, between the house and the boundary gate cameras, between the high point and the boundary gates I would setup PtMP links. Each module (everything except the house) was offgrid, so it would need to be self-powered and have some ability to connect to the other modules. So I plan to power each module with a Solar Panel, which would store energy in a couple of batteries, this would all be managed by a [Ubiquiti SolarPoint](https://store.ui.com/us/en/products/sunmax-sp-40) which saved me a bit of work as this also had network switch built-in.

I broke the rollout down to a couple of stages.

### Stage 1

Build out the home network.

So I got a UDM-SE, some cameras and some APs and play around with it. Test out the interface, test out the cameras and see if it really lived up to the reviews and the expectations I had. I also used this time to learn so much more about networking, and get really hands-on, splicing cables, learning about network interfaces and VLANs. 

So I put up some cameras, one to cover the driveway and another to cover the paddock close the house, this paddock camera was there to test out the night-vision capability.

I gave access to the rest of the family to see what they thought of the cameras, they were thrilled, the quality was great and it was super easy for them to access through the UniFi Protect app. 

Once I put in the UniFi U6-Pro AP, they were also super happy, they had good WiFi throughout the house, much better range then the Starlink Router, and I had better control over the network to seperate our IoT devices and personal devices onto seperate VLANs.

### Stage 2

This was going to be about testing the modules I had planned.

So this stage was to test that the modules worked, and that I could to UISP links between modules.
