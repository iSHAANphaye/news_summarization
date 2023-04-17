# NLP Pipeline for News Summarization

## Introduction:
This NLP pipeline aims to summarize news articles scraped from various sources by removing redundant and unnecessary sentences from the content. The pipeline uses TF-IDF to identify the most important sentences in the article and generates a summary based on these sentences. The summary can then be used for further NLP tasks such as named entity recognition.

## Requirements:

1. Python 3.6 or higher
2. pandas library
3. numpy library
4. scikit-learn package
5. nltk package

## Usage:

1. Ensure that the above requirements are installed.
2. Clone the repository to your local machine.
3. Open the 'news_summarization.ipynb' file in a Jupyter Notebook or a Python IDE.
4. Modify the 'df' variable to point to the location of the news dataset provided in the assignment or download it through this link: https://drive.google.com/file/d/1KsWWrhGaK0_IMXPaYBOEXXE8IExqogmJ.
5. Run the code in each cell sequentially.

## Code Explanation:

1. The news dataset is loaded using pandas. 
2. Convert the 'content' column of this dataset into 'str' type using 'astype' method; and introduce a new column 'Original Content' in the dataframe, which is a copy of 'content' column.
3. 'Original Metrics' column is made in the dataframe which contains various metrics about the content such as word count, sentence count, average word length, etc.
4. The 'train_set' and 'test_set' dataframes are defined by doing a 10-90 split on the news dataset.
5. A TF-IDF vectorizer is fit on the training dataset to obtain the IDF scores of the words.
6. The cleaned responses are generated for the test set by first constructing a similarity matrix using cosine similarity between the TF-IDF vectors of each sentence in the article. The sentences with the highest similarity scores are retained and concatenated to form the cleaned response.
7. The various new metrics of the new content are calculated and added to the test set dataframe.
8. We then remove redundant columns and retain the 'Original Content', 'Original Metrics', 'New Content', 'New Metrics', 'Removed Lines' columns.

Note: The last cell of code is commented out because it writes the result to a CSV file, and its output path is specific to the author's system. You will need to modify this path to write the output file to your desired location, although the final output CSV file named 'test_cleaned_responses.csv' is available in the repository.

## Output:

The output DataFrame, in this case named test_set(modified after the due processes, ofcourse) is saved as a CSV file in the same directory as the 'news_summarization.ipynb' file. The CSV file contains the following columns: Original Content, New Content, Removed Lines, and Old Metrics.
![Screenshot 2023-04-17 194031](https://user-images.githubusercontent.com/75660041/232510543-ca06b3eb-2e07-4e08-a97b-d7ea1f5e7e2e.png)


## Conclusion:
This NLP pipeline provides an efficient way to summarize news articles by removing unnecessary and redundant sentences from the content. The pipeline can be further extended to perform other NLP tasks such as sentiment analysis, topic modeling, and entity recognition.



