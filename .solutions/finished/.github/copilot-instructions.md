# Copilot Workspace Instructions

## Development Checklist

Before committing any changes, ensure:

- [ ] `uv run ruff check .` passes with no errors
- [ ] `uv run pytest` passes
- [ ] Code follows Python conventions (snake_case, type hints)
- [ ] No unused variables or imports

## Project Overview

**Soc Ops** is a Social Bingo game built with Python (FastAPI + Jinja2 + HTMX). Players find people who match questions to mark squares and get 5 in a row.

## Architecture

```
app/
├── templates/       # Jinja2 HTML templates
│   ├── base.html
│   ├── home.html
│   └── components/  # bingo_board, bingo_modal, game_screen, start_screen
├── static/          # CSS & JS assets
├── models.py        # Pydantic models (GameState, BingoSquare)
├── game_logic.py    # Board generation & bingo detection
├── game_service.py  # Session management (GameSession)
├── data.py          # Question bank
└── main.py          # FastAPI routes & HTMX endpoints
tests/
├── test_api.py      # API endpoint tests (httpx + TestClient)
└── test_game_logic.py  # Game logic unit tests
```

## Key Commands

```bash
uv run uvicorn app.main:app --reload --port 8000  # Run dev server
uv run pytest                                       # Run tests
uv run ruff check .                                 # Lint
```

## Styling

Uses custom CSS utility classes (Tailwind-like) in `app/static/css/app.css`:
- Layout: `.flex`, `.grid`, `.items-center`
- Spacing: `.p-4`, `.mb-2`, `.mx-auto`
- Colors: `.bg-accent`, `.bg-marked`, `.text-gray-700`

## State Management

- `GameSession` manages game state server-side
- State persisted via signed cookies (itsdangerous)
- HTMX handles partial page updates without full reloads

## Design Guide

### Visual Aesthetic
- **Playful & Fun**: Use bright colors, emojis, and animations to create an engaging social game experience
- **Typography**: "Fredoka One" font for headings and playful text
- **Backgrounds**: Gradient backgrounds (yellow-to-pink) for visual interest

### Color Palette
- **Primary Accent**: `#FF6B9D` (Bright Pink) - buttons, highlights
- **Secondary**: `#4ECDC4` (Turquoise) - complementary elements
- **Marked Squares**: `#81C784` (Bright Green) - with confetti animations
- **Winning Squares**: `#FFD54F` (Gold) - with sparkle effects
- **Background**: Linear gradient from `#FFF9C4` to `#FCE4EC`

### Animations & Interactions
- **Hover Effects**: Scale transforms (1.05x) on interactive elements
- **Button States**: Pulse animations for calls-to-action
- **Celebrations**: Bounce, confetti, and sparkle effects for wins
- **Transitions**: 300ms duration with smooth easing

### UI Components
- **Buttons**: Rounded corners (rounded-2xl), shadow effects, hover scaling
- **Cards**: White backgrounds with accent borders and fun shadows
- **Emojis**: Use relevant emojis in questions, instructions, and UI text
- **Spacing**: Generous padding and margins for breathing room

### Accessibility
- Maintain proper contrast ratios
- Use semantic HTML and ARIA labels
- Ensure touch targets are adequately sized (minimum 44px)
- Support keyboard navigation for all interactive elements
