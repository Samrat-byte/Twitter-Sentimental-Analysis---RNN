**Twitter Sentimental Analysis using RNN and LSTM**

**Step 1**: Downloading and Uploading dataset
First, we will download the twitter sentiment dataset from Kaggle the link is given below:

Dataset Link: https://www.kaggle.com/datasets/abhi8923shriv/sentiment-analysis-dataset?select=train.csv

After downloading this the word in labels as follows:

Negative Sentiment: 0

Positive Sentiment: 1

After this we will upload the data on our drive that we will mount on the Google Colab.

**Step 2**: Changing runtime and loading the data in Colab
Create a new notebook in Colab
Go on the Runtime tab and change the Runtime type to GPU and save it. Mount the Drive in which you uploaded the Dataset you want to train the model.

Output



**Step 3**: Vectorizing the embedded dataset
Now we will run to vectorize the words.
And load it into the dictionary function so it can be called directly.

**Step 4**: Downloading required NLP libraries and Tokenizing the data
Download wordnet and omw file to deal with string data from NLP library After this we will tokenize the data. Which divides the data into small parts, so the sentences become easier to use or translate into other language or format. After this we will Lemmatizer our data. Lemmatizer will convert the words to the most common form of that word or the most used similar word so it is easier to detect.

Required Lib:

nltk.download('omw-1.4')

nltk.download('wordnet')

Output Before tokenizing:



After tokenizing:



Before Lemmatizer:



After Lemmatizer:



**Step 5**: Vectorizing and Dividing Test and Training data
Now we will create a function that will loop and vectorize the data and return as a float/decimal valued data. Now we will divide the data into training and testing with 70% for training and 30% for testing which is considered a standard.

**Step 6**: Finding out the overall size of data and padding
We will define df_to_X_y so we can count the sentences size Then will plot to see the max and min num of tokens our dataset has in a sentence.
After this we will pad our dataset to the max size of the token, so we don't get bad results. So, our training is accurate, and our shape of data is relevant.
Function for counting the token size for our dataset Now we print and get an output graph for the token size





**Step 7**: Modeling RNN
We will create our model by designing Lstm, Dropout, Dense and flatten layer. We will get lstm layers to assign weights Dropout to remove overfitting Dense to get the most values Then flatten to get the output layer.

We are using shape 57 as the max token size is 50 Using three LSTM layers and 64 sized filter Dropout of 0.2 so our model doesn't over fit Flatten over layer in the end And dense to get the values and sigmoid activation function because it's a binary class.



**Step 8**: Compiling model
First, we are defining the location where we want to save our trained weights.
Optimizer we used is Adam.
Loss is Binary Crossentropy.

**Step 9:** Fitting the model
Now we will fit our model using the fit command. We are giving 20 epochs to train our data.

**Step 10:** Loading our model and printing the accuracy of our model
Now we will load our trained model and the weights. The give it a test data to get the accuracy of our model given below.

Output:



We have accuracy of positive sentiment: 88 %

We have accuracy of negative sentiment: 81 %

**Step 11:** Now we will give it a tweet to check if it gives good results
Output:



Actual: Positive Sentiment

Predicted: Positive Sentiment



Actual: Negative Sentiment

Predicted: Negative Sentiment

Twitter-Sentiment-Analysis-using-RNN-LSTM/README.md at main · AHMEDSANA/Twitter-Sentiment-Analysis-using-RNN-LSTM

