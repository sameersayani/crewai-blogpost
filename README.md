# AI Trends Blog Post Generator

This project uses a small [CrewAI](https://docs.crewai.com/) crew to research current AI industry trends on the web and turn the findings into a concise Markdown blog post.

## How It Works

The notebook, [`crewai-blogpost.ipynb`](crewai-blogpost.ipynb), defines two agents:

| Agent | Responsibility |
| --- | --- |
| Market Research Analyst | Uses `WebsiteSearchTool` to research current AI trends and summarize the top three developments and their impact. |
| Content Writer | Uses the research summary to write an engaging, four-paragraph blog post in Markdown. |

CrewAI runs the research task before the writing task. The generated post is saved to `blog-posts/news.md`.

## Requirements

- Python and Jupyter support in VS Code, or another Jupyter environment
- An OpenAI API key
- Internet access for web research and model requests

The notebook installs its Python packages in the first cell:

```text
crewai
crewai_tools
langchain
langchain_community
langchain_openai
```

## Setup and Run

1. Set `OPENAI_API_KEY` in the environment before starting the notebook kernel. In PowerShell, for the current terminal session:

	```powershell
	$env:OPENAI_API_KEY = "your-openai-api-key"
	```

	Do not paste API keys into the notebook or commit them to source control.

2. Open `crewai-blogpost.ipynb` and select a Python kernel.
3. Run the notebook cells from top to bottom. The first cell installs the dependencies; later cells configure the search tool, language model, agents, and tasks, then start the crew.
4. Ensure the `blog-posts` directory exists in the project folder. The final task writes `blog-posts/news.md`.

The research reflects what the web search tool can find when the notebook is run; review sources and generated claims before publishing.
