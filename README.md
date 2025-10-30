# ICT Assistant RAG Level Evaluation

This project provides a document retrieval evaluation framework for an Information and Communication Technology (ICT) assistant AI specialized in CSTA (Computer-Supported Telecommunications Applications) standards. It leverages [Promptfoo](https://promptfoo.dev) to automate and analyze retrieval-augmented generation (RAG) performance against a benchmark of realistic queries and gold-standard documents. The main purpose is to rigorously evaluate the quality of the AI’s retrieval responses, ensuring reliability for CSTA and ICT-related assistant scenarios.

## Features

- Automated evaluation of RAG pipelines for ICT and CSTA domain questions.
- Test dataset of expert queries with corresponding ground truth.
- Customizable provider (API) endpoints for local or remote retrievers.
- HTML output reports summarizing pass/fail results by query and assertion.

---

## Requirements

- Python (recommended: 3.8+)
- Node.js (for installing Promptfoo CLI)
- [Promptfoo](https://promptfoo.dev) (`npm install -g promptfoo`)
- A running retrieval API endpoint (`http://localhost:3000/api/retrieve` by default)
- YAML support

---

## Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/szentesik/ict_assistant_rag_level_evaluation.git
   cd ict_assistant_rag_level_evaluation
   ```

2. **Install Promptfoo globally (if not already installed):**

   ```bash
   npm install -g promptfoo
   ```

3. **(Optional) Set up and run your retriever server**

   - Expected at `http://localhost:3000/api/retrieve`.
   - Modify `promptfooconfig.yaml` to point to your API if different.

---

## Quick Start

1. **Edit or review the test dataset:**  
   The file `datasets.yaml` contains a list of evaluation queries and assertions (expected retrieval results).

2. **Review Promptfoo configuration:**  
   All test and output options are specified in `promptfooconfig.yaml`.

3. **Run the evaluation:**  
   ```bash
   promptfoo eval
   ```
4. **View the results:**
   Run `promptfoo view` to use the local web viewer, or 
   open the HTML report generated at `output/latest_results.html`.   

---

## Usage & Customization

- **Adding Queries:**  
  Edit `datasets.yaml` to add/remove evaluation prompts or update ground truth assertions.

- **Customizing API endpoint:**  
  Update the `url` field under `providers` in `promptfooconfig.yaml` to match your retriever endpoint.

- **Tweaking Output:**  
  Set the `outputPath` field in `promptfooconfig.yaml` to control result file location or specify --output in command line.

---

## File Structure

- `promptfooconfig.yaml`: Main Promptfoo evaluation config.
- `datasets.yaml`: List of test queries and assertions.
- `output/`: Folder with latest and historical HTML results.
- `README.md`: Project overview (this file).

---

## Example Run

```bash
promptfoo eval --output output/results-$(Get-Date -Format "yyyyMMdd_hhmmss").html
```

---

## References

- [Promptfoo Documentation](https://promptfoo.dev/docs/)
- [CSTA Standard Overview (Wikipedia)](https://en.wikipedia.org/wiki/Computer-supported_telecommunications_applications)

---

## License

MIT (or your preferred license here)

---

Let me know if you want any customizations for your organizational needs or a sample badge for build status/results!