# 🚀 Context Control MCP - Setup Guide

## Quick Setup

### 1. Install Dependencies
```bash
npm install
```

### 2. Initialize Project Context
```bash
# Create .claude directory for context files
mkdir -p .claude

# Create initial meta-context.md
cat > .claude/meta-context.md << 'EOF'
# Meta-Context - Your Project Name
*Updated: $(date '+%Y-%m-%d') | Context Control MCP v1.0*

## Project Overview
- **Tech Stack**: [Your stack here]
- **Current Phase**: Initial setup
- **Goals**: [Your project goals]

## Next Priorities
1. Configure Context Control MCP
2. Set up git hooks
3. Start development tracking
EOF

# Create empty session log
touch .claude/session-log.jsonl
```

### 3. Configure MCP Server
Create `mcp-config.json`:
```json
{
  "mcpServers": {
    "context-control": {
      "command": "node",
      "args": ["./context-control-server.js"],
      "description": "Context Control MCP - Git-powered context management"
    }
  }
}
```

### 4. Set Up Git Hooks
```bash
npm run hooks
```

## Available Commands

```bash
# Start MCP server
npm run start

# Get smart resume briefing
npm run resume

# View metrics dashboard  
npm run dashboard

# Check roadmap status
npm run status

# Install git hooks
npm run hooks
```

## Integration with Claude

Add to your Claude MCP configuration:
```json
{
  "context-control": {
    "command": "node",
    "args": ["/path/to/context-control-server.js"]
  }
}
```

## File Structure

```
your-project/
├── .claude/
│   ├── meta-context.md      # Auto-updated project context
│   └── session-log.jsonl    # Session history + metrics  
├── context-control-server.js
├── mcp-config.json
└── package.json
```

## Troubleshooting

1. **Server won't start**: Check Node.js version (>=18.0.0 required)
2. **Git hooks not working**: Run `chmod +x .git/hooks/*`
3. **Context files missing**: Run the initialization commands above

For issues: https://github.com/diazpolanco13/context-control-mcp/issues