Palmer Penguins — LLM-Assisted EDA

This project explores the Palmer Penguins dataset using a locally running Gemma 3 12B language model via LM Studio. The idea is to use natural language prompts to generate and execute data analysis code directly within a Jupyter notebook.

Project Structure

notebooks/eda.ipynb — initial exploratory data analysis performed manually, covering basic exploration of the dataset's structure and distributions
notebooks/llm_eda.ipynb — LLM-assisted analysis using a locally running Gemma 3 12B model, with a custom prompt pipeline that generates and auto-executes Python code in response to natural language queries


How It Works

A context-aware prompt template feeds the model information about the dataset — column names, data types, and sample rows — along with constraints specifying variable names and libraries. Natural language prompts are sent to the model, and any returned Python code is displayed as formatted markdown and executed automatically in the notebook.

Dataset

Palmer Penguins is a widely used dataset for data science education, containing measurements for three penguin species observed across three islands in the Palmer Archipelago, Antarctica.