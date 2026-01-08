# Claude Code Guidelines for Personal Blog

## Branch Naming

Use semantic branch prefixes based on change type:

- `feat/` - New features or additions
- `fix/` - Bug fixes or corrections
- `docs/` - Documentation updates
- `refactor/` - Code refactoring
- `style/` - UI/styling changes

Examples: `feat/dark-mode`, `fix/mobile-nav`, `docs/readme-update`

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
