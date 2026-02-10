# Refstash Agent Skill

Fetch UI references from Refstash for design exploration, pattern analysis, and UI brief generation.

## About Refstash

[Refstash](https://refstash.app) is a Progressive Web App for designers and developers to collect, organize, and manage UI references with AI-powered features. This skill enables agents to access your curated design library.

## Installation

```
npx skills add refstash/skills
```

Or for Claude Code specifically:

```
/plugin marketplace add refstash/skills
/plugin install refstash@refstash-skills
```

## Setup

1. Create an account at [refstash.app](https://refstash.app)
2. Generate an API token in Settings
3. Set the environment variable:

```bash
export REFSTASH_API_TOKEN=your_token_here
```

Or add to your `.env` file:

```
REFSTASH_API_TOKEN=your_token_here
```

## Usage

The skill provides two main operations:

### `refstash.search`

Fetch references from your projects:

```
Search my "Dashboard Redesign" project for references tagged "navigation" and "analytics". Return up to 15 results.
```

### `refstash.getReference`

Get a single reference with full details:

```
Get the full details of reference ref_abc123 including all media items and tags.
```

### Design Pattern Analysis

```
Fetch all references from the "Mobile Banking App" project and analyze the navigation patterns, color schemes, and component approaches. Cite specific reference IDs as evidence.
```

### UI Brief Generation

```
Using the "E-commerce Checkout" project references tagged "payment", create a UI brief for a modern checkout flow. Include tone, layout principles, key screens, components, and accessibility considerations.
```

## Configuration (Optional)

Create `skills/refstash.config.json` in your project:

```json
{
  "refstash": {
    "baseUrl": "https://refstash.app",
    "apiTokenEnv": "REFSTASH_API_TOKEN",
    "defaultProjectId": "proj_xxx",
    "defaultTags": ["dashboard", "saas"],
    "defaultLimit": 30
  }
}
```

## Reference Schema

Each reference includes:

- **id**: Unique identifier
- **title**: Reference title
- **description**: Optional description
- **url**: Source URL
- **tags**: Array of tag names
- **source**: Type and name of source app/site
- **assets**: Image URLs
- **analysis**: AI-extracted design data (colors, typography, layout notes, etc.)
- **type**: screenshot, component, flow, or screencast

## Workflows

The skill supports common design workflows:

1. **Summarize Design Patterns** - Analyze references for recurring UI patterns
2. **Generate UI Brief** - Create structured design specifications
3. **Design System Extraction** - Extract component libraries and design tokens
4. **Comparative Analysis** - Compare different approaches across references

## Privacy

- Reference data is fetched from your Refstash account
- All AI analysis happens locally in your agent environment
- No reference data is sent back to Refstash servers

## Examples

See the `examples/` directory for detailed prompt templates:

- `examples/summarize.md` - Design pattern analysis workflows
- `examples/brief.md` - UI brief generation workflows

## Support

- Website: [refstash.app](https://refstash.app)
- Documentation: [docs.refstash.app](https://docs.refstash.app)
- Issues: [github.com/refstash/refstash-skill](https://github.com/refstash/refstash-skill/issues)

## License

MIT License - see [LICENSE](LICENSE) for details.
