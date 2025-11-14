---
name: kb-sync
description: Sync and organize Obsidian knowledge base. Identifies orphaned notes, broken links, suggests improvements, and maintains knowledge graph health.
---

Perform comprehensive knowledge base maintenance and organization for your Obsidian vault.

## Steps
1. Scan the knowledge base directory structure
2. Identify orphaned notes (no incoming/outgoing links)
3. Find broken links and missing references
4. Analyze tag usage and suggest taxonomy improvements
5. Check for duplicate or similar content
6. Suggest folder reorganization if needed
7. Identify notes that need updates or review
8. Generate maintenance report

## Analysis Categories

### Link Health
- Broken links and their locations
- Orphaned notes without connections
- Highly connected hub notes
- Suggested bidirectional links

### Content Organization
- Notes missing tags or metadata
- Inconsistent naming conventions
- Duplicate or overlapping content
- Notes that should be merged or split

### Metadata Quality
- Missing or incomplete frontmatter
- Inconsistent tag usage
- Date and timestamp gaps
- Source attribution needed

### Suggestions
- New MOC (Map of Content) opportunities
- Template standardization
- Folder structure improvements
- Automation opportunities

## Output
Generate a markdown report with:
1. **Summary Statistics**: Total notes, links, orphans, etc.
2. **Action Items**: Prioritized list of fixes
3. **Opportunities**: Suggested improvements
4. **Health Score**: Overall knowledge base quality metric

Optionally execute fixes automatically with user confirmation.

## Usage
- `/kb-sync` - Full analysis and report
- `/kb-sync --fix` - Auto-fix obvious issues
- `/kb-sync --report-only` - Generate report without changes

Help maintain a healthy, discoverable knowledge base.
