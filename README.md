<H3>ENTER YOUR NAME : BASKARAN V</H3>
<H3>ENTER YOUR REGISTER NO.: 212222230020</H3>
<H3>DATE: </H3>
<H1 Align="center">Project Based Experiment<H1>
<H3>Objective:<H3>
Perform sentiment analysis using your Facebook data and count the number of Occurrences of my name in the extracted text.
<H3>Program:</H3>

~~~py
import json
from nltk.sentiment import SentimentIntensityAnalyzer

# Load Facebook data
with open('facebook_data.json') as f:
    data = json.load(f)

# Initialize sentiment analyzer
sia = SentimentIntensityAnalyzer()

# Count occurrences of term
term_count = 0

# Perform sentiment analysis
positive_count = 0
negative_count = 0
neutral_count = 0

for post in data['posts']:
    # Count occurrences of term
    term_count += post['message'].count('Syed Abdul Wasih')
    
    # Perform sentiment analysis
    sentiment_score = sia.polarity_scores(post['message'])
    if sentiment_score['compound'] > 0.05:
        positive_count += 1
    elif sentiment_score['compound'] < -0.05:
        negative_count += 1
    else:
        neutral_count += 1

print("Occurrences of 'Syed Abdul Wasih':", term_count)
print("Positive posts:", positive_count)
print("Negative posts:", negative_count)
print("Neutral posts:", neutral_count)
~~~

<H3>Output:</H3>

![AII](https://github.com/BaskaranV15/Project-Based-Experiment-AAI/assets/118703522/fbb349e6-edaa-443a-8b47-f04974cbd697)


<H3>Inference:</H3>

Through this project, I've learned about the process of parsing Facebook data, performing sentiment analysis, and counting occurrences of specific terms. I've gained insights into how to use Python libraries like NLTK for sentiment analysis and JSON for data parsing. Additionally, I've reinforced the importance of adapting code to different data structures and requirements.
