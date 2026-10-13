# Currency Converter with LangChain Tools

This project is a Jupyter notebook demonstration of a currency-conversion workflow using a local Ollama chat model and two LangChain tools.

## How it works

The notebook, [`cc_tool.ipynb`](./cc_tool.ipynb), binds two tools to `qwen2.5:3b`:

- `convert_currency` requests the exchange rate for a pair of currencies from ExchangeRate-API.
- `convert` multiplies an amount by the exchange rate.

The model proposes tool calls. Python code in the notebook executes the calls, uses the rate returned by the API when invoking `convert`, adds the tool results to the conversation, and asks the model to write the final response.

For the detailed sequence and current implementation limitations, see [`flow.md`](./flow.md).

## Requirements

- Python with Jupyter support
- Ollama installed and running
- The `qwen2.5:3b` model available in Ollama
- An ExchangeRate-API key
- Python packages: `langchain-ollama`, `langchain-core`, and `requests`

## Setup

1. Install the Python packages in the environment used by the notebook:

   ```bash
   pip install langchain-ollama langchain-core requests
   ```

2. Start Ollama and download the model if needed:

   ```bash
   ollama pull qwen2.5:3b
   ```

3. Set the API key as an environment variable named `API` before starting the notebook kernel. For example, in a macOS/Linux terminal:

   ```bash
   export API="your-exchangerate-api-key"
   ```

   Then launch VS Code or Jupyter from that terminal so the kernel inherits the variable. The notebook reads `API` with `os.environ["API"]`; it does not load a `.env` file itself.

4. Open `cc_tool.ipynb` in VS Code or Jupyter, select the environment where you installed the packages, and run the cells from top to bottom.

## Example request

The notebook's example asks for the USD-to-INR exchange rate and converts 100 USD. The exchange rate is fetched live from ExchangeRate-API, so the result changes with the provider's data.

## Notes

- Keep API keys private. Do not commit them; `.env` is listed in `.gitignore`.
- The notebook currently has limited input validation and API error handling. See the limitations section in [`flow.md`](./flow.md).
- To rerun the conversation cleanly, restart the kernel or recreate the `messages` list before executing the tool-dispatch cells again.
# conversion_using_tools-Agentic-AI-
