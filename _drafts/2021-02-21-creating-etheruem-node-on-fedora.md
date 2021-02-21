---
layout: post
title: creating etheruem node on fedora
date: '2021-02-21T11:31:37.000-00:00'
author: rabbitear
tags: Jekyll Github-Pages
modified_time: '2021-02-21T11:31:37.000-00:00'
---
## Game plan
:todo-lists:
* [○] Geth get going so can see the _eth.blockNumber_
* [○] Sync the node fully.
* [○] Make the notes.

Questions:
* Q: Why is the eth.blockNumber at zero?
* Q: How do I know if it's come up to the current blockNumber?
* Q: what does --miner.etherbase 'address' actually do?
* Q: is localhost port 8545 the right or is it 30303?

Try:
* start mining on http://127.0.0.1:8545
* watch _net.peerCount_ and _eth.blockNumber_

