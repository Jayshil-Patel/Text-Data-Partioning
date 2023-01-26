# Gutenberg Sampler
This script is used to download multiple books from Project Gutenberg, sample them into 200 partitions of 100 words each, and organize the data into a single Pandas DataFrame with a label column.
## Requirements
Python 3
Pandas
Requests

## Function Description
'sample_books(book_urls, labels)' : This function takes two lists as arguments: 'book_urls' and 'labels'. It uses the 'zip' function to iterate over the two lists in parallel and pass the corresponding book URL and label to the 'sample_book' function that I showed you earlier. It also creates an empty list called 'dataframes' to store the DataFrames. Inside the for loop, 'sample_book' function is called for each url and label, and the returned dataframe is appended to 'dataframes' list. After the for loop, the dataframes in the list are concatenated into a single DataFrame using the 'pd.concat()' function and stored in the 'final_df' variable. Finally, the 'final_df' is returned.

## Usage
1. Download the script
2. In the script, provide the URLs of the books you want to download in the 'book_urls' list and the corresponding labels in the 'labels' list.
3. Run the script by executing 'Text_Data_Partioning.ipynb' in the command line
4. The script will return a single DataFrame containing the sampled text partitions and their corresponding labels.
## Example
```python
book_urls = ['http://www.gutenberg.org/files/1342/1342-0.txt', 'http://www.gutenberg.org/files/84/84-0.txt']
labels = ['Pride and Prejudice', 'Frankenstein']
df = sample_books(book_urls, labels)

```
This example downloads the books "Pride and Prejudice" and "Frankenstein" from Project Gutenberg and samples them into 200 partitions of 100 words each. The resulting DataFrame, df, will have a label column with the labels "Pride and Prejudice" and "Frankenstein", and a text column with the corresponding text partitions.
