# Palmer Penguins — LLM-Assisted EDA

This project explores the Palmer Penguins dataset using a locally running Gemma 3 12B language model via LM Studio. The idea is to use natural language prompts to generate and execute data analysis code directly within a Jupyter notebook.

While I have extensive experience using cloud-based LLMs to support data science work, I wanted to integrate a locally-hosted one into a project for the following reasons:

 1. Efficiency: no jumping back and forth between a cloud-based LLM and a Jupyter notebook
    
2. Transparency: I wanted the Python code to be immediately visible for easy validation. At this point in time, I want my eyes on what the AI does--AI is for stetching my abilities, not replacing them.
    
3. Security: The model does not see the records themselves--it only sees the context. And even what it does see doesn't leave the local machine.

I've been happy with the results so far, and hope to do more in-depth work on more complex datasets with locally-hosted LLMs in the future. 

## Current Challenge

For simple EDA tasks, short, simple prompts seem to work well--the preprogrammed context is doing its job. As I tried multi-step analysis like displaying a correlation matrix as a heatmap, context becomes an issue. I'm coming across the issue of having a single context statement that goes to the model with each prompt--I can't add to it as I go, because that will create issues with earlier prompts. I'm looking into dynamic context options.

## Project Structure

- notebooks/eda.ipynb — initial exploratory data analysis performed manually, covering basic exploration of the dataset's structure and distributions
- notebooks/llm_eda.ipynb — LLM-assisted analysis using a locally running Gemma 3 12B model, with a custom prompt pipeline that generates and auto-executes Python code in response to natural language queries


## How It Works

A context-aware prompt template feeds the model information about the dataset--column names, data types, and sample rows, along with constraints specifying variable names and libraries. Natural language prompts are sent to the model, and any returned Python code is displayed as formatted markdown and executed automatically in the notebook.

## Dataset

Palmer Penguins is a widely used dataset for data science education, containing measurements for three penguin species observed across three islands in the Palmer Archipelago, Antarctica. I chose it for this project because I wanted somethig clean and manageable for testing smaller LLM capabilities. 