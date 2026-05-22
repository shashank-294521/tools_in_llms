# Tools with LLMs

A hands-on project demonstrating how Large Language Models (LLMs) can interact with external tools using LangChain and Groq.

This notebook explains the concept of **tool calling**, how to create custom tools, bind them with an LLM, and execute tool-based workflows.

---

## Features

* Introduction to Tool Calling in LLMs
* Creating custom tools using LangChain
* Using the `@tool` decorator
* Binding tools with LLMs
* Executing tool calls dynamically
* Understanding tool invocation flow
* Integration with Groq models
* Practical examples of tool usage

---

## Technologies Used

* Python
* LangChain
* Groq API
* Jupyter Notebook / Google Colab

---

## Project Structure

```bash
tools_in_llms/
│
├── tools_with_llms.ipynb   # Main notebook
├── README.md               # Project documentation
```

---

## Installation

Install the required dependencies:

```bash
pip install -q langchain-groq langchain-core requests
```

---

## Imports Used

```python
from langchain_groq import ChatGroq
from langchain_core.tools import tool
```

---

## Creating a Custom Tool

Example of a multiplication tool:

```python
@tool
def multiply(a:int,b:int)->int:
    """Multiply two numbers"""
    return a*b
```

---

## Initializing the LLM

```python
llm = ChatGroq(
    model="llama-3.3-70b-versatile",
    temperature=0.7
)
```

---

## Binding Tools with LLM

```python
llm_with_tools = llm.bind_tools([multiply])
```

This allows the LLM to decide when to use the tool automatically.

---

## Example Query

```python
query = "Can you multiply 3 with 10?"
```

The LLM recognizes that the task requires mathematical computation and calls the multiplication tool internally.

---

## Concepts Covered

### What are Tool Calls?

Tool calls allow LLMs to:

* Use external APIs
* Execute functions
* Perform calculations
* Access databases
* Retrieve live information
* Automate workflows

Instead of only generating text, the model can interact with real-world systems.

---

## Workflow

1. Create a tool
2. Bind the tool to the LLM
3. Send a query
4. LLM decides whether tool usage is required
5. Tool executes
6. Result is returned to the user

---

## Use Cases

* AI Agents
* Chatbots with external actions
* Calculator assistants
* Weather bots
* Database querying assistants
* Automation systems
* API integrations

---

## How to Run

### Clone the Repository

```bash
git clone https://github.com/shashank-294521/tools_in_llms.git
```

### Move into the Project Folder

```bash
cd tools_in_llms
```

### Open Notebook

Run Jupyter Notebook or upload the notebook to Google Colab.

---

## Output Demonstration

The notebook demonstrates:

* Tool creation
* Tool binding
* Tool invocation by the LLM
* Returning results from tools

---

## Future Improvements

* Add multiple tools
* Integrate APIs
* Add memory support
* Build AI agents
* Add streaming responses
* Connect with databases
* Build a web interface

---

## Learning Outcomes

After completing this project, you will understand:

* How tool calling works in modern LLMs
* How LangChain manages tools
* How LLMs decide when to invoke tools
* Basic AI agent architecture

---

## Author

Shashank

---

## Repository

GitHub Repository:

[https://github.com/shashank-294521/tools_in_llms](https://github.com/shashank-294521/tools_in_llms)
