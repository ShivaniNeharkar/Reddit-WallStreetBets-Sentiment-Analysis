# Reddit-WallStreetBets-Sentiment-Analysis


Hello Folks,
Utilizing natural language processing techniques to evaluate sentiment within r/wallstreetbets posts and comments. This analysis aims to reveal the community's overall market sentiment, influencing stock prices and trading strategies. Identifying stocks frequently discussed in the subreddit to pinpoint equities of interest. Tracking changes in mentions over time will uncover emerging trends and illustrate the impact of community sentiment on specific stocks.

What have we used?
VADER: NLTK's Sentiment Intensity Analyzer typically uses a pre-trained model.Each tokenized word was assigned a sentiment score using NLTK’s Sentiment Intensity Analyzer, which provides a compound score representing the overall sentiment (positive, negative, or neutral).
https://colab.research.google.com/drive/1wZj2RAKZmXD5M7Lbt68YPlFzvr_mOSX4

LSTM GloVe: We were not satisfied with Vader so we decided to build our own LSTM model to analyze the sentiment.
https://colab.research.google.com/drive/1V4LWMcpntNchafUH4_d7vWYzPpaHrH9C

Conclusion:
Our sentiment analysis of the WallStreetBets subreddit provides valuable insights into the emotions and sentiment expressed within this influential online community. We found that WallStreetBets exhibits a dynamic emotional tone, closely tied to real-world financial events and market performance. 
Emotions within the subreddit range from exuberance to frustration, reflecting the diverse sentiments of retail investors. 

With an example: "This stock is going to the moon! Can't wait for the gains!"

1. Preprocessing:
The comment is tokenized into individual words: ["This", "stock", "is", "going", "to", "the", "moon", "Can't", "wait", "for", "the", "gains"].
Common preprocessing steps like converting to lowercase, removing special characters, or stopwords may be applied.


2. GloVe Embeddings:
Each word is mapped to its corresponding GloVe vector (pre-trained on large datasets like Wikipedia).
For instance, GloVe may map the word "stock" to a 300-dimensional vector of real numbers that captures its meaning and context, while "moon" and "gains" would also have their own representations.
Now, the comment becomes a sequence of word vectors: [v("this"), v("stock"), v("is"), ..., v("gains")], where v(word) represents the GloVe embedding for each word.


3. LSTM Processing:
This sequence of word vectors is fed into an LSTM network.
LSTMs are great for capturing dependencies and relationships between words in a sequence. As the LSTM processes each word vector, it retains important context. For example:
It learns the phrase "going to the moon" as expressing excitement or optimism (since "moon" in finance slang can refer to high gains).
It also understands "Can't wait for the gains!" as a positive expression of anticipation.


4. Output Layer:
After the LSTM processes the sequence, it outputs a final representation summarizing the sentiment of the entire comment.
This representation is fed into a fully connected layer, followed by a softmax function (if classifying as positive/negative/neutral).
If the output is a high probability for "positive," the model predicts the comment is positive.


5. Prediction:
In this case, the model would likely classify the comment as positive, since the phrases "to the moon" and "gains" indicate optimism and excitement about future stock performance.


![SMDM](https://github.com/ShivaniNeharkar/Reddit-WallStreetBets-Sentiment-Analysis/assets/43198273/9aadb56e-bca3-4b3d-a563-2c6db95f20d4)


