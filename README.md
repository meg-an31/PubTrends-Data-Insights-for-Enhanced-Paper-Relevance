# PubTrends-Data-Insights-for-Enhanced-Paper-Relevance
Assignment for the JetBrains internship 2025

## How to run
I have compiled my work into a Google Colab file for easy access. Please open the file using [this link](https://colab.research.google.com/drive/1iK4EsA_U7qivSoc8INfalE0mOu4KMOoy?usp=sharing), and there is also a copy of the code in this repo. The instructions below are also included in the colab file.

To choose the number of clusters the algorithm uses, please input an integer in the box `num_clusters`.

Also include the file named `PMIDs_list` before running by going to the left hand menu, and selecting **Files → Upload to session storage**.

To run the code, select **Runtime → Run all**.

The final graph will be displayed at the bottom of the page. *I am so sorry about how long it takes to run! eutils limits the number of API calls you can make without a key (and google colab is also hellishly slow).*

## Expected output
The output should look something like this: 

![image](https://github.com/user-attachments/assets/a7016a73-c204-4fd0-8d1a-92d0b8910448)

The colours represent the clustering, and the numbers attached to each point are the input articles that each dataset is related to. There is definitely scope to improve the quality of this output, based on the specific use case!


## Limitations
The most impactful limitation I came across is the fact that GEO Datasets cannot be queried to output an xml file (please see [here](https://www.ncbi.nlm.nih.gov/books/NBK25499/table/chapter4.T._valid_values_of__retmode_and/?report=objectonly)). This meant I could only use the shortform description given by the text output. Please see an example of the text I was working with in [this example API call](https://eutils.ncbi.nlm.nih.gov/entrez/eutils/efetch.fcgi?db=gds&id=200127892&rettype=xml). To comply with the specifications, I used the categories available to me: Title, Summary, Organism, Experiment type. The Overall design was not included in the api return text.
