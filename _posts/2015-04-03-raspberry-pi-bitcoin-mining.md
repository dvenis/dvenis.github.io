---
layout: post
title: "Raspberry Pi Bitcoin Mining"
date:   2015-04-04 09:41:00
tags: bitcoin raspberry-pi research 
---

Since I bought my Raspberry Pi 2 a month ago, I've been wondering what things I could do with it. One of the uses I thought would be really cool was to use it as a bitcoin miner. Obviously I wasn't expecting this to be a get rich quick scheme, but maybe the Pi could pay for itself if with a year of mining.

#What is Mining?

In an oversimplified explanation, bitcoin miners are trying to find hashes that match a given set of criteria. Once this hash is found, it is broadcasted to the rest of the mining network, and bitcoins are awarded to the miner. The difficulty of the hashing criteria is being constantly adjusted so that only 25 bitcoins are awarded every 10 minutes (one block). This means that when there are more, and more powerful, miners it becomes harder to mine for bitcoins.

#Results

The I used for the Pi is [cpuminer](http://sourceforge.net/projects/cpuminer/). After some configuration (following [this](http://www.linuxuser.co.uk/tutorials/mine-bitcoins-with-raspberry-pi) guide), and setting up my wallet and bitcoin pool, I was ready to mine. Unfortunately, the mining speed was, to say the least, underwhelming. 

{:.large}
{% include image.html url="/img/cpuminer-rpi2.jpg" caption="cpuminer mining speeds on the Raspberry Pi 2 (ignore the beautiful CRT TV quality)" %}

Each thread was clocking in at less than 0.5kH/s, for a total of 1.8kH/s. To put this in perspective, for $20 I could buy an ASIC USB miner that does 2GH/s, and probably uses less electricity. Assuming all currencies retain the same value, it would take 576 701 years to make $1USD (that's $1.25CAD though!). (After some research though, the RPi2 processor should be capable of over 200kH/s, so it should really only be 5000 years!) 

Even if you make a proper Pi miner that uses ASIC USBs on a powered hub to mine, you won't ever make real money. Looking at the Hex-Fury ASIC, it's advertised as up to 15GH/s, and uses at least 10W (5V and 2A). This is the most liberal estimate. At current values, 15GH/s makes $1.204USD per month. Total power used during the month is 7.2kWh. Let's say you can get electricity at $0.07/kWh, then your profit is $0.70/month, per Hex-Fury. That means it will take 30 years to pay off the price of the ASIC in the first place. (These are all the most liberal estimates I can allow myself to make. In the real world you wouldn't even be able to get this performance.)

The bottom line is, there is no real way to mine bitcoins profitably on a small scale.
