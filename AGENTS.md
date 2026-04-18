# AGENTS.md

## Purpose
This repository is a Python FastAPI + HTMX web app for a Social Bingo game. Add or improve backend logic, HTMX interactions, templates, and tests while preserving the playable app flow.

## Key facts
- Python project, requires >=3.13.
- Uses uv for dependency management and command execution.
- FastAPI app entrypoint: app.main:run.
- Templates and HTMX-driven UI are in app/templates/ and app/static/.
- Game logic is centralized in app/game_service.py and app/game_logic.py.
- Tests live in tests/ and should pass before changes are considered complete.

## Architecture Overview
- **Backend**: FastAPI with session-based state management (no database required)
- **Frontend**: HTMX for dynamic interactions, Jinja2 templates, custom CSS utilities
- **State Management**: Cookie-based sessions with unique session IDs
- **Game Logic**: Pure functions in game_logic.py, session state in game_service.py
- **Data Models**: Pydantic models in models.py for type safety

## Development Patterns
- **HTMX Interactions**: Use hx-post, hx-target, hx-swap='outerHTML' for seamless updates
- **Template Structure**: Base template with component includes, session state passed to templates
- **CSS**: Custom utility classes in app.css (Tailwind-like but custom)
- **Testing**: FastAPI TestClient for API tests, pure function tests for game logic
- **Questions**: Social bingo prompts in data.py (24 questions + FREE SPACE)

## Recommended workflows
- Install dependencies: uv sync
- Run tests: uv run pytest
- Start dev server: uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
- Lint code: uv run ruff check .

## Special guidance
- Do not use VS Code Simple Browser for app preview; HTMX needs a full browser.
- Prefer opening http://localhost:8000 in an external browser.
- Keep UI updates consistent with the app's HTMX partial templates and stateful session design.
- Avoid editing files inside .solutions/ unless explicitly asked; they are solution artifacts.
- Use custom CSS utilities over inline styles for consistency.
- Follow Pydantic model patterns for data validation.
- Keep game logic pure and testable in game_logic.py.
- Session store is in-memory; consider TTL cleanup for long-running instances.
- No database; game state lost on restart—fine for single-instance deployments.

## Key Files Exemplifying Patterns
- [app/game_logic.py](app/game_logic.py): Pure functions for bingo mechanics (board generation, bingo detection).
- [app/game_service.py](app/game_service.py): Stateful session management with clear state transitions.
- [app/main.py](app/main.py): HTMX-driven endpoints returning HTML fragments.
- [app/models.py](app/models.py): Frozen Pydantic models for immutability.
- [tests/test_game_logic.py](tests/test_game_logic.py): Unit tests for pure functions.
- [tests/test_api.py](tests/test_api.py): Integration tests for routes and HTML responses.
- [app/templates/components/bingo_board.html](app/templates/components/bingo_board.html): HTMX attributes and Jinja2 conditionals.
- [app/static/css/app.css](app/static/css/app.css): Custom utility classes.

## References
- Project overview: [README.md](README.md)
- Dependency and script config: [pyproject.toml](pyproject.toml)
- App routes and entrypoint: [app/main.py](app/main.py)
- UI templates: [app/templates/](app/templates/)
- Static assets: [app/static/](app/static/)
- Game logic: [app/game_logic.py](app/game_logic.py)
- Session management: [app/game_service.py](app/game_service.py)
- Data models: [app/models.py](app/models.py)
- CSS utilities: [.github/instructions/css-utilities.instructions.md](.github/instructions/css-utilities.instructions.md)
- Frontend design: [.github/instructions/frontend-design.instructions.md](.github/instructions/frontend-design.instructions.md)
- General instructions: [.github/instructions/general.instructions.md](.github/instructions/general.instructions.md)

