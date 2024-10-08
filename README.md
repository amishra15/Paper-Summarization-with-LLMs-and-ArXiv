# Paper-Summarization-with-LLMs-and-ArXiv

This project implements a system that retrieves relevant research papers from the ArXiv API, extracts their abstracts, and generates concise summaries using a Large Language Model (LLM) from Hugging Face's Transformers library. The system allows users to search for papers by a query, displays the paper titles and authors, and provides summaries of each paper.

## Features

- **Paper Retrieval**: Fetches relevant papers from ArXiv using the ArXiv API based on user queries.
- **Summarization**: Uses a pre-trained summarization model (`facebook/bart-large-cnn`) from Hugging Face to generate summaries of paper abstracts.
- **Interactive UI**: Provides a simple user interface using `ipywidgets` where users can enter a search query and specify the number of papers to retrieve and summarize.

## Requirements

The following Python packages are required for running this project:

- `transformers` - for text summarization.
- `arxiv` - for fetching papers from the ArXiv API.
- `ipywidgets` - for building the interactive user interface in Jupyter notebooks.

Install all necessary packages using:

```sh
pip install transformers arxiv ipywidgets
```

## How to Run

1. Open the project in Google Colab or a Jupyter Notebook environment.
2. Run the entire script to install dependencies and load necessary libraries.
3. The user interface will allow you to enter a query and the number of papers to retrieve.
4. Click the **"Search"** button to fetch and display the paper titles, authors, summaries, and links to the full papers.

## Usage

- **Enter a Query**: Use the text box labeled "Query" to enter keywords to search for relevant papers on ArXiv (e.g., "AI in Finance").
- **Number of Papers**: Use the integer input box to specify how many papers to retrieve (from 1 to 20).
- **View Summaries**: After clicking **"Search"**, the titles, authors, and summaries of the specified number of papers are displayed.

## Code Overview

### Key Functions

- **`fetch_papers(query, max_results=5)`**: Retrieves research papers from ArXiv based on the search query.
- **`summarize_text(text)`**: Summarizes the given text using the `facebook/bart-large-cnn` model. The `max_length` and `min_length` are adaptively set based on the input length to ensure high-quality summaries.
- **`display_paper_details_and_summaries(papers)`**: Displays the titles, authors, and summaries of the retrieved papers, as well as a link to the PDF of each paper.

### Example Output

After running the script and entering a query, you'll see outputs like:

- **Title**: Paper Title Here
- **Authors**: Author Names Here
- **Summary**: Generated Summary Here

## Known Issues

- The summary length is adaptively set based on the input text length. In cases where the abstract is very short, the summarizer may produce a warning, which has been mitigated by adjusting the `max_length` and `min_length` dynamically.
- Make sure to run the script in an environment that supports `ipywidgets`, such as Google Colab or Jupyter Notebook.

## Future Improvements

- **Improving UI**: Add more interactive elements to allow users to refine searches, such as filtering by publication date or subject.
- **Extended Summarization**: Summarize specific sections from the full text of papers instead of just abstracts.
- **Paper Storage**: Add functionality to save the summaries and details to a file for future reference.

## License

This project is licensed under the MIT License.

## Acknowledgements

- **ArXiv** for providing a comprehensive API to access research papers.
- **Hugging Face** for the easy-to-use `transformers` library.
- **Google Colab** for providing an accessible environment to run this project.

## Contact

For questions or suggestions, please feel free to reach out or submit a pull request on GitHub.
