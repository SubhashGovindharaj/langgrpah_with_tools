# 🤖 LangGraph ChatBot with Tools (LangChain + LangGraph)

A fully working conversational chatbot using **LangGraph**, enhanced with **tools like Wikipedia search**, and powered by **LangChain agents**. This notebook demonstrates how to create a **graph-based conversational agent** with dynamic tool calling and streaming capabilities.

---

## 🚀 Features

- Built with [LangGraph](https://python.langgraph.org/)
- Uses LangChain agents with **Tool calling**
- Includes **Wikipedia search tool** for answering real-world queries
- Streaming responses with `.stream()` API
- Mermaid graph visualization of your conversational graph
- Graceful handling of failed tool responses
- Basic structure to scale with more tools in the future (like calculator, search, etc.)

---

## 📂 File Structure

langgraph_with_tools/
├── langgraph_chatbot_with_tools.ipynb  <- Main implementation notebook
├── README.md                           <- You’re reading it

---

## 🧰 Requirements

Create a `requirements.txt` with the following content:

```txt
langchain
langgraph
openai
wikipedia
beautifulsoup4
lxml
IPython

🧠 How It Works
	•	A user sends a message like:
“Hi there, my name is Subhash”
	•	LangGraph starts at the START node → passes to chatbot → decides whether a tool is needed.
	•	If tools are triggered (e.g., “Wikipedia”), the graph routes to the Tool node and uses it.
	•	Once tool output is returned, conversation resumes with updated context.

⸻

🖼️ Graph Visualization

The flow is rendered with Mermaid:

from IPython.display import Image, display
display(Image(graph.get_graph().draw_mermaid_png()))

================================ Human Message =================================
Hi there, My name is Subhash

================================== Ai Message ==================================
Tool Calls:
  wikipedia (call_xxx)
  Args: query: subhash

================================= Tool Message =================================
Name: wikipedia
No good Wikipedia Search Result was found

================================== Ai Message ==================================
It seems like there isn't a lot of publicly available information about someone named Subhash...

🔭 Future Enhancements
	•	Add calculator/search tools
	•	Build Gradio or Streamlit UI
	•	Deploy as an API with FastAPI
	•	Add memory to the agent for contextual awareness

⸻

🧑‍💻 Author

Built with ❤️ by Subhash Govindharaj
