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
There is a supervisor module responsible for managing the agents and their interactions. The agents are responsible for different tasks such as:
- Communication
- Personalization
- Sentiment Analysis
- Risk Analysis
- Making API calls

Too many options and too much uncertainty can lead to decision paralysis. Especially for uninformed traders, the amount of information available can be overwhelming. Don't you wish there was someone to guide you along?

We decided to go with a RAG architecture because of the benefit as described by the OpenAI cookbook. It says that when you fine-tune a model, it's like studying for an exam one week away.When you insert knowledge into the prompt via retrieval, it's like taking an exam with open notes.

The RAG database is populated with with information scraped from pages providing relevant information on trading platforms. 

We chose Gemini 1.0 as our LLM model because it is capable of reasoning and has sufficient context window. Just enough such that it is not too expensive to run and not too small to be useful.
Our RAG model is agentic RAG, where agents are able to loop and evaluate themselves if the answers are satisfactory.
Additionally, each agent is able to search the web for information if they don't already have enough information available to them. This is made possible with the Tavily tools binded to the agents.

We hope that with our app, users will have one click access to all the information they need to make informed decisions. All within the convenience of a chat interface.

## Limitations
1. not holding token on mainnet so cannot use faucet...(for Hyperliquid, requires token from Arbitrum Sepolia, and THENA)
2. hence no way to call on chain functions from agent

## Roadmap
We have identified areas for further R&D.
The next steps in our roadmap are to:
- Data collection and tuning via LangSmith and human feedback
- Implementation of long term memory for cross session usage

still researching on the following:
- https://xrpl.org/docs
- https://xrpl.org/blog/2015/introducing-the-data-api
- https://xrpl.org/docs/tutorials/python/send-payments/create-accounts-send-xrp
- https://xrpl.org/docs/references/http-websocket-apis
- https://xrpl.org/docs/references/data-api
- https://github.com/ripple/rippled-historical-database
