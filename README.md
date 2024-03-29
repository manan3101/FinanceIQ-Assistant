# FinanceIQ

FinanceIQ represents a seamless integration of cutting-edge technologies, including langchain, OpenAI, and Streamlit, converging to deliver a transformative news research solution. This innovative platform is meticulously crafted to provide users with swift access to invaluable insights from the expansive realm of financial news articles.

Gone are the days of laboriously sifting through lengthy articles to extract pertinent information. FinanceIQ revolutionizes the research landscape by offering a streamlined experience where users can effortlessly tap into the wealth of knowledge embedded within news articles. By simply providing the URL and articulating their queries, users can navigate through complex financial narratives with remarkable ease.

With an intuitive interface designed for accessibility and efficiency, FinanceIQ redefines the paradigm of traditional research methodologies. By saving users valuable time and enhancing productivity, this tool serves as an indispensable asset in the arsenal of professionals and enthusiasts alike.

Beyond its functional prowess, FinanceIQ stands as a testament to the power of informed decision-making in the dynamic arena of finance. Whether it's tracking market trends, analyzing stock performance, or staying abreast of financial news developments, FinanceIQ empowers users to glean actionable insights with unparalleled convenience.

Embrace the future of financial research with FinanceIQ – where effortless information retrieval converges with unparalleled convenience to unlock the boundless potential of financial news analysis.

# Installation and setup
Follow these steps to install and run the FinanceIQ project:
1. Clone the repository to your local machine using the following command:
   ```bash
   git clone https://github.com/manan3101/FinanceIQ.git
2. Install necessary dependencies using pip:
   ```bash
   pip install -r requirements.txt
3. Set up your OpenAI API and Modify the .env file to include your API key:
   ```bash
   OPENAI_API_KEY="enter your key"
4. Run the project using Streamlit:
   ```bash
   streamlit run main.py
   ```

# Project Workflow

This project operates in two main phases:

## Phase 1: Creating Knowledge Base

1. **Data Extraction from URL**:
   - User provides a URL.
   - The project utilizes `UnstructuredURLLoader()` and `load()` to load and extract data from the provided URL article.
   - The loaded data is then prepared for further processing.

2. **Text Chunking**:
   - The loaded data is split into manageable chunks using `split_documents()`.
   - This step breaks down the text into smaller sections, facilitating efficient processing.

3. **Embedding Generation and Vector Database Creation**:
   - Embeddings are created for all the text chunks using `OpenAIEmbeddings()`.
   - Embeddings capture the semantic representations of the text, enabling meaningful analysis.
   - A vector database is constructed using `FAISS`, indexing the embeddings of the text chunks for fast and effective retrieval of relevant information.

## Phase 2: Retrieval of Knowledge

1. **Selection of Relevant Embeddings**:
   - The relevant embedding of the chunk is selected using `RetrievalQAWithSourcesChain`.

2. **Answering Queries**:
   - The OpenAI model is employed to answer queries from the selected chunk.
   - An instance of the OpenAI model is created with specific parameters `OpenAI(model="gpt-3.5-turbo-instruct")`.
   - Queries are answered using this model.

3. **Displaying Answers**:
   - The answers are displayed on the prompt for user interaction.

By following these steps, the project effectively retrieves and presents relevant information based on user queries, leveraging the established knowledge base.
