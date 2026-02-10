# Generate UI Brief

Use this workflow to create a structured UI design brief grounded in your Refstash references.

## Example Prompts

### Feature Brief

```
Using my "Social Media App" project references tagged "onboarding" and "sign up", create a UI brief for a modern mobile onboarding flow. Target audience: Gen Z users. Tone: friendly, energetic, and approachable.
```

### Component Brief

```
Fetch references tagged "data visualization" and "charts". Create a UI brief for an analytics dashboard component library. Include chart types, color schemes, and interaction patterns.
```

### Page Brief

```
Search the "E-commerce" project for "product listing" and "grid" references. Generate a UI brief for a product catalog page that works on both mobile and desktop.
```

### Design System Brief

```
Using all references from the "Design System" project, create a comprehensive design system brief covering color, typography, components, and usage guidelines.
```

## Brief Structure

### Title
Clear, descriptive name for the feature/interface

### Audience
Who is this for? (demographics, tech-savviness, context of use)

### Tone
- List 3-5 adjectives describing the feeling
- Examples: friendly, professional, playful, minimal, trustworthy

### Layout Principles
Key structural patterns:
- Grid system
- Hierarchy and spacing
- Responsive behavior
- Content organization

### Key Screens
For each screen:
- Purpose
- Content priorities
- Key actions
- Reference examples

### Components
Component recommendations:
- Component name
- Description
- States (default, hover, active, disabled)
- Reference examples

### Content Guidelines
- Voice and tone
- Label conventions
- Error messaging
- Help text patterns

### Accessibility Notes
- WCAG compliance considerations
- Screen reader support
- Keyboard navigation
- Color contrast

### Open Questions
Unresolved decisions that need stakeholder input

## Tips

1. **Ground in references** - Cite specific examples from your library
2. **Be specific** - Provide concrete guidance, not abstractions
3. **Consider context** - Think about user scenarios and constraints
4. **Highlight tradeoffs** - Explain why certain approaches were chosen
5. **Stay focused** - Keep recommendations aligned with the brief's scope

## Example Output

```
# Mobile Onboarding Flow - UI Brief

## Audience
Gen Z users (18-24), tech-savvy, mobile-first, expect personalization and visual appeal. Context: Downloading app for first time, possibly from social media ad.

## Tone
- Friendly and approachable
- Energetic and optimistic
- Modern and trendy
- Simple and straightforward
- Personal and customized

## Layout Principles

Based on ref_abc123, ref_def456, ref_ghi789:

1. **Single focus per screen** - One primary action, minimal distractions
2. **Generous whitespace** - 24-32px padding, comfortable breathing room
3. **Bottom-aligned primary actions** - Within thumb reach (ref_def456, ref_ghi789)
4. **Progressive disclosure** - Information revealed step-by-step (ref_abc123)
5. **Vertical stack** - Single column, left-aligned content (universal pattern)

## Key Screens

### Screen 1: Welcome
- **Purpose**: Set expectations and create positive first impression
- **Content**: Logo, tagline, "Get Started" CTA
- **Actions**: Primary: "Get Started", Secondary: "I already have an account"
- **References**: ref_abc123 (friendly illustration), ref_def456 (video preview)

### Screen 2: Value Props
- **Purpose**: Show benefits, not features
- **Content**: 3 scrolling cards with icons + short descriptions
- **Actions**: Swipeable carousel, "Continue" at bottom
- **References**: ref_def456 (carousel pattern), ref_ghi789 (card animations)

### Screen 3: Interests Selection
- **Purpose**: Personalize content recommendations
- **Content**: Grid of selectable interest tags with chips
- **Actions**: Multi-select, "Continue" enabled when 3+ selected
- **References**: ref_ghi789 (tag selection UI), ref_jkl012 (selection feedback)

### Screen 4: Permissions
- **Purpose**: Request necessary permissions with context
- **Content**: Permission requests with "why this matters" explanations
- **Actions**: "Allow" / "Not Now" for each
- **References**: ref_abc123 (permission explanations), ref_def456 (defer pattern)

## Components

### Primary Button
- **Description**: 48px height, rounded-full (24px), gradient background
- **States**: Default (gradient), Pressed (slightly darker), Disabled (50% opacity)
- **References**: ref_abc123, ref_def456, ref_ghi789 (all use rounded-full)

### Interest Chip
- **Description**: Pill-shaped tag with icon, 40px height
- **States**: Default (outline + gray), Selected (filled + gradient), Disabled (grayed out)
- **References**: ref_ghi789 (chip behavior), ref_jkl012 (selection animations)

### Progress Indicator
- **Description**: Dots at bottom showing current step (1/4, 2/4, etc.)
- **States**: Current (filled), Completed (checkmark), Upcoming (outline)
- **References**: ref_abc123 (dot pattern), ref_def456 (checkmarks)

### Value Prop Card
- **Description**: 280px width card with icon, title, 2-line description
- **States**: Default (shadow), Swiped (slightly enlarged), Active (border)
- **References**: ref_def456 (carousel card), ref_ghi789 (swipe physics)

## Content Guidelines

### Voice and Tone
- **Personality**: Enthusiastic but not over-the-top
- **Language**: Simple, direct, avoid jargon
- **Emoji**: Use sparingly, for emphasis only
- **Examples**: "Let's get you set up!" ✅ / "Commence initialization process" ❌

### Labels
- **Primary actions**: Action-oriented verbs ("Get Started", "Continue")
- **Secondary actions**: Lowercase, understated ("maybe later", "skip")
- **Navigation**: Back = "Back", Continue = action-specific
- **Examples from references**: ref_abc123 ("Let's go!"), ref_def456 ("Tell me more")

### Error Messages
- **Tone**: Helpful, not blaming
- **Structure**: What happened + how to fix
- **Examples**: "Oops! Something went wrong. Tap to retry." ✅ / "Error 404" ❌

### Help Text
- **Placement**: Below input or in info icon tooltip
- **Style**: Brief, action-oriented
- **Examples from**: ref_ghi789 (helper text patterns), ref_jkl012 (info icons)

## Accessibility Notes

### WCAG Compliance
- **Color contrast**: All text meets 4.5:1 ratio (ref_abc123, ref_def456)
- **Touch targets**: Minimum 44x44px (universal pattern)
- **Focus indicators**: Visible 2px outline on all interactive elements

### Screen Reader Support
- **Labels**: All buttons have clear labels (ref_ghi789 best practice)
- ** announcements**: Selection changes announced ("3 interests selected")
- **Ordering**: Logical tab order following visual flow

### Keyboard Navigation
- **On mobile**: Focus visible after swipe (ref_ghi789 pattern)
- **Escape**: Closes modals, returns to previous step

### Color Independence
- **Not color-only**: States use shape + icon + color (ref_def456, ref_ghi789)
- **Dark mode**: References show high-contrast alternatives (ref_jkl012)

## Open Questions

1. **Skip option**: Should users be able to skip the entire flow? (Stakeholder input needed)
2. **Social sign-in**: Include "Continue with Google/Apple" on Screen 1? (Technical dependency)
3. **Depth vs. breadth**: 4 screens with fewer choices vs. 8 screens with more personalization? (A/B test recommended)
4. **Re-edit onboarding**: Can users change interests later? (Product decision)
5. **Localization**: How will chip-based interest selection work for RTL languages? (i18n review needed)

## References Cited

- ref_abc123: Friendly welcome screens with illustrations
- ref_def456: Video-led onboarding with carousel value props
- ref_ghi789: Interest selection with tag-based personalization
- ref_jkl012: Progressive permission requests with explanations
```
