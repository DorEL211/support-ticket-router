Build a Google Colab notebook (`.ipynb`) in Python using LangGraph that implements a customer support ticket router for a to-do app.

### Model Choice
Use `gpt-6-luna` via `ChatOpenAI(model="gpt-6-luna", temperature=0)`.
Why: Sorting a short support ticket into one of three predefined categories is a simple classification task that does not require an expensive reasoning model. `gpt-6-luna` is one of OpenAI's lowest-cost text models, keeping test runs fast and inexpensive, while `temperature=0` ensures deterministic and consistent routing.

### Setup & API Key
- First cell: `!pip -q install langgraph langchain-openai`
- Load the OpenAI API key from Google Colab Secrets (never use `getpass` and never hardcode any key):
  ```python
  import os
  from google.colab import userdata
  os.environ["OPENAI_API_KEY"] = userdata.get("OPENAI_API_KEY")
