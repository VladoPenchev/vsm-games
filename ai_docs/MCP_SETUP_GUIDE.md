# MCP Server Setup Guide for VSM Games

## Current Status ✅
Your MCP servers have been installed and configured successfully!

### ✅ Working Servers
- **GitHub MCP Server**: Connected (needs GitHub token for full functionality)
- **Sequential Thinking MCP Server**: Connected  
- **File System MCP Server**: Connected (scoped to your project directory)
- **AWS Powertools MCP Server**: Connected (configured with SSO profile)
- **AWS General MCP Server**: Connected (DynamoDB, Lambda, API Gateway access)

### ⚠️ Needs Minor Setup
- **Git MCP Server**: Installation issue (not critical - GitHub server provides repository functionality)

### 🔧 Configured Environment
- **AWS Profile**: amplify-policy-191687650583 (SSO)
- **AWS Region**: eu-north-1
- **Project Path**: /home/vlado/development/vsm-games

## Next Steps

### 1. GitHub Configuration (Optional but Recommended)
To enable full GitHub functionality:
1. Go to https://github.com/settings/tokens
2. Create a Personal Access Token with repo permissions
3. Add to your environment or Claude Code settings

### 2. AWS Configuration (Required for AWS servers)
Since your project deploys to AWS via GitHub, you'll need AWS credentials:

```bash
# Install AWS CLI if not already installed
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install

# Configure AWS credentials
aws configure
# Enter your Access Key ID, Secret Access Key, Region (e.g., us-east-1), output format (json)
```

### 3. Environment Variables
Add these to your shell profile (~/.bashrc or ~/.zshrc):
```bash
export AWS_REGION=us-east-1  # or your preferred region
export GITHUB_TOKEN=your_github_token_here
```

## What Each Server Does

### GitHub & Git
- **GitHub**: Repository management, deployment monitoring, issues/PRs
- **Git**: Local repository operations, commit history, branch management

### AWS Servers
- **AWS Core**: Foundation for all AWS operations
- **AWS Cost**: Track spending from your GitHub deployments
- **AWS API**: Direct AWS service interactions
- **Amplify Data**: Natural language queries on your todo app data

### Development Helpers
- **Sequential Thinking**: Break complex tasks into steps
- **File System**: Enhanced file operations within your project

## Testing Your Setup

After configuring credentials, restart Claude Code and run:
```bash
claude mcp list
```

All servers should show ✓ Connected status.

## Usage Examples

You can now use these natural language commands:

### AWS Operations
- "List my Lambda functions in eu-north-1"
- "Show me DynamoDB tables for this project"
- "Check AWS service costs and usage"
- "Get Lambda function logs for my amplify backend"

### GitHub & Repository
- "Show me recent commits and their status"  
- "Check the deployment status of my last GitHub commit"
- "List open issues and pull requests"
- "Show me repository statistics"

### File & Project Management
- "List files in my project directory"
- "Read the contents of my App.tsx file"
- "Show me the project structure"
- "Create a new component file"

### Development Workflow
- "Break down this complex task into steps" (Sequential Thinking)
- "Help me plan the implementation of a new feature"
- "Guide me through AWS Amplify best practices"

## Your Working MCP Servers

Run `claude mcp list` to see all connected servers:
- ✅ github: Repository management and deployment monitoring
- ✅ sequential-thinking: Complex task planning and breakdown  
- ✅ filesystem: Local file operations within your project
- ✅ aws-powertools: AWS Lambda Powertools documentation and guidance
- ✅ aws-general: Direct AWS service interactions (DynamoDB, Lambda, API Gateway)