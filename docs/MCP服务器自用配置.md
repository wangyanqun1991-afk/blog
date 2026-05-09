# MCP 服务器配置

```json
{
  "mcpServers": {
    "chrome-devtools": {
      "//": "Chrome DevTools 浏览器自动化调试",
      "disabled": false,
      "timeout": 60,
      "type": "stdio",
      "command": "npx",
      "args": [
        "chrome-devtools-mcp@latest",
        "--autoConnect",
        "-y",
        "--channel=stable"
      ]
    },
    "js-reverse": {
      "//": "JavaScript 逆向分析",
      "disabled": false,
      "timeout": 60,
      "type": "stdio",
      "command": "npx",
      "args": [
        "js-reverse-mcp",
        "--autoConnect"
      ]
    },
    "github": {
      "//": "GitHub API 操作（Token 已擦除）",
      "command": "npx",
      "args": ["-y", "@github/github-mcp-server"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "<your-github-token>"
      }
    },
    "mcp-git-ingest": {
      "//": "Git 仓库代码分析",
      "command": "uvx",
      "args": ["--from", "git+https://github.com/adhikasp/mcp-git-ingest", "mcp-git-ingest"]
    },
    "gitmcp": {
      "//": " github MCP 代码读取",
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://gitmcp.io/{owner}/{repo}"
      ]
    },
    "claude-context": {
      "//": "基于claude-上下文管理（API Key 已擦除 按照openAI的格式填写deepseek即可）",
      "command": "npx",
      "args": ["-y", "@zilliz/claude-context-mcp@latest"],
      "env": {
        "OPENAI_API_KEY": "<your-openai-api-key>",
        "OPENAI_BASE_URL": "https://api.deepseek.com",
        "EMBEDDING_MODEL": "deepseek-v4-flash",
        "MILVUS_TOKEN": "<your-zilliz-token>"
      }
    }
  }
}
```

