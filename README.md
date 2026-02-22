# AI Trip Planner

AI Trip Planner is a Python project that helps generate travel plans using LLM-powered workflows (LangChain-based).

## Features

- Generate trip ideas based on destination, dates, and preferences
- Build day-wise itineraries
- Suggest activities, food spots, and travel tips
- Easy local setup with `uv` and virtual environment

## Tech Stack

- Python 3.10+
- [uv](https://docs.astral.sh/uv/) for environment and package management
- LangChain

## Project Setup (Windows)

### 1) Create virtual environment

```powershell
uv venv
```

### 2) Activate virtual environment

```powershell
.venv\Scripts\activate
```

### 3) Install dependencies

```powershell
uv pip install -r requirements.txt
```

If `requirements.txt` is not available yet, install minimum dependency:

```powershell
uv pip install langchain
```

## Environment Variables

Create a `.env` file in the project root:

```env
GROQ_API_KEY=
OPENAI_API_KEY=
GOOGLE_API_KEY=
GPLACES_API_KEY=
FOURSQUARE_API_KEY=
TAVILAY_API_KEY=
OPENWEATHERMAP_API_KEY=
EXCHANGE_RATE_API_KEY=
```

Add any other provider keys your code uses (for example: Anthropic, Groq, etc.).

## Run the Project

Use your actual entry-point file (example commands below):

```powershell
python main.py
```

or

```powershell
python app.py
```

## Recommended Project Structure

```text
AI_Trip_Planner/
├── .venv/
├── src/
│   ├── planners/
│   ├── prompts/
│   ├── tools/
│   └── main.py
├── tests/
├── .env
├── requirements.txt
└── README.md
```

## Development Notes

- Always activate `.venv` before running project commands.
- Keep secrets only in `.env` (never hardcode API keys).
- Pin dependency versions in `requirements.txt` for reproducibility.

## Common Commands

```powershell
# Install/update dependencies
uv pip install -r requirements.txt

# Freeze installed packages
uv pip freeze > requirements.txt

# Run tests (if tests exist)
pytest -q
```

## Troubleshooting

- **`uv` not recognized**  
  Install `uv` and restart terminal.

- **Virtual env not activating**  
  Use PowerShell from the project root and run:
  ```powershell
  .venv\Scripts\activate
  ```
