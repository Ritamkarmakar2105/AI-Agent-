# AI-Agent-

Research Assistant

This project is a Python-based research assistant that leverages LangChain, Pydantic, and Together AI's language model to perform research tasks. It integrates tools like DuckDuckGo search, Wikipedia queries, and a custom text-saving tool to generate structured research outputs. The assistant processes user queries, retrieves relevant information, and saves the results to a text file in a structured format.

Features





Structured Output: Responses are formatted using a Pydantic model (ResearchResponse) with fields for topic, summary, sources, and tools used.



Tool Integration:





DuckDuckGo Search: Performs web searches for up-to-date information.



Wikipedia Query: Retrieves concise information from Wikipedia.



Text Saving Tool: Saves research outputs to a text file with timestamps.



Modular Design: Built with LangChain for easy extension with additional tools or models.



Configurable LLM: Uses Together AI's Llama-3-8b model with adjustable parameters like temperature.

Prerequisites





Python 3.8 or higher



A Together AI API key (sign up at Together AI to obtain one)

Installation





Clone the repository:

git clone <repository-url>
cd research-assistant



Create a virtual environment (optional but recommended):

python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate



Install the required dependencies:

pip install -r requirements.txt



Set up the Together AI API key:





Replace the TOGETHER_API_KEY variable in the script with your actual API key:

TOGETHER_API_KEY = "your-api-key-here"



Alternatively, set it as an environment variable:

export TOGETHER_API_KEY="your-api-key-here"

Usage





Run the script:

python research_assistant.py



Enter a research query when prompted (e.g., "What is the history of artificial intelligence?").



The assistant will:





Process the query using the configured tools.



Generate a structured response with a summary, sources, and tools used.



Save the output to research_output.txt.



View the results in the console and check research_output.txt for saved outputs.

Example Output

For the query "What is the history of artificial intelligence?":

ResearchResponse(
    topic="History of Artificial Intelligence",
    summary="Artificial Intelligence (AI) began in the 1950s with pioneers like Alan Turing. The term 'AI' was coined in 1956 at the Dartmouth Conference. Early AI focused on symbolic reasoning, followed by machine learning advancements in the 1980s. Deep learning and neural networks surged in the 2010s, driven by big data and GPU advancements.",
    sources=["https://en.wikipedia.org/wiki/Artificial_intelligence", "https://www.example.com/ai-history"],
    tools_used=["wikipedia", "search", "save_text_to_file"]
)

Saved to research_output.txt:

--- Research Output ---
Timestamp: 2025-05-16 21:47:23

Topic: History of Artificial Intelligence
Summary: Artificial Intelligence (AI) began in the 1950s...
Sources: https://en.wikipedia.org/wiki/Artificial_intelligence, https://www.example.com/ai-history
Tools Used: wikipedia, search, save_text_to_file

Project Structure





research_assistant.py: Main script containing the research assistant logic.



requirements.txt: List of Python dependencies.



research_output.txt: Output file where research results are saved (generated after running).

Dependencies

See requirements.txt for the full list of dependencies, including:





pydantic: For structured data modeling.



langchain-together: For integrating Together AI's LLM.



langchain-community: For tool integrations (Wikipedia, DuckDuckGo).



python-dateutil: For timestamp handling.

Notes





Ensure a stable internet connection for web-based tools (DuckDuckGo, Wikipedia).



The Together AI API key must be valid to use the LLM.



The output file (research_output.txt) is appended with each run, preserving previous research outputs.



Adjust the temperature parameter in the ChatTogether initialization for more deterministic or creative responses.

Troubleshooting





API Key Errors: Verify that the TOGETHER_API_KEY is correctly set and valid.



Dependency Issues: Ensure all packages in requirements.txt are installed correctly. Use pip install -r requirements.txt.



Parsing Errors: If the response fails to parse, check the raw response printed in the console for debugging.

