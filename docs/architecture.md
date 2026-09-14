# Architecture

## Overview

The system is built to quickly detect new item listings on CSGORoll and automatically buy items that match the configured pricing rules.  
It also automates the selling side by accepting purchases from other users and sending the corresponding Steam trade offers.

## Main Parts

**1. Real-time Listener**  
Receives new item listings as soon as they appear on the platform.

**2. Pricing Rules**  
Checks each listing against the configured pricing rules and decides whether the item should be bought.

**3. Execution**  
- **Buying:** If the item matches the pricing rules, the system buys it and handles the Steam trade offer.  
- **Selling:** When someone buys an item from you, the system automatically accepts the purchase and sends the Steam trade offer.

**4. Database**  
Stores information about items, trades, prices.

## Simple Flow

### Buying

New listing → Listener → Pricing Rules → Buy → Accept Steam Trade Offer
↓
Database

### Selling

Someone buys your item → Accept purchase → Send Steam Trade Offer
↓
Database

## Goals

- React to new listings as fast as possible
- Make reliable buy/sell decisions
- Handle Steam trades automatically
- Keep the system stable and easy to configure