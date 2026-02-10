---
name: refstash
description: Fetch UI references from Refstash for design exploration, pattern analysis, and UI brief generation. Use when working on design systems, UI components, or needing visual inspiration for web/mobile interfaces.
model: sonnet
---

# Refstash Skill

Connect to Refstash to fetch curated UI references and generate design insights. This skill enables agents to access your design library and provide contextual design guidance.

## Setup

1. **Get your API token** from [Refstash Settings](https://refstash.app/settings)
2. **Set environment variable**: `export REFSTASH_API_TOKEN=your_token_here`
3. **Optional**: Create a `skills/refstash.config.json` in your project:

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

## Available Operations

### `refstash.search`

Fetch references from your Refstash projects.

**Parameters:**
- `projectId` (string, required): The project ID to search
- `tags` (string[], optional): Filter by tags
- `query` (string, optional): Free text search
- `limit` (number, optional): Max results (default: 30)

**Returns:**
```typescript
{
  references: RefstashReference[]
  resultCount: number
  projectName: string
}
```

**Example:**
```
Search my "Dashboard Redesign" project for references tagged "navigation" and "analytics". Return up to 15 results.
```

### `refstash.getReference`

Get a single reference with full details.

**Parameters:**
- `referenceId` (string, required): The reference ID

**Example:**
```
Get the full details of reference ref_abc123 including all media items and tags.
```

## Reference Schema

Each `RefstashReference` includes:

```typescript
{
  id: string
  title: string
  description: string | null
  url: string | null
  tags: string[]
  source: {
    type: "site" | "app" | "other"
    name?: string
  }
  createdAt: string (ISO)
  assets: {
    thumbnailUrl: string | null
    imageUrl: string | null
  }
  analysis: {
    colors: string[]
    typography: string[]
    layoutNotes: string[]
    uiElements: string[]
    extractedText: string[]
  }
  type: "screenshot" | "component" | "flow" | "screencast"
}
```

## Workflows

### Summarize Design Patterns

Fetch references and analyze them for recurring patterns:

```
Search the "Mobile Banking App" project and summarize the navigation patterns, color schemes, and component approaches used across the references. Cite specific reference IDs as evidence.
```

**Expected output:**
- Themes: Common design directions
- Patterns: Recurring UI patterns with evidence
- Dos: Best practices observed
- Don'ts: Anti-patterns to avoid

### Generate UI Brief

Create a structured design brief grounded in references:

```
Using the "E-commerce Checkout" project references tagged "payment", create a UI brief for a modern checkout flow. Include tone, layout principles, key screens, components, and accessibility considerations.
```

**Expected output:**
```typescript
{
  title: string
  audience: string
  tone: string[]
  layoutPrinciples: string[]
  keyScreens: string[]
  components: string[]
  contentGuidelines: string[]
  accessibilityNotes: string[]
  openQuestions: string[]
}
```

### Design System Extraction

Analyze references for design system patterns:

```
Fetch all "Design System" references and extract the button variants, form patterns, color usage, and typography scale. Organize by component type.
```

## Guidelines

1. **Always cite sources** - Include reference IDs when making claims about patterns
2. **Handle missing data gracefully** - Some references may lack analysis data
3. **Consider constraints** - Ask about mobile-first, dark mode, accessibility requirements
4. **Be specific** - Reference concrete elements from the images, not general impressions
5. **Stay grounded** - Base recommendations on the provided references, not generic advice

## Privacy Note

The Refstash skill fetches reference data from your Refstash account. All AI analysis and summarization happens locally in your agent environment - no reference data is sent back to Refstash servers.

## Error Handling

Common errors:
- `401 Unauthorized`: Check your `REFSTASH_API_TOKEN` is valid
- `403 Forbidden`: You don't have access to this project
- `404 Not Found`: Project or reference not found
- `429 Too Many Requests`: Rate limited - wait a moment before retrying

## Examples

### Finding Dashboard Inspiration

```
I'm designing a SaaS analytics dashboard. Search my "Analytics Dashboard" project for references with "charts", "tables", and "navigation" tags. Summarize the layout patterns and component approaches.
```

### Mobile App Navigation

```
Search for mobile app references with "bottom navigation" or "tab bar" tags. Compare the different approaches and recommend the best pattern for a social media app.
```

### Form Design

```
Fetch references tagged "forms" or "sign up" and analyze the form field layouts, validation patterns, and error handling approaches. Create a component checklist.
```

## Related Skills

- `compound-engineering:frontend-design` - Generate frontend code from design specs
- `superpowers:brainstorming` - Explore design directions before implementation

## Support

For issues or questions about Refstash, visit [refstash.app](https://refstash.app) or check the [documentation](https://docs.refstash.app).
