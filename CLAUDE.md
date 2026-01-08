# Claude Code Guidelines for Personal Blog

## Branch Naming

Use semantic branch prefixes with `claude/` prefix and session ID suffix:

- `claude/feat-<description>-<session-id>` - New features or additions
- `claude/fix-<description>-<session-id>` - Bug fixes or corrections
- `claude/docs-<description>-<session-id>` - Documentation updates
- `claude/refactor-<description>-<session-id>` - Code refactoring
- `claude/style-<description>-<session-id>` - UI/styling changes

Examples: `claude/feat-dark-mode-abc123`, `claude/fix-mobile-nav-xyz789`

**Important:** Branch names MUST start with `claude/` and end with session ID for push to succeed.

## Commit Messages

Keep commits small and concise. Use simple, descriptive messages:

- ✅ "Fix blog sources target blank"
- ✅ "Add dark mode toggle"
- ❌ "This commit adds comprehensive dark mode support with theme switching, persistent storage, and smooth transitions across all pages"

## Quality Checks

Before committing, always:

1. Run build: `npm run build`
2. Run type check: `npx astro check`
3. Format code: `npx prettier --write`
4. Verify all changes work as expected

## Communication

Always ask if you are not sure about:

- Implementation approach
- Design decisions
- Breaking changes
- User preferences

## Project Log

Maintain `.claude-sessions.log` with session summaries for future reference.

## Writing Style

Blog posts should be:

- Conversational and human-like
- Clear and accessible
- Well-researched with proper citations
- Engaging without being overly technical
- SEO-friendly with proper headings and structure
