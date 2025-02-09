# reflexion-agent

The goal of this reflexion agent is to create a very detailed article about a topic we will provide.

```mermaid
%%{init: {'flowchart': {'curve': 'linear'}}}%%
graph TD;
	__start__([<p>__start__</p>]):::first
	draft(draft)
	execute_tools(execute_tools)
	revise(revise)
	__end__([<p>__end__</p>]):::last
	__start__ --> draft;
	draft --> execute_tools;
	execute_tools --> revise;
	revise -.-> draft;
	revise -.-> execute_tools;
	revise -.-> __end__;
	classDef default fill:#f2f0ff,line-height:1.2
	classDef first fill-opacity:0
	classDef last fill:#bfb6fc
```

### Tools for this project
- OpenAI GPT4 Turbo
- Function Calling
- Tavily (Search Engine)
- LangSmith

#### Prompting Concepts:
- **Ouput Parser** to get structure outputs

### Installation
After initialize the poetry project, you can add the following dependencies:
```sh
poetry add python-dotenv black isort langchain langchain-openai langgraph langchain-community
```

### Environment
Here is the template for the .env file:
```
OPENAI_API_KEY=<API Key from openai>
TAVILY_API_KEY=<Tavily API Key>
LANGCHAIN_API_KEY=<API Key from langsmith>
LANGCHAIN_TRACING_V2=true
LANGCHAIN_PROJECT=<name that will show up in the langsmith dashboard>
```

