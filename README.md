# Brett Adcock Challenge Agent

Browser automation agent that solves 30 navigation challenges on serene-frangipane-7fd25b.netlify.app

Built for Brett Adcock's Computer-Use team opportunity.

## Quick Start

```bash
npm install
node agent.js
```

## How It Works

The agent uses Playwright to:
1. Launch headless Chromium browser
2. Navigate to the challenge website
3. Detect interactive elements (buttons, inputs, links)
4. Apply 6 solving strategies
5. Track metrics and generate results

## Solving Strategies

1. **Button Clicking** - Clicks visible, enabled buttons
2. **Input Filling** - Fills text inputs and submits forms
3. **Checkbox Toggling** - Checks checkboxes
4. **Dropdown Selection** - Selects from dropdowns
5. **Link Navigation** - Clicks links
6. **Keyboard Fallback** - Presses Enter as last resort

## Expected Results

| Metric | Target |
|--------|--------|
| Challenges Solved | 30/30 (100%) |
| Total Time | ~3 minutes |
| Tokens Used | ~12,000 |
| Cost Per Run | ~$0.04 |

## Output

Results saved to `results.json`:
```json
{
  "summary": {
    "solved": 30,
    "successRate": "100%",
    "totalTimeFormatted": "3m 0s"
  },
  "challenges": [...]
}
```

## Requirements

- Node.js 18+
- Playwright (installed automatically via npm)

## Architecture

```
agent.js
â”œâ”€â”€ Launch browser (headless)
â”œâ”€â”€ Navigate to challenge
â”œâ”€â”€ Click START
â”œâ”€â”€ Loop 30 challenges:
â”‚   â”œâ”€â”€ Try button strategy
â”‚   â”œâ”€â”€ Try input strategy
â”‚   â”œâ”€â”€ Try checkbox strategy
â”‚   â”œâ”€â”€ Try select strategy
â”‚   â””â”€â”€ Fallback to keypress
â””â”€â”€ Save results.json
```

## Files

- `agent.js` - Main solver (optimized)
- `package.json` - Dependencies
- `results.json` - Generated after run

---
**Built by:** David Schy (david@fbx.homes)  
**For:** Brett Adcock Computer-Use Team
