# MCP Servers Configuration

This directory contains Model Context Protocol (MCP) server configurations for the claude-config toolkit. The servers are automatically configured via npm packages.

## 🚀 Configured Servers

### 1. Context7
- **Package**: `@context7/mcp-server`
- **Transport**: STDIO
- **Purpose**: Enhanced context management and information retrieval
- **Auto-Configured**: ✅ Yes

### 2. Chrome DevTools
- **Package**: `chrome-devtools-mcp`
- **Transport**: STDIO
- **Purpose**: Browser automation, debugging, and web scraping
- **Auto-Configured**: ✅ Yes

### 3. Sequential Thinking
- **Package**: `@modelcontextprotocol/server-sequential-thinking`
- **Transport**: STDIO
- **Purpose**: Structured reasoning and step-by-step problem solving
- **Auto-Configured**: ✅ Yes

## 📁 Directory Structure

```
mcp-servers/
├── README.md          # This file
└── .mcp.json         # MCP server configuration
```

## 🔧 Automatic Configuration

### Prerequisites
- Claude Code CLI (>= 2024.10)
- Node.js and npm (for MCP package execution)

### Setup Process
The MCP servers are automatically configured when the plugin is installed:

1. **Package Installation**: npm packages are installed automatically
2. **Server Configuration**: `.mcp.json` configures the servers
3. **Auto-Detection**: Claude Code automatically detects and loads the servers

### No Manual Installation Required
- ❌ No `claude mcp add` commands needed
- ❌ No manual server configuration
- ✅ Everything works out-of-the-box

### Verification
To verify MCP servers are working:

```bash
# Check if MCP servers are detected
claude --help | grep -i mcp

# Test MCP functionality during usage
# The servers will be automatically available when needed
```

## 🎯 Usage

### With Context7
```
Use Context7 for enhanced context management and information retrieval.
```

### With Chrome DevTools
```
Use Chrome DevTools MCP for browser automation, debugging, and web scraping tasks.
```

### With Sequential Thinking
```
Use Sequential Thinking for structured reasoning and step-by-step problem solving.
```

## 🎯 Usage with Claude Code

### With Context7
```
Use Context7 to search for relevant information and provide better context for responses.
```

### With Chrome DevTools
```
Use Chrome DevTools MCP to automate browser interactions and debug web applications.
```

### With Sequential Thinking
```
Use Sequential Thinking for structured problem-solving and step-by-step analysis.
```

## 📋 Integration with Existing Tools

### With Git Flow Commands
```bash
/git:feature browser-automation
# Then use Chrome DevTools MCP for web automation
```

### With Agents
```
Use the data-scientist agent with Context7 for enhanced data analysis and insights.
```

## 🛠️ Configuration Details

The `.mcp.json` file contains:
- Server configurations with proper command structures
- Installation commands for easy setup
- Descriptions and usage notes
- Transport type specifications (SSE for Context7)

## 🔍 Server Capabilities

### Context7
- Enhanced context retrieval and management
- Information synthesis and organization
- Knowledge base integration

### Chrome DevTools
- Browser automation and control
- Web page interaction and scraping
- Debugging and development tools

### Sequential Thinking
- Structured reasoning processes
- Step-by-step problem decomposition
- Logical thinking frameworks

## 📚 Resources

- [Context7 Documentation](https://context7.com/)
- [Chrome DevTools MCP](https://github.com/modelcontextprotocol/servers)
- [Sequential Thinking MCP](https://github.com/modelcontextprotocol/server-sequential-thinking)
- [Claude Code MCP Integration](https://docs.claude.com/en/docs/claude-code/mcp)

## 🛠️ Troubleshooting

### Common Issues
1. **Server not found**: Run the installation commands first
2. **Permission issues**: Ensure Claude CLI has proper permissions
3. **Network issues**: Check internet connection for Context7
4. **Package issues**: Update npm and reinstall packages

### Debug Commands
```bash
# List available MCP servers
claude mcp list

# Check MCP server status
claude mcp status

# Test individual servers
claude mcp test context7
claude mcp test chrome-devtools
claude mcp test thinking
```