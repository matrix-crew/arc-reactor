# Arc Reactor

A collection of useful Claude Code plugins by matrix-crew, including both custom-built and curated external plugins.

## Quick Start

```bash
/plugin marketplace add matrix-crew/arc-reactor

/plugin install <plugin-name>
```

## Plugins

| Plugin | Category | Description |
| ------ | -------- | ----------- |
| [project-management](#project-management) | Management | Project initialization, status tracking, and planning |
| [quality-assurance](#quality-assurance) | QA | Exploratory testing and systematic bug discovery |
| [cloudflare-docs](#cloudflare-docs) | Documentation | Cloudflare documentation access and search |
| [cloudflare-observability](#cloudflare-observability) | Monitoring | Cloudflare observability and monitoring tools |
| [cloudflare-workers-bindings](#cloudflare-workers-bindings) | Development | Cloudflare Workers bindings management |
| [cloudflare-workers-builds](#cloudflare-workers-builds) | Deployment | Cloudflare Workers build and deployment tools |
| [context7](#context7) | Development | Up-to-date documentation lookup from source repositories |
| [filesystem](#filesystem) | Development | Filesystem operations and file management |
| [firecrawl](#firecrawl) | Integration | Web scraping and search capabilities |
| [magic](#magic) | Utility | AI-driven UI component creation |
| [memory](#memory) | Utility | Knowledge graph-based persistent memory |
| [n8n](#n8n) | Integration | n8n workflow creation and management |
| [sequential-thinking](#sequential-thinking) | Utility | Dynamic and reflective problem-solving |
| [serena](#serena) | Development | Professional coding agent with semantic tools |
| [vercel](#vercel) | Deployment | Vercel deployments and projects |

## Plugin Details

### project-management

Project management tools for kickoff, status tracking, and feature planning.

**Skills (auto-triggered):**
- **Kickoff** - Activates on "start a new project", "design a new app", "create a project spec". Runs a 6-phase process (discovery → architecture → UI/UX → risk → kickoff.md → bootstrap) and outputs `specifications/kickoff.md`
- **Ideation** - Activates on "suggest features", "what should I build next", "what's missing in this project". Analyzes the codebase and competitors to surface feature ideas
- **Planning** - Activates on "plan this feature", "write a technical spec", "how should I architect this". Produces detailed tech spec, design decisions, risk analysis, and task breakdown

**Usage:**

```
# Skills trigger automatically:
# "Let's design a new SaaS app"
# "What features should I add next?"
# "Write a technical spec for the payment system"
```

### quality-assurance

Quality assurance tools for exploratory testing and systematic bug discovery.

**Skills (auto-triggered):**
- **Exploratory Testing** - Activates on "find edge cases", "what could go wrong", "explore this code for bugs"

**Usage:**

```
# Skills trigger automatically:
# "What edge cases could break this code?"
# "Explore this feature for bugs"
```

### cloudflare-docs

Access and search Cloudflare documentation directly from Claude Code.

**Homepage:** [Cloudflare MCP Documentation](https://developers.cloudflare.com/agents/model-context-protocol/)

### cloudflare-observability

Monitor and observe your Cloudflare infrastructure with integrated observability tools.

**Homepage:** [Cloudflare MCP Documentation](https://developers.cloudflare.com/agents/model-context-protocol/)

### cloudflare-workers-bindings

Manage Cloudflare Workers bindings including KV namespaces, Durable Objects, and more.

**Homepage:** [Cloudflare MCP Documentation](https://developers.cloudflare.com/agents/model-context-protocol/)

### cloudflare-workers-builds

Build and deploy Cloudflare Workers with integrated CI/CD tools.

**Homepage:** [Cloudflare MCP Documentation](https://developers.cloudflare.com/agents/model-context-protocol/)

### context7

Pull version-specific documentation and code examples directly from source repositories into your LLM context using Upstash Context7.

**Homepage:** [Context7 Documentation](https://context7.com/docs/clients/claude-code)

### filesystem

Perform filesystem operations including reading, writing, searching, and managing files and directories.

**Homepage:** [MCP Filesystem Server](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem)

### firecrawl

Web scraping and search capabilities powered by Firecrawl for extracting structured data from websites.

**Homepage:** [Firecrawl MCP Server](https://docs.firecrawl.dev/mcp-server)

### magic

AI-driven tool that helps developers create beautiful, modern UI components instantly through natural language descriptions.

**Homepage:** [Magic MCP](https://github.com/21st-dev/magic-mcp)

### memory

Knowledge graph-based persistent memory system that helps maintain context across conversations.

**Homepage:** [MCP Memory Server](https://github.com/modelcontextprotocol/servers/tree/main/src/memory)

### n8n

n8n workflow creation and management with AI support. Search nodes, validate workflows, manage templates, and create workflows efficiently.

**Homepage:** [n8n MCP Server](https://github.com/czlonkowski/n8n-mcp)

### sequential-thinking

Dynamic and reflective problem-solving with structured thinking processes for complex tasks.

**Homepage:** [MCP Sequential Thinking Server](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking)

### serena

Professional coding agent with semantic coding tools for intelligent file operations, symbol-level editing, and memory management.

**Homepage:** [Serena](https://github.com/oraios/serena)

### vercel

Manage Vercel deployments, projects, and infrastructure directly from Claude Code.

**Homepage:** [Vercel MCP Documentation](https://vercel.com/docs/mcp/vercel-mcp)

## Project Structure

```
arc-reactor/
├── .claude-plugin/
│   └── marketplace.json       # Marketplace configuration
├── external_plugins/          # Curated external plugins
│   ├── cloudflare-docs/
│   ├── cloudflare-observability/
│   ├── cloudflare-workers-bindings/
│   ├── cloudflare-workers-builds/
│   ├── context7/
│   ├── filesystem/
│   ├── firecrawl/
│   ├── magic/
│   ├── memory/
│   ├── n8n/
│   ├── sequential-thinking/
│   ├── serena/
│   └── vercel/
├── plugins/
│   ├── project-management/       # Project management plugin
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   └── skills/
│   │       ├── kickoff/
│   │       │   └── SKILL.md
│   │       ├── ideation/
│   │       │   └── SKILL.md
│   │       └── planning/
│   │           └── SKILL.md
│   └── quality-assurance/              # QA tools plugin
│       ├── .claude-plugin/
│       │   └── plugin.json
│       └── skills/
│           └── exploratory-testing/
│               └── SKILL.md
├── LICENSE
└── README.md
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](LICENSE) file for details.
