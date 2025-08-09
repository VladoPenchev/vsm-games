# Claude Code Restart Instructions

## To Apply MCP Server Changes

MCP servers require a restart of Claude Code to be properly loaded and recognized.

### How to Restart Claude Code:

1. **Exit Claude Code completely**
   - Use `Ctrl+C` or close the terminal/application completely
   - Make sure no Claude Code processes are running

2. **Restart Claude Code**
   - Reopen your terminal
   - Navigate to your project: `cd /home/vlado/development/vsm-games`
   - Run: `claude`

3. **Verify MCP Servers**
   - After restart, run `/mcp` command
   - You should now see all 5 MCP servers:
     - github
     - sequential-thinking  
     - filesystem
     - aws-powertools
     - aws-general

### Expected Result After Restart:
All 5 MCP servers should be visible and connected in the `/mcp` command interface, allowing you to use natural language commands for AWS operations, GitHub management, file operations, and development planning.

### If Still Having Issues:
Run `claude mcp list` to verify connectivity from command line vs the `/mcp` interface.