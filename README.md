EXPECTED OUTPUT:
Overall Response: The aim is to categorize text-based sentiment as positive, neutral, or negative, based on the following thresholds: 
Positive: If 80% or more of the sentiment is positive.
Neutral: If the sentiment is between 50% and 55% positive.
Negative: If the sentiment is 49% or less positive.

Expressed Sentiment: The task is to analyze text and identify the primary emotion expressed. This involves determining whether the text conveys happiness, sadness, anger, fear, surprise, disgust, love (including affection, adoration, passion, and compassion), jealousy, guilt, pride, hope, or empathy.
Positive Percentage: To quantify the positivity of the text, assigning a numerical value to its positive sentiment. This involves analyzing the text for positive language, positive emotions, and other indicators of positivity. The higher the numerical value, the more positive the text is deemed to be.
Negative Percentage: To quantify the negativity of the text, assigning a numerical value to its negative sentiment. This involves analyzing the text for negative language, negative emotions, and other indicators of negativity. The higher the numerical value, the more negative the text is deemed to be.
Neutral Percentage: To quantify the neutrality of the text, assigning a numerical value to its neutral sentiment.


	The performance evaluation was conducted in a three-phased approach, each stage progressively delving deeper into specific parameters: data volume, input method, and prompt format.

Stage 1: Baseline Assessment

In the initial phase, a fundamental evaluation was conducted. Prompts, accompanied by relevant context and explicit instructions, were fed to the language model. The model's ability to process and comprehend these inputs, and subsequently generate accurate and relevant outputs, was assessed. This baseline evaluation established a benchmark against which subsequent stages could be compared.

“
prompt=""" Analyze the following product review and categorize it as positive, negative, or neutral. Here Is your reviews...

Look like old product, volume decrease button not working properly if you hold it for 1-2 sec then its decreased the volume, cushions cover is clearly visible, ear Bar is also very tight..!! First' time' I returned any electronic product in the Amazon disappointing from Amazon and zeb.But headphone is okay. In this price range good sound quality.. ear cushions is also comfortable!!Good headphone you can go for it.!!Thank you

Quite good product from zebronics...button quality is slightly low and based is also low kind ...bt at this price battery durability is the best and overall sound quality...Clarity is good..so it is value for money...!

Very important : You have to build the answer based on the.....

Stage 2: Scalability Testing

To gauge the model's scalability and potential, the number of prompts was significantly increased. This phase aimed to determine the model's capacity to handle larger datasets without compromising accuracy or efficiency. The model's ability to maintain accurate and consistent performance, even when faced with a substantial increase in input, was a key focus of this stage. Additionally, the model's efficiency in processing and analyzing information was evaluated.

sentences = []
review_test1 = “Look like old product, volume decrease button not working properly if you hold it for 1-2 sec then its decreased the volume, cushions cover is clearly visible, ear Bar is also very tight..!! First' time' I returned any electronic product in the Amazon disappointing from Amazon and zeb.But headphone is okay. In this price range good sound quality.. ear cushions is also comfortable!!Good headphone you can go for it.!!Thank you
”

review_test2 = “Quite good product from zebronics...button quality is slightly low and based is also low kind ...bt at this price battery durability is the best and overall sound quality...Clarity is good..so it is value for money...!
”

# Constructing the Prompt for the Model
context=f""" Analyze the following Reviews and categorize it as positive, negative, or neutral.{sentences}
 
You have to build the answer based on the ......


Stage 3: Data Input Optimization

The final stage focused on optimizing the data input process. A dataset was directly read from a .txt file, stored in a structured format (array), and then fed to the model. This approach streamlined the data ingestion process, eliminating the need for manual intervention and reducing potential errors. By automating the data input process, the model could efficiently process large volumes of review data, leading to improved performance and scalability.

“
sentences = []
with open('Review Dataset.txt', 'r') as file:
    for line in file:
        line = line.strip()  # Remove leading/trailing whitespace
        if line:  # Check if line is not empty
            sentences.append(line)

# Constructing the Prompt for the Model
context=f""" Analyze the following Reviews and categorize it as positive, negative, or neutral.{sentences}
 
You have to build the answer based on the .....


















NOTE: There are 100+ Reviews has been used for the Model Training and the Datasets has divided into two separated files as .txt and .csv files respectively.
