# MediCare Patient Follow-Up Agent

An interview case-study prototype that uses an LLM agent to review patient records, identify clinical risks and create prioritised follow-up actions.

## What the notebook covers

- Loads and explores 100 patient records.
- Defines tools for patient lookup, vital checks, lab references and cohort comparison.
- Uses an OpenAI-compatible tool-calling loop instead of hardcoded risk decisions.
- Demonstrates a detailed review of one patient.
- Finds all missed appointments and creates a ranked follow-up worklist.
- Validates every recorded action with Pydantic.

## Run locally

Requirements: Python 3.10 or newer and Jupyter Notebook or JupyterLab.

```bash
pip install pandas matplotlib openai "pydantic>=2" python-dotenv jupyter
```

Create a local `.env` file:

```env
OPENAI_API_KEY=your_api_key
```

Keep `patient_data.csv` beside the notebook, open `MediCare_FollowUp_Agent.ipynb`, and select **Restart Kernel and Run All Cells**.

The default model is `gpt-4.1-mini`. The notebook also supports other OpenAI-compatible endpoints through `LLM_API_KEY`, `LLM_BASE_URL` and `LLM_MODEL`.

## Notes

- API keys are loaded from the environment and are not stored in the repository.
- Patient names are removed before records are sent to the model.
- Saved outputs are included for review; running all cells with a valid API key generates a fresh agent response.
- This is a decision-support prototype. Clinical recommendations require professional review.
