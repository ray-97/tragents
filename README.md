Setup your virtual environment and install the requirements:
```
uv venv # Create a virtual environment with https://github.com/astral-sh/uv
source .venv/bin/activate
uv pip install -r requirements.txt
```

# Overview
This document provides an overview of the research conducted on areas of integration between AI Agents and crypto trading protocols such as THENA, HyperLiquid and XRPL.

## Table of Contents
1. [Introduction](#Introduction)
2. [Architecture](#Architecture)
3. [Limitations](#Limitations)
5. [Roadmap](#Roadmap)

## Introduction
Our project aims to enhance user experience according to their profile(risk appetite, goals, token type preferences etc), optimize liquidity management and improving decision making across the ecosystem. We are targeting retail users (more specifically people considered to be uninformed traders) by aiding them in research (sentimental analysis on KOLs tweeter, news, governance proposals etc), decision making(suggestions for pricing, market entry and position size for staking, pooling, and  reallocation etc) and automation of on chain trading, LP & staking. 

In a way, this achieves the goals of liquidity optimization, risk management, governance decision support, sentiment & market analysis and user experience enhancement. 

## Architecture
A system crew of agents for responsible for different tasks, built using LangChain(a composable framework for building LLMs).


## Limitations
1. not holding token on mainnet so cannot use faucet...(for Hyperliquid, requires token from Arbitrum Sepolia, and THENA)
2. hence no way to call on chain functions from agent

## Roadmap
We have identified areas for further R&D.
The next steps in our roadmap are to:
- Data collection and tuning via LangSmith and human feedback

still researching on the following:
- https://xrpl.org/docs
- https://xrpl.org/blog/2015/introducing-the-data-api
- https://xrpl.org/docs/tutorials/python/send-payments/create-accounts-send-xrp
- https://xrpl.org/docs/references/http-websocket-apis
- https://xrpl.org/docs/references/data-api
- https://github.com/ripple/rippled-historical-database
