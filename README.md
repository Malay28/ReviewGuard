# ReviewGuard
Model combats fake consumer reviews using a DFFNN to detect fraudulent content. 


## Emotion features

### Please note the following before executing either of the ipynb files:

1. Our proposed model uses a publicy available amazon review dataset from kaggle (https://www.kaggle.com/datasets/lievgarcia/amazon-reviews). The file can be found at "datasets/amazon_reviews.txt"

2. In order to capture the relationship between spurious reviews and emotion representation, 30 emotion features were extracted from the "datasets/amazon_reviews.txt" using 9 emotion lexicons. The resultant features were added to the dataset and saved as "datasets/amazon_reviews_features.txt"

3. The code used to extract the aforementioned emotion features can be found in "Emotion_Feature_Generation.ipynb". Recomputing these features requires Java 1.6+. It also requires extraction of all the lexicons from "emotion_lexicons.zip" (In case of extraction, do not modify the default path for extraction destination). 
Our advice would be to NOT execute "Emotion_Feature_Generation.ipynb" as it consumes significant disk space and time.

4. The code for the rest of the project (including preprocessing, remaining feature extraction, model training, validation) can be found in "Fake_Review_Detection.ipynb" (this uses "datasets/amazon_reviews_features.txt"). It has the following dependencies:
	a. nltk
	b. pandas
	c. re
	d. sklearn
	e. matplotlib
	f. gensim
	g. tensorflow



### Running the main project code:

Execute "Fake_Review_Detection.ipynb" cell by cell.

### References for the 30 emotion indicators:


4 polarity-based (count of words belonging to pos and neg word list from each of the two lexicons):

	1. OpinionFinder: https://mpqa.cs.pitt.edu/opinionfinder/opinionfinder_2/
	2. Bing Liu's opinion lexicon: https://www.cs.uic.edu/~liub/FBS/sentiment-analysis.html#lexicon
		

10 strength-based  (positive and negative score from each of the five lexicons)

	1. Afinn: https://github.com/fnielsen/afinn
	2. S140: http://saifmohammad.com/WebPages/lexicons.html
	3. SentiWordNet 3.0: https://github.com/aesuli/SentiWordNet	
	4. NRC Hashtag: http://saifmohammad.com/WebPages/lexicons.html    				
	5. Emoticon: http://saifmohammad.com/WebPages/lexicons.html 
		     http://saifmohammad.com/WebDocs/NRC-Emoticon-Lexicon-v1.0.zip (for downloading the lexicon)	


3. 16 emotion-based   (8 emotion scores from NRC emotion, 8 emotion scores from NRC expanded)

	1. NRC emotion lexicon (emolex): 
		https://saifmohammad.com/WebPages/NRC-Emotion-Lexicon.htm
	 	https://pypi.org/project/NRCLex/
	2. NRC expanded: https://ieeexplore.ieee.org/document/7817108



