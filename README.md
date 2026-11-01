# AI-powered-research-assistant
AI research assistant for Google Colab. It does literature reviews, document Q&amp;A, citation formatting and peer-review feedback, using the free Gemini API.
# 🔎 AI Research Assistant

An AI-powered research assistant that runs in **Google Colab**. Ask a topic or question, upload papers, and get structured briefings, summaries, citations and peer-review feedback. It runs on the **free Gemini API**, so no payment is needed.

## Features

| Use case | How to call it |
|---|---|
| Topic research: overview, literature review, compare, critique, research plan, timeline | `ra.research(topic, mode)` |
| Follow-up questions (remembers the conversation) | `ra.follow_up(question)` |
| Live web research with sources | `ra.research(topic, web=True)` |
| Upload PDFs or text and ask questions | `ra.upload()`, then `ra.ask_docs(question)` |
| Summarize, synthesize, or find gaps across documents | `ra.docs_task(task)` |
| Extract key fields from papers into a table | `ra.extract()` |
| Citation formatting (APA, MLA, IEEE, Chicago, Harvard, BibTeX) | `ra.cite(refs, style)` |
| Brainstorm research questions and hypotheses | `ra.brainstorm(topic)` |
| Peer-review feedback on your draft | `ra.peer_review(draft)` |
| Explain a concept at any level | `ra.explain(concept, level)` |
| Export notes to Markdown and HTML | `ra.export()` |

The notebook also includes an interactive tabbed form, a type-your-question chat prompt, and a self-test that runs every use case once.

## How to run

1. **Get a free API key.** Go to [aistudio.google.com](https://aistudio.google.com), click **Get API key**, then **Create API key**. A Google account is all you need.
2. **Open the notebook in Colab** with the badge above.
3. **Add the key as a secret.** In Colab, open the 🔑 **Secrets** tab, add a secret named `GEMINI_API_KEY`, paste your key, and turn on **Notebook access**.
4. **Run the cells from top to bottom.**
5. **Ask something:**
   ```python
   ra.research("Impact of transformers on time-series forecasting", mode="Literature review")
   ra.follow_up("Which datasets are most used?")
   ```

## Configuration

- **Model:** set `MODEL` in the core cell. Google retires model names over time, so if you see a 404 "model not found" error, change it to a model currently listed in Google AI Studio (for example `gemini-3.8-flash`).
- **Answer length:** the `DEPTH` setting controls the maximum output size. Raise it if answers are cut off.
- **Rate limits:** the free tier is rate limited, so the code pauses between calls and retries automatically.

## Security

**Never commit your API key.** The code reads it from Colab Secrets or an environment variable, and `.gitignore` excludes `.env` and secrets files. If a key is ever exposed, delete it in Google AI Studio and create a new one.

## Limitations

- Answers come from an AI model. It can be wrong or make things up, so verify names, figures and citations against original sources.
- Free-tier limits and model names change, and Google may use free-tier data to improve its products, so don't upload confidential documents.
- Web search depends on your account and provider settings.
- Large PDFs use many tokens.

## Project structure

```
├── research_assistant_colab_gemini.ipynb   # free Gemini version (main notebook)
├── README.md
├── requirements.txt
├── LICENSE
└── .gitignore
```

## License

MIT, see [LICENSE](LICENSE). Copyright (c) 2026 Shwetha.
