---
name: intel-digest
description: Process intelligence feeds from FOLO and other sources. Generates categorized daily digest with key insights, trends, and actionable items.
---

Generate a comprehensive intelligence digest from FOLO RSS feeds and other information sources.

## Steps
1. Access FOLO data or provided RSS feeds
2. Parse and extract articles/posts
3. Remove duplicates and low-quality content
4. Categorize by topic and priority
5. Identify key themes and patterns
6. Extract actionable insights
7. Generate structured digest report

## Processing Pipeline

### 1. Ingestion
- Read FOLO database or RSS feeds
- Parse article metadata (title, source, date, tags)
- Extract full content when available

### 2. Filtering
- Remove duplicates (same article from multiple sources)
- Filter out spam and low-quality content
- Identify high-priority items based on:
  - Source credibility
  - Topic relevance
  - Timeliness
  - Engagement metrics (if available)

### 3. Categorization
Organize content into categories:
- **Technology**: AI/ML, software, tools, infrastructure
- **Markets**: Finance, crypto, economy, trading
- **Research**: Papers, studies, breakthroughs
- **Business**: Startups, strategy, entrepreneurship
- **Personal Development**: Skills, productivity, careers
- **Other**: Uncategorized items worth reviewing

### 4. Analysis
- Identify trending topics
- Detect weak signals and emerging patterns
- Cross-reference related items
- Extract key quotes and insights

### 5. Synthesis
- Generate executive summary
- Highlight must-read items
- Create action items and follow-ups
- Suggest knowledge base entries

## Output Format

```markdown
# Daily Intelligence Digest - [Date]

## Executive Summary
[2-3 sentences summarizing the day's most important developments]

## Must-Read (Priority 1)
- [Item 1]: Brief description and why it matters
- [Item 2]: ...

## Category Summaries

### Technology & AI
- [Articles with brief takeaways]

### Markets & Finance
- [Articles with brief takeaways]

### Research & Learning
- [Articles with brief takeaways]

[... other categories ...]

## Trends & Patterns
- [Notable patterns across sources]

## Action Items
- [ ] Follow up on [topic]
- [ ] Deep dive into [article]
- [ ] Add to knowledge base: [insights]

## Statistics
- Total items processed: X
- Items by category: [breakdown]
- Sources: [list]
```

## Integration Options
- Save to daily notes in Obsidian
- Export as standalone markdown file
- Update specific knowledge base sections
- Generate follow-up research tasks

## Usage
- `/intel-digest` - Process today's feeds
- `/intel-digest --date 2024-11-14` - Specific date
- `/intel-digest --category tech` - Filter by category
- `/intel-digest --priority high` - Only high-priority items

Transform information overload into actionable intelligence.
