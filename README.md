# wasserstoff-AiTask
RAG Chatbot for Wordpress Site
This Colab notebook implements a system that can extract text from a Wordpress website and answer user questions about the extracted content.

Functionality:

Extract Text: The extract_text_from_website function fetches the HTML content of a given website URL, parses it using BeautifulSoup, and extracts the relevant textual content. It then cleans the text by removing unnecessary elements like whitespace and line breaks.
Chunking: The chunk_text function splits the extracted text into smaller, more manageable chunks of a specific size with some overlap between consecutive chunks.
Embedding and Indexing: The embed_and_index_text function embeds the text chunks using a pre-trained text-embedding model and indexes them in a ChromaDB collection for faster retrieval.
Retrieve Relevant Chunks: The retrieve_relevant_chunks function takes a user query and retrieves the most relevant text chunks from the indexed data (or directly from the chunks if indexing is not used) based on semantic similarity.
Generate Answer: The generate_answer function utilizes a large language model (LLM) to create an answer to the user's question using the retrieved text chunks as context.
Model and Libraries:

Text Extraction:
requests: For fetching website content.
BeautifulSoup: For parsing HTML content.
re: For regular expression based text cleaning.
Text Embedding (Optional):
transformers: Provides pre-trained text-embedding models (specifically AutoTokenizer and AutoModel from the transformers library are used).
Indexing (Optional):
chromadb: A database specifically designed for storing and querying multimedia data (including embeddings).
Question Answering:
groq: Client library for interacting with the Google AI Platform's Large Language Models (LLMs) like LaMDA. The specific LLM used within GROQ depends on the chosen model identifier (e.g., "llama3-70b-8192").
Running the Colab Notebook:

Upload this Colab notebook to your Github repository.
Open the notebook in Colab.
Replace "groq-api-key" in the generate_answer function with your actual GROQ API key.
Run the notebook cells.
The notebook will prompt you to enter a website URL. After extracting the text, it will enter a loop where you can ask questions about the website content. Type "END" (uppercase or lowercase) to exit the loop.
