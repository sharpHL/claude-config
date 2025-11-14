# Workflow Commands

Daily workflow automation commands for algorithm engineering, knowledge management, and productivity.

## Available Commands

### `/daily-market-brief`
**Generate comprehensive market analysis briefs**

Creates structured market analysis based on time of day (morning/midday/evening):
- Morning: Pre-market analysis, key levels, economic calendar
- Midday: Intraday trends, volume analysis, sector performance
- Evening: Day recap, technical updates, tomorrow's outlook

**Usage:**
```bash
/daily-market-brief              # Auto-detect time
/daily-market-brief morning      # Morning brief
/daily-market-brief evening      # Evening summary
```

**Integrations:**
- 52etf.site data analysis
- Custom market data sources
- Save to daily notes

---

### `/kb-sync`
**Obsidian knowledge base maintenance**

Comprehensive vault analysis and maintenance:
- Find orphaned notes and broken links
- Analyze tag usage and metadata
- Suggest folder reorganization
- Generate health reports with action items

**Usage:**
```bash
/kb-sync                  # Full analysis + report
/kb-sync --fix           # Auto-fix obvious issues
/kb-sync --report-only   # Report without changes
```

**Features:**
- Link health analysis
- Content organization suggestions
- Metadata quality checks
- Knowledge graph optimization

---

### `/intel-digest`
**Intelligence feed processing and synthesis**

Process RSS feeds from FOLO and other sources into actionable intelligence:
- Categorize by topic (Tech, Markets, Research, Business, etc.)
- Filter signal from noise
- Identify trends and patterns
- Generate executive summaries

**Usage:**
```bash
/intel-digest                        # Process today's feeds
/intel-digest --date 2024-11-14     # Specific date
/intel-digest --category tech       # Filter by category
/intel-digest --priority high       # High-priority only
```

**Output:**
- Daily intelligence digest
- Categorized summaries
- Must-read items
- Action items and follow-ups

**Integrations:**
- FOLO RSS feeds
- Custom RSS sources
- Save to Obsidian daily notes

---

### `/research-summary`
**AI/ML research paper analysis**

Analyze academic papers and generate structured summaries:
- Extract key contributions and methodology
- Summarize experimental results
- Assess practical applicability
- Create Obsidian knowledge base entries

**Usage:**
```bash
/research-summary [paper-url]      # From arXiv or URL
/research-summary [paper.pdf]      # From PDF file
/research-summary --topic LLM      # Focus on specific aspects
```

**Output:**
- Structured Obsidian note with:
  - TL;DR summary
  - Problem & approach
  - Methodology & results
  - Strengths & limitations
  - Personal notes & implementation ideas
  - Related work links

**Use Cases:**
- Stay current with AI/ML research
- Build research knowledge base
- Identify implementation opportunities

---

### `/algo-benchmark`
**Algorithm performance benchmarking**

Comprehensive algorithm analysis and profiling:
- Time/space complexity analysis
- Performance across input sizes
- Comparative benchmarking
- Profiling and bottleneck identification

**Usage:**
```bash
/algo-benchmark my_sort.py                          # Benchmark file
/algo-benchmark --function quick_sort               # Specific function
/algo-benchmark --compare "bubble,merge,quick"      # Compare algorithms
/algo-benchmark --max-size 1000000                  # Test up to 1M elements
/algo-benchmark --profile memory                    # Focus on memory
```

**Features:**
- Empirical complexity analysis
- Time vs input size plots
- Memory profiling
- Comparative analysis reports
- Performance recommendations

**Output:**
- Detailed benchmark report
- Visualizations (time/memory curves)
- Bottleneck analysis
- Optimization suggestions

---

## Workflow Integration

### Daily Routine Example
```bash
# Morning
/daily-market-brief morning          # Get market overview
/intel-digest --priority high        # Check important news

# During Work
/algo-benchmark new_algorithm.py     # Test new implementation
/research-summary https://arxiv...   # Analyze interesting paper

# Evening
/daily-market-brief evening          # Market recap
/kb-sync                             # Maintain knowledge base
/intel-digest                        # Full daily digest
```

### Knowledge Management Workflow
```bash
# Process research papers
/research-summary paper.pdf

# Synthesize intelligence
/intel-digest --category research

# Maintain vault
/kb-sync --fix

# Result: Organized, up-to-date knowledge base
```

### Algorithm Engineering Workflow
```bash
# Develop algorithm
# (write code)

# Benchmark performance
/algo-benchmark --compare "v1,v2,optimized"

# Document findings
# (results saved to benchmarks/)

# Result: Data-driven optimization decisions
```

## Tips & Best Practices

### Market Analysis
- Run morning brief before market open
- Use midday updates for intraday adjustments
- Review evening summary for next day planning
- Save briefs to dated notes for historical reference

### Knowledge Management
- Run `/kb-sync` weekly for vault health
- Use `/intel-digest` daily for information synthesis
- Create templates for recurring note types
- Build MOCs (Maps of Content) for major topics

### Research Tracking
- Process papers immediately when discovered
- Tag papers by topic and relevance
- Link to related work in knowledge base
- Track implementation ideas separately

### Algorithm Development
- Benchmark before and after optimization
- Test with varying input sizes
- Compare against theoretical complexity
- Version control benchmark results

## Related Agents

These commands work well with specialized agents:
- `etf-market-analyst` - For market analysis
- `knowledge-curator` - For Obsidian management
- `intelligence-synthesizer` - For feed processing
- `research-digest` - For paper analysis
- `algorithm-engineer` - For algorithm optimization

## Customization

You can modify these commands to fit your specific workflows:
1. Edit command files in `/commands/workflow/`
2. Adjust output formats and structures
3. Add integrations with your tools
4. Customize categorization schemes

See individual command files for detailed implementation.
