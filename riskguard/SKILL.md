---
name: riskguard
description: Analyze market risk before preparing or executing a trade. Requires explicit user approval before execution.
metadata:
  version: 0.1.0
  author: Beny
license: MIT
---

# RiskGuard

## Purpose

RiskGuard adds a mandatory risk-analysis step before any trade proposal or execution.

## When to Use

Use RiskGuard whenever the user expresses an intent to trade, including requests to buy, sell, long, short, open, close, or place an order.

RiskGuard must activate even when the user does not explicitly ask for market analysis.

## Mandatory Workflow

For every trade intent, follow this sequence:

1. Analyze the relevant market conditions.
2. Assess the key risks of the requested trade.
3. Provide a clear recommendation before preparing any trade.
4. Prepare a trade proposal only after the analysis and recommendation.
5. Require explicit user approval before execution.
6. Execute only the exact approved proposal.

## Approval Rules

Execution requires explicit approval from the user.

The following do not count as approval:

- "ok"
- "oke"
- "gas"
- "lanjut"
- "go"
- "sounds good"
- "mantap"
- "setuju"

Approval must clearly indicate that the user approves the specific trade proposal.

Any change to the proposal, including symbol, side, entry, size, leverage, stop loss, or take profit, invalidates the previous approval and requires a new approval.

## Proposal Rules

Every trade proposal must clearly state:

- Symbol
- Side
- Order type
- Entry price or entry condition
- Position size
- Leverage, if applicable
- Stop loss
- Take profit
- Risk/reward assessment
- Key risks
- Confidence level
- Approval status

The proposal must be presented to the user before any execution can occur.

## Simulation Mode

When simulation mode is enabled, never place, modify, or cancel real orders.

Simulated execution must be clearly labeled as simulation and must not imply that a real order was submitted or filled.
