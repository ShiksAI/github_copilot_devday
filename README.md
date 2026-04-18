# 🎯 Soc Ops - Social Bingo Game

<div align="center">

![Soc Ops Banner](https://img.shields.io/badge/Social_Bingo-Game-blue?style=for-the-badge&logo=game&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.13+-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![HTMX](https://img.shields.io/badge/HTMX-3366CC?style=flat-square&logo=htmx&logoColor=white)

**Break the ice at your next team mixer!** 🎉

*Find people who match the questions and get 5 in a row to win!*

[🚀 Live Demo](https://copilot-dev-days.github.io/agent-lab-python/) • [📖 Workshop Guide](https://copilot-dev-days.github.io/agent-lab-python/docs/) • [💻 GitHub Repo](https://github.com/copilot-dev-days/agent-lab-python)

---

## 🎮 What is Soc Ops?

Soc Ops is a **fun, interactive Social Bingo game** designed for in-person team mixers and icebreaker activities. Players tap squares as they find colleagues who match fun questions like:

- "Has lived in another country" 🌍
- "Can juggle" 🤹‍♂️
- "Has a pet" 🐾
- "Plays an instrument" 🎵

Get **5 in a row** (horizontally, vertically, or diagonally) to win! 🏆

</div>

---

## ✨ Features

<div align="center">

| 🎯 **Core Gameplay** | 🎨 **Modern UI** | 📱 **Responsive Design** |
|:--------------------:|:----------------:|:-----------------------:|
| Interactive bingo board | Clean, modern interface | Mobile-friendly |
| 24+ fun questions | HTMX-powered updates | Touch-optimized |
| Win detection | Custom CSS utilities | Fast loading |

</div>

### 🚀 Tech Stack

- **Backend**: FastAPI + Python 3.13+
- **Frontend**: HTMX + Jinja2 templates
- **Styling**: Custom CSS utility classes
- **Deployment**: Ready for any hosting platform
- **Development**: `uv` for dependency management

---

## 🎯 Quick Start

### Prerequisites
- Python 3.13+
- Git
- VS Code (recommended)

### Installation

```bash
# Clone the repository
git clone https://github.com/copilot-dev-days/agent-lab-python.git
cd agent-lab-python

# Install dependencies
uv sync

# Start the development server
uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```

### Play the Game
1. Open [http://localhost:8000](http://localhost:8000) in your browser
2. Click "Start Game"
3. Tap squares when you find someone who matches each question
4. Get 5 in a row to win!

---

## 🎓 GitHub Copilot Workshop

This project is part of the **GitHub Copilot DevDay Agent Lab** - a hands-on workshop teaching AI-first development with VS Code and GitHub Copilot.

### 🗺️ Workshop Parts

| Part | Title | Duration | Focus |
|------|-------|----------|-------|
| [**00**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview) | Overview & Setup | — | Prerequisites & checklist |
| [**01**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=01-setup) | Context Engineering | 15 min | Custom instructions & agents |
| [**02**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=02-design) | Design-First Frontend | 15 min | UI/UX with AI assistance |
| [**03**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=03-quiz-master) | Custom Quiz Master | 10 min | Specialized AI agents |
| [**04**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=04-multi-agent) | Multi-Agent Development | 20 min | Advanced AI workflows |

### 🎯 Learning Outcomes

- **Context Engineering**: Teach AI about your codebase
- **Agent Mode**: Use autonomous AI agents for development
- **Custom Instructions**: Create reusable AI guidance
- **Multi-Agent Workflows**: Coordinate multiple AI agents
- **AI-First Development**: Leverage AI throughout the development lifecycle

---

## 📁 Project Structure

```
soc-ops/
├── app/                    # FastAPI application
│   ├── main.py            # App entry point & routes
│   ├── game_service.py    # Game session management
│   ├── game_logic.py      # Core bingo logic
│   ├── models.py          # Pydantic data models
│   ├── data.py            # Bingo questions
│   └── templates/         # Jinja2 templates
│       ├── components/    # HTMX components
│       └── static/        # CSS & JS assets
├── tests/                 # Test suite
├── workshop/              # Workshop materials
└── docs/                  # Workshop documentation
```

---

## 🛠️ Development

### Available Commands

```bash
# Install dependencies
uv sync

# Run tests
uv run pytest

# Start development server
uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000

# Lint code
uv run ruff check .

# Format code
uv run ruff format .
```

### Testing

```bash
# Run all tests
uv run pytest

# Run with coverage
uv run pytest --cov=app --cov-report=html

# Run specific test file
uv run pytest tests/test_api.py
```

---

## 🌐 Internationalization

Soc Ops supports multiple languages:

- 🇬🇧 **English** (primary)
- 🇪🇸 **Español** ([README.es.md](README.es.md))
- 🇧🇷 **Português (Brasil)** ([README.pt_BR.md](README.pt_BR.md))

---

## 🤝 Contributing

This project welcomes contributions! Whether you're fixing bugs, adding features, or improving documentation:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

### Development Guidelines

- Follow the existing code style
- Add tests for new features
- Update documentation as needed
- Use `uv run ruff check .` to lint your code

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

<div align="center">

**Made with ❤️ for the GitHub Copilot DevDay community**

[⭐ Star this repo](https://github.com/copilot-dev-days/agent-lab-python) • [🐛 Report issues](https://github.com/copilot-dev-days/agent-lab-python/issues) • [💬 Join discussions](https://github.com/copilot-dev-days/agent-lab-python/discussions)

---

*Ready to break the ice? Start the workshop above! 🚀*

</div>
