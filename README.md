# Energy & Water Saving Chatbot (Chatbot Hemat Energi dan Air)

A Streamlit chatbot that gives practical recommendations for saving electricity and water at home and in industry, powered by Google Gemini 1.5 Flash. It answers in Indonesian and is instructed to stay on topic: it only answers questions about saving energy and water.

## Features

- **Focused assistant:** a system instruction makes the model an energy- and water-saving advisor that answers in proper Indonesian and declines unrelated questions.
- **Multi-turn chat:** a Gemini chat session is kept in Streamlit session state, so follow-ups keep context.
- **Suggested questions:** five questions are picked at random from 42 (energy and water, households and industry); click one to send it, or shuffle with **Randomize Questions**.
- **Flexible API key setup:** read from a `.env` file locally, or from Streamlit secrets when deployed.
- **Codespaces ready:** a dev container installs dependencies and starts the app on port 8501.

## Topics Covered

| | Households | Industry |
|---|---|---|
| **Energy** | LED lighting, AC temperature, efficient appliances, insulation, smart thermostats, cooking | Energy audits, energy management, renewables, smart lighting, automatic controls, cooling, lean manufacturing |
| **Water** | Bathroom habits, dishwashing, dual-flush toilets, low-flow shower heads, leak repair, rainwater | Water audits, wastewater treatment, recycling, sensors, cleaning processes, green manufacturing |

## Model Configuration

`gemini-1.5-flash-latest`, temperature 0.7, top-p 0.95, top-k 64, up to 8,192 output tokens. Scope is set by the system instruction (Indonesian, energy and water saving only, emoji allowed).

## Tech Stack

Python 3.11, Streamlit, `google-generativeai`, python-dotenv, Dev Container.

## Project Structure

```
chatbot-hemat-energi/
├── main.py                  # Streamlit app: Gemini setup, chat, suggested questions
├── main.py.bak              # Earlier version
├── requirements.txt
└── .devcontainer/devcontainer.json
```

## Getting Started

```bash
git clone https://github.com/harrymardika/chatbot-hemat-energi.git
cd chatbot-hemat-energi
pip install -r requirements.txt
```

Create a `.env` file with a [Google AI Studio](https://aistudio.google.com/) key:

```env
GOOGLE_GEMINI_KEY=<your Gemini API key>
```

```bash
streamlit run main.py
```

On Streamlit Community Cloud, add the key under **Settings → Secrets** as `api_key = "<your key>"`. In GitHub Codespaces, the dev container installs everything and starts the app automatically.

## Author

**Harry Mardika** · [GitHub](https://github.com/harrymardika)
