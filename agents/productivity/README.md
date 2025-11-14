# Productivity Agents

Specialized agents for knowledge management, information synthesis, and productivity workflows.

## Available Agents

### `knowledge-curator`
**Obsidian knowledge base management specialist**

Maintains and optimizes your Obsidian vault with:
- Note organization and folder structure design
- Bidirectional linking and knowledge graphs
- Tag taxonomy and metadata systems
- Orphaned note identification and link gardening
- Template creation and workflow automation

**Use when:**
- Organizing or restructuring your knowledge base
- Identifying broken links or orphaned notes
- Creating note templates and metadata systems
- Building MOCs (Maps of Content)
- Implementing Zettelkasten or PARA methods

### `intelligence-synthesizer`
**Intelligence gathering and synthesis specialist**

Processes information from multiple sources into actionable insights:
- RSS feed aggregation and processing (FOLO integration)
- Pattern recognition and trend identification
- Signal vs noise filtering
- Multi-source cross-referencing
- Daily intelligence digests
- Categorized reports and summaries

**Use when:**
- Processing daily intelligence feeds from FOLO
- Generating intelligence digests from multiple sources
- Identifying emerging trends and weak signals
- Creating categorized content summaries
- Extracting actionable insights from information streams

## Integration with Your Workflows

### Obsidian + Claude Code
Use `knowledge-curator` to:
1. Maintain vault health (broken links, orphans)
2. Design and implement note templates
3. Build knowledge graph connections
4. Organize literature and research notes

### FOLO + Intelligence Gathering
Use `intelligence-synthesizer` to:
1. Process daily RSS feeds
2. Generate categorized intelligence digests
3. Identify high-priority items
4. Create action items and follow-ups
5. Update knowledge base with insights

## Best Practices

### For Knowledge Curation
- Run regular vault maintenance (weekly/monthly)
- Use consistent frontmatter and metadata
- Implement atomic notes (one idea per note)
- Build hub notes for major topics
- Leverage dataview for dynamic queries

### For Intelligence Synthesis
- Process feeds daily for best results
- Use consistent categorization schemes
- Filter signal from noise aggressively
- Create action items from insights
- Archive digests in dated daily notes

## Example Commands

```bash
# Use knowledge curator for vault maintenance
/agent knowledge-curator "Analyze my vault and suggest improvements"

# Use intelligence synthesizer for daily digest
/agent intelligence-synthesizer "Generate today's intelligence digest from FOLO feeds"
```

## Related Commands

- `/kb-sync` - Automated knowledge base maintenance
- `/intel-digest` - Generate intelligence digest from feeds
- `/research-summary` - Summarize research papers for knowledge base

## Resources

- [Obsidian Documentation](https://help.obsidian.md/)
- [FOLO GitHub](https://github.com/RSSNext/Folo)
- [Zettelkasten Method](https://zettelkasten.de/)
- [PARA Method](https://fortelabs.com/blog/para/)
