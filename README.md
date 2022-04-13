# Concordia University

Gina Cody School of Engineering and Computer Science

Machine Learning
(COMP6321)

# Instructor:

Dr. Mirco Ravanelli

# Submitted By:

Amir Bahador Eizadkhah

Amin Nazarian Saralang

____________________________________________________________________________________________________________________________________________________________________

# NLP With Amazon Crawling Comments, LSTM, Sk-Learn
(Review Rating Prediction)


The primary purpose of the following project is to predict the rates of comments submitted by people who purchased the item on Amazon. Five different famous classifiers do the projects to test and measure the classifiers' accuracy when they face actual, live data. The models are designed to process the text as the matrix of features, and the targets are rates in the range of one to five.

The classifications are done by five different popular classifiers with Sk-Learn and PyTorch:

• Gaussian Naïve Bayes

• Support Vector Machine

• Long-Short Time Memory (LSTM)

• K-Nearest Neighbors

• Random Forest

___________________________________________________

The notebook consists of seven separate sections:

1- Importing Libraries

This part is just for importing all essential libraries which we need in order to run the project.
Then If you are working with Google Colab, you must unlock the Google Drive to access the resources such as Dataset and model Weights.
Also, there are some methods to plot the models that we need down the road.

** You can skip part 2, 3, 4  with importing 'Reviews_Modified.csv' directly to your code from Link below **

https://drive.google.com/file/d/1vCIvjK6l9vp2Tec5IkO_Aokn0V6oYhVI/view?usp=sharing

** This data frame is composed of all data, gathered right after preprocessing part **

** Otherwise, you must download dataset from the link below and convert it into .csv and continue **

https://forms.gle/UEkkJs69e7Z5A5Ps9

2- Importing Dataset

Convert .json to .csv

Open the .csv file and change the column name for rates and reviews into 'SCORE' and 'TEXT' and save it.

In case you want to use another dataset, if you have .csv dataset you have to skip the first cell of code.

Note: you need to capitalize the column names because 'TabularDataset' library in PyTorch only works with the Capital column header!!

3- Crawling

There are 3 blocks of code in this part. Just run the first one.
During running second block you will be asked to enter a link which must be for Amazon and must be begins with https://, otherwise you will face an error.
Note: Your browser must be updated to the least version. If there is a contradiction with your version and a version in the Header (First code block if crawling), just you need to copy yours and paste it in the Header.

the link that I used is:

https://www.amazon.com/Apple-iPhone-XR-Fully-Unlocked/product-reviews/B07P6Y7954/ref=cm_cr_arp_d_paging_btm_next_0?ie=UTF8&reviewerType=all_reviews&pageNumber=0

If you aim to use another link, it is better to looking for a product with huge amount of comments.
Also, you have to bear in mind that the dataset is about Cellphones and Mobile Accessories. So, you will end up with poor prediction if you use a product from a different category. 

In order copy another link, follow the below instruction:

- Select a product.
- Scroll down when you see 'See all reviews >' and click on it
- Scroll down again and click on 'Next page' button.
- Copy the link and paste it into the Python Input

Crawling might take a while.
At the end you must see some rows of comments. Else, check the Header Version or check if you copy and paste the link correctly.

4- Data Preprocessing

This part will run without any trouble.

5- Classification

All models are from sk-learn library
You can easily classify your data. Also, feel free to change the Hyperparameters.

6- LSTM

** It is better to run the LSTM with Colab GPU **

In this part we use LSTM as below

LSTM(
  (embedding): Embedding(27253, 128)
  (rnn): LSTM(128, 256, batch_first=True)
  (linear): Linear(in_features=256, out_features=5, bias=True)
)

The input dimension is the length of X_torch_v.vocab
Embedding size is 128
Hidden size is equal to 256
And obviously we have only 5 classes which is our output

Easily you can start to train the code with 25 epochs.
Between 20-25 you can select one. Otherwise the model will overfit if the number of epochs is greater than 25

Note: If you want to skip this part just upload 'model_parameters.pth' to your notebook
You can add it in 6.2.2 part in model training

7- Overall Results

In the final part you can run two blocks of code, and you can observe two plots indicating Accuracy and F1-Score of all classifiers.
