---
name: daily-market-brief
description: Generate comprehensive market analysis brief (morning/midday/evening) from market data. Analyzes ETF performance, trends, and generates actionable insights.
---

Generate a comprehensive market analysis brief based on the time of day and available market data.

## Steps
1. Determine the briefing type (morning/midday/evening) based on current time or user input
2. Fetch or analyze market data from provided sources (52etf.site or user-provided data)
3. Calculate key technical indicators and metrics
4. Identify trends, support/resistance levels, and notable moves
5. Generate structured brief with actionable insights

## Brief Structure

### Morning Brief (Pre-Market)
- Overnight developments and futures
- Key levels to watch today
- Economic calendar and events
- Sector outlooks
- Trading plan considerations

### Midday Update
- Morning price action analysis
- Volume and momentum assessment
- Intraday trend confirmation
- Notable sector rotations
- Afternoon outlook

### Evening Summary
- Day's performance recap
- Volume analysis and notable moves
- Technical level updates
- Risk assessment
- Tomorrow's setup and key levels

## Output Format
Provide analysis in markdown format with:
- Clear sections for each category
- Key metrics in tables
- Risk warnings where appropriate
- Actionable takeaways
- Optional: Save to designated notes location

## Usage Examples
- `/daily-market-brief` - Auto-detect time and generate appropriate brief
- `/daily-market-brief morning` - Generate morning pre-market brief
- `/daily-market-brief evening` - Generate end-of-day summary

Focus on objective analysis with appropriate risk disclaimers.
