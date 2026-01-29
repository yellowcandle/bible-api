# Bible API Lookup Skill

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![skills.sh](https://img.shields.io/badge/skills.sh-compatible-blue)](https://skills.sh)

Query and display Bible verses, scripture references, biblical passages, and commentary. Supports 1000+ translations in 100+ languages via the free HelloAO Bible API - no API key required.

## Installation

```bash
npx skills add yellowcandle/bible-api-skill
```

## Features

- **1000+ Translations** - Access Bible text in 100+ languages
- **Commentary Support** - Get biblical commentary from Adam Clarke and Tyndale
- **Multi-language** - Automatic language detection for appropriate translations
- **Audio Links** - Access audio Bible recordings
- **No API Key** - Free, open Bible API (HelloAO)

## Quick Start

Once installed, AI agents can help you look up Bible verses:

**Examples:**
- "What does John 3:16 say?"
- "Read Psalm 23 in Spanish"
- "Show me Genesis 1:1-5"
- "Get commentary on Matthew 5"

## Supported Reference Formats

| Format | Example |
|--------|---------|
| Single verse | John 3:16 |
| Verse range | Genesis 1:1-5 |
| Full chapter | Psalm 23 |
| Numbered books | 1 Corinthians 13 |
| Abbreviated | Rev 21:1-4 |

## Language Support

The skill automatically detects your language and selects appropriate translations:

| Language | Default Translation |
|----------|-------------------|
| English | BSB (Berean Standard Bible) |
| Spanish | RVR1960 or NVI |
| German | DELUT (Luther) |
| French | LSG (Louis Segond) |
| Portuguese | ARC or NVI-PT |
| Chinese | CUV (Chinese Union) |

## API Reference

This skill uses the [HelloAO Bible API](https://bible.helloao.org) (free, no key required).

### Available Endpoints

| Task | Endpoint |
|------|----------|
| List translations | `GET /api/available_translations.json` |
| List books | `GET /api/{translation}/books.json` |
| Get chapter | `GET /api/{translation}/{book}/{chapter}.json` |
| List commentaries | `GET /api/available_commentaries.json` |
| Get commentary | `GET /api/c/{commentary}/{book}/{chapter}.json` |

### Book IDs

The skill uses 3-letter USFM book IDs. See `book-ids.md` for the complete list of Bible books and their identifiers.

## File Structure

```
bible-api-skill/
├── skill.yaml        # Main skill definition with instructions
├── book-ids.md       # USFM book ID reference table
└── README.md         # This file
```

## Commentaries

Available commentary sources:

- **Adam Clarke** (`adam-clarke`) - Comprehensive verse-by-verse commentary
- **Tyndale** (`tyndale`) - Bible commentary with profiles

## Requirements

- Compatible with Claude Code, Cursor, Windsurf, and other AI agents that support skills
- No API key required
- Internet connection required for API access

## License

MIT License - feel free to use and modify as needed.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Support

If you encounter any issues or have questions, please open an issue on GitHub.

---

**Made with faith by [yellowcandle](https://github.com/yellowcandle)**
