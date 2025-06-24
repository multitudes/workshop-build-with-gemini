# langchain - langgraph - langflow - langsmith

Here's a summary of the main differences between these LangChain ecosystem frameworks:

### LangChain
The core framework for building LLM applications. Provides components for chains, agents, and prompts.

````python
from langchain.llms import OpenAI
from langchain.chains import LLMChain
from langchain.prompts import PromptTemplate

# Basic LangChain example
llm = OpenAI()
prompt = PromptTemplate(
    input_variables=["product"],
    template="What is a good name for a company that makes {product}?"
)
chain = LLMChain(llm=llm, prompt=prompt)
print(chain.run("eco-friendly water bottles"))
````

### LangGraph 
Built on top of LangChain, focused on orchestrating complex multi-agent workflows using directed graphs.

````python
from langgraph.graph import Graph
from langchain.chat_models import ChatOpenAI

# Create nodes and edges for a workflow
nodes = {
    "planner": planner_node,
    "executor": executor_node,
    "reviewer": reviewer_node
}
edges = [
    ("planner", "executor"),
    ("executor", "reviewer")
]
workflow = Graph(nodes=nodes)
workflow.add_edges(edges)
````

### LangFlow
Visual tool for building LangChain flows using a drag-and-drop interface. No coding required.
- Provides UI components for LangChain objects
- Exports flows as Python code
- Great for prototyping

### LangSmith
Monitoring and debugging platform for LangChain applications:

````python
from langsmith import Client
from langchain.callbacks import LangSmithCallbackHandler

# Track runs in LangSmith
client = Client()
callback = LangSmithCallbackHandler(
    project_name="My Project"
)
chain = LLMChain(
    llm=llm,
    prompt=prompt,
    callbacks=[callback]
)
````

Key Differences:
- **LangChain**: Core building blocks and abstractions
- **LangGraph**: Complex workflow orchestration
- **LangFlow**: Visual development environment
- **LangSmith**: Monitoring and debugging

They work together as an ecosystem:
1. Build components with LangChain
2. Orchestrate workflows with LangGraph
3. Prototype visually with LangFlow
4. Monitor everything with LangSmith