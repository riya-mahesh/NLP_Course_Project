This project compares different methods for information retrieval on the Cranfield dataset.

Cranfield dataset: https://ir-datasets.com/cranfield.html

Create a directory 'output' inside the main directory.

To obtain results, run main.py with the appropriate arguments.
```bash
python3 main.py [-custom] [-dataset <DATASET FOLDER>] [-out_folder <OUTPUT FOLDER>]
                [-segmenter (naive|punkt)] [-tokenizer (naive|ptb)]
                [-reducer (stemming|lemmatization)] [-lsa] [-doc2vec] [-word2vec] [-bm25]
```              
For example: python3 main.py -word2vec -reducer lemmatization
> Will run word2vec using lemmatization for inflection reduction

When the -custom flag is passed, the system will take a query from the user as input. For example:
> python main.py -custom
> Enter query below
> Papers on Aerodynamics
This will print the IDs of the five most relevant documents to the query to standard output.

When the flag is not passed, all the queries in the Cranfield dataset are considered and precision@k, recall@k, f-score@k, nDCG@k and the Mean Average Precision are computed.

In both the cases, *queries.txt files and *docs.txt files will be generated in the OUTPUT FOLDER after each stage of preprocessing of the documents and queries.


To perform hypothesis testing, run hypothesis_testing_main.py followed by hypothesis_testing.py
