# Summarize Design Patterns

Use this workflow to analyze your Refstash references and extract recurring design patterns.

## Example Prompts

### Quick Pattern Analysis

```
Search my "Dashboard Redesign" project for references tagged "navigation". Summarize the navigation patterns used, highlighting common approaches and variations. Cite specific reference IDs.
```

### Comprehensive Design Audit

```
Fetch all references from the "Mobile Banking App" project and analyze:
1. Color schemes and branding approaches
2. Typography choices (fonts, sizes, weights)
3. Layout density and spacing
4. Component patterns (buttons, cards, forms)
5. Navigation structures

For each category, identify patterns, cite evidence from specific references, and call out any anti-patterns.
```

### Comparative Analysis

```
Search for "e-commerce" references with "checkout" and "payment" tags. Compare:
- Payment flow patterns
- Form layouts and validation
- Trust signals and security indicators
- Cart visualization approaches

Recommend the best pattern for a modern D2C brand targeting millennials.
```

### Design System Extraction

```
Fetch all "Design System" references and extract:
1. Color palette usage (primary, secondary, semantic colors)
2. Typography scale (headings, body, captions)
3. Component variants (buttons, inputs, cards)
4. Spacing and rhythm
5. Icon style and usage

Organize as a design system specification with token names and usage guidelines.
```

## Output Format

When summarizing patterns, structure your response as:

### Themes
- List 3-5 major design directions observed

### Patterns
For each pattern:
- **Name**: Descriptive name
- **Evidence**: Reference IDs showing this pattern
- **Description**: How it works
- **Frequency**: How common (rare/common/universal)

### Dos
Best practices observed across references with evidence.

### Don'ts
Anti-patterns to avoid with evidence and reasoning.

### Component Suggestions
Specific component recommendations based on the analysis.

## Tips

1. **Be specific** - Reference concrete UI elements, not general impressions
2. **Cite sources** - Include reference IDs for all claims
3. **Note variations** - Call out when patterns differ by context
4. **Consider constraints** - Ask about platform, audience, accessibility needs
5. **Stay grounded** - Base analysis on provided references only

## Example Output

```
## Themes

1. **Card-Based Layout** (80% of references)
   - References: ref_abc123, ref_def456, ref_ghi789
   - Clean separation of content with subtle shadows

2. **Minimal Navigation** (60% of references)
   - References: ref_abc123, ref_jkl012
   - Reduced to essential actions, often bottom-aligned

## Patterns

### Primary Button Style
- **Evidence**: ref_abc123, ref_def456, ref_ghi789, ref_jkl012
- **Description**: Rounded (8px), solid blue (#0066FF), white text, no border
- **Frequency**: Universal across all references

### Card Elevation
- **Evidence**: ref_abc123, ref_def456, ref_ghi789
- **Description**: Subtle box-shadow (0 2px 8px rgba(0,0,0,0.1))
- **Frequency**: Common (3/5 references)
- **Variation**: ref_mno345 uses border instead of shadow

## Dos

- ✅ Use 8px border radius for buttons and cards (ref_abc123, ref_def456, ref_ghi789)
- ✅ Limit primary actions to one per screen (all references)
- ✅ Use 16px base font size with 1.5 line height (ref_abc123, ref_def456)

## Don'ts

- ❌ Avoid rounded corners smaller than 8px (feels dated - ref_ghi789 shows outdated approach)
- ❌ Don't use more than 3 font weights (creates visual noise - observed in ref_jkl012)
- ❌ Avoid solid black borders - use subtle grays instead (ref_abc123, ref_def456)

## Component Suggestions

Based on the analysis, recommend implementing:
1. PrimaryButton with 8px border radius, #0066FF background
2. Card component with subtle shadow and 16px padding
3. Typography scale: h1 (32px), h2 (24px), body (16px), caption (14px)
4. Spacing scale: 4, 8, 16, 24, 32, 48px
```
