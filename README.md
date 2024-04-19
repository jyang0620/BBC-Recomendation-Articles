# BBC-Recomendation_Articles

This project implements a simple [word2vec](https://arxiv.org/pdf/1301.3781.pdf) model on a database of word vectors from the [Stanford Glove Project](https://nlp.stanford.edu/projects/glove/) trained on a dump of Wikipedia. With the database, we organize them into a table by calculating the centroids of each text's vector and computing the similarity using Euclidean distance, outputting it into a local Flask Web Server.

To run the process, follow the subsequent steps:

1. In the terminal, go to the `~/data` dir and download the data:
```
wget https://s3-us-west-1.amazonaws.com/msan692/glove.6B.300d.txt.zip
wget https://s3-us-west-1.amazonaws.com/msan692/bbc.zip
```

2. Run `python doc2vec.py ~/data/glove.6B.300d.txt ~/data/bbc` in the terminal with the python files to get the articles.pkl and recommended.pkl files

3. Run `flask --app server run` to Run the Flask App. It should be running at `http://127.0.0.1/:5000` on your web browser. To go to a specific article, you can click on any hyperlink on the homepage, for example: `http://127.0.0.1/:5000/article/entertainment/303.txt`
