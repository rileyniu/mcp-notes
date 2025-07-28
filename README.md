# MCP Notes

A repository for Model Context Protocol (MCP) agent configurations and documentation.

## Contents

- **[configs/agents/playwright-browser.json](configs/agents/playwright-browser.json)** - Playwright browser automation agent configuration
- **[docs/playwright-capabilities.md](docs/playwright-capabilities.md)** - Complete guide to Playwright MCP server capabilities and examples

## Setup and Usage

### 1. Create and Activate Python Virtual Environment

```bash
# Create virtual environment
python3 -m venv mcp_env

# Activate virtual environment
source mcp_env/bin/activate

# You should see (mcp_env) in your prompt
```

### 2. Install Requirements

```bash
# Install Hugging Face Hub with MCP support
pip install "huggingface_hub[mcp]>=0.32.0"

# Install npx for running MCP servers
npm install -g npx
```

### 3. Login to Hugging Face

```bash
# Login to Hugging Face Hub (you'll need a token)
huggingface-cli login
```

Get your token from: https://huggingface.co/settings/tokens

### 4. Run the Playwright Browser Agent

```bash
# Run the agent with browser automation capabilities
tiny-agents run configs/agents/playwright-browser.json
```

## What You Can Do

Once the agent is running, you can perform browser automation tasks like:

- **Web navigation**: "Go to google.com and search for 'Python tutorials'"
- **Data extraction**: "Visit hacker news and get the top 5 story titles"
- **Screenshots**: "Take a screenshot of the current page"
- **Form filling**: "Fill out the contact form with my information"
- **Multi-tab browsing**: "Open 3 tabs with different news websites"

See [docs/playwright-capabilities.md](docs/playwright-capabilities.md) for detailed capabilities and example workflows.

## Exiting the Agent

To stop the agent, press:
```bash
Ctrl + C
```

To deactivate the virtual environment:
```bash
deactivate
```
