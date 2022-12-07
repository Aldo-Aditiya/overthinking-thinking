---
{"dg-publish":true,"permalink":"/2-general-archive/designing-quantitative-trading-systems/"}
---


## Overview of System Design
A trading system is a system that helps you decide **when** to trade, how big to set your **bet sizes**, and **allocation** division to different trades (e.g. on different instruments).

To determine each of those variables, we need to consider three things:
- [[2 - General Archive/1 - How Much do You Like the Trade?\|1 - How Much do You Like the Trade?]] quantified through **Forecasts**
- [[2 - General Archive/2 - How Much Can You Afford to Lose?\|2 - How Much Can You Afford to Lose?]] quantified through **Volatility Targets**
- [[2 - General Archive/3 - How Risky Is the Trade?\|3 - How Risky Is the Trade?]] quantified through **Risk**

We will see how we combine these three aspects to design our trading system. 

Note: this system design is mostly based on Robert Carver's brilliant book, [Systematic Trading](https://www.amazon.com/Systematic-Trading-designing-trading-investing/dp/0857194453).
