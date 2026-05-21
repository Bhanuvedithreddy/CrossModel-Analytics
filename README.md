# CrossModel-Analytics

**LLM Nexus: Intelligent routing & cost-analysis engine for Generative AI**

## Overview

CrossModel-Analytics allows users to compare outputs, latency, and costs across multiple Large Language Models (LLMs) such as OpenAI's ChatGPT, Gemini, and Llama. The app is implemented in Python using [Streamlit](https://streamlit.io/) for an interactive, browser-based UI. It is designed to help enterprise and research users select the optimal LLM for their needs based on specific prompts, performance, and cost criteria.

---

## Features

- **Model Comparison**: Dispatches prompts in parallel to ChatGPT, Gemini, and Llama models, comparing outputs side-by-side.
- **Intelligent Routing**: Chooses optimal models depending on user-specified tasks (General, Coding, Fast Response, Cost Saving).
- **Metrics Dashboard**: Tracks and visualizes latency, response length, and request frequency for all supported LLMs.
- **Cost Analysis**: Estimates and reports the cost of queries against various models.
- **Authentication**: Simple username/password with local credential storage.
- **Rate Limiting**: Prevents abuse with configurable user-based query limits.
- **Enterprise UI**: Intuitive controls, dark-mode-optimized interface, and report export features.

---

## Getting Started

### Prerequisites

- Python 3.11+
- Access keys for LLM APIs (e.g. `OPENAI_API_KEY` for ChatGPT and credentials for Gemini, Llama, etc.)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Bhanuvedithreddy/CrossModel-Analytics.git
   cd CrossModel-Analytics
   ```

2. **Install the requirements**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set environment variables**

   - `OPENAI_API_KEY` for ChatGPT
   - Environment variables for Gemini, Llama models (see their respective docs)

   You can use a `.env` file with [python-dotenv](https://github.com/theskumar/python-dotenv).

4. **Run the app**
   ```bash
   streamlit run app.py
   ```

5. **Access the UI**

   By default, the app will be available at `http://localhost:8501`

---

## Configuration

- `config.py` - Adjust the `MODEL_CONFIG` dictionary to set your per-model cost, performance, or feature adjustments.
- `.devcontainer/devcontainer.json` - Provides settings for running the app in a dev container or Codespace.

---

## Usage

1. Register or login (credentials are stored locally in `data/users.csv`).
2. Select your target objective (General, Coding, Fast Response, Cost Saving).
3. Enter your prompt and execute the query.
4. Review the comparative results in visually segmented tabs:
    - Visual Comparison
    - Raw Data (JSON)
    - Cost Report
    - Performance Dashboard (bar and line charts)
5. Export or review the generated report files in `data/comparision_reports/`.

---

## Project Structure

- `app.py` — Main Streamlit application file
- `auth.py` — Authentication (login/registration logic)
- `config.py` — Model configuration (cost, speed, quality)
- `utils/` — Supporting utilities: routing, metrics, reporting, parallel execution, etc.
- `models/` — Model-specific API integration (e.g., ChatGPT, Gemini, Llama)
- `data/` — Stores user data, metrics, and comparative reports

---

## Dependencies

See `requirements.txt` for full list. Major dependencies include:

```
streamlit
openai
google-generativeai
huggingface-hub
python-dotenv
pandas
numpy
```

---

## Notes & Caveats

- **Model APIs**: You will need API keys and (potentially) paid plans for most commercial LLM endpoints.
- **Local data**: User data and reports are stored locally. For production, consider a secure backend for credentials and analytics.
- **Current Models Supported**: ChatGPT, Gemini, Llama (modify or extend in the `models/` folder as needed).

---

## License

MIT License. See [LICENSE](LICENSE) file for details.

---

## Acknowledgements

- [Streamlit](https://streamlit.io/)
- OpenAI, Gemini, Llama APIs
- Project by [Bhanu Vedith Reddy](https://github.com/Bhanuvedithreddy)
