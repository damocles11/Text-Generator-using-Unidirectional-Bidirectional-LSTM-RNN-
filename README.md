# Text-Generator-using-Unidirectional-Bidirectional-LSTM-RNN-
Text generation is a subfield of natural language processing. It leverages knowledge in computational linguistics and artificial intelligence to automatically generate natural language texts, which can satisfy certain communicative requirements. The purpose of this project is to discuss about text generation, using machine learning approaches, especially Recurrent Neural Networks (RNN). 
# Neural Network for Generating Sentence 
Instead of a simple LSTM, I have used a bidirectional LSTM architecture. This network configuration converges faster than a single LSTM, and from empiric tests, seems better in term of accuracy. 
I have used Keras, which require less effort to create the network of is more readable than conventional TensorFlow code. 
#  QUICK OVERVIEW
We are going to learn the dependencies between characters and the conditional probabilities of characters in sequences so that we can in turn generate wholly new and original sequences of characters. 
We will perform the following steps to construct the model 

1)Scrape reviews form Amazon

2)Take those reviews as an input and convert the words into tokens using a tokenizer 

3)Convert the sequence of tokens into N-gram sequences of predictors and labels 

4)Now as the sequences are not of same size we have to pad the and make their size same 

5)Now we first build a LSTM network with two layers each with 100 neurons and a dropout of 10% at each layer ,the loss function used here is categorical cross entropy and the optimizer is adam. 

6)We train the network using the data we prepared,after training it we would note the loss. 

7)We give a seed value to the network and it returns an array of 0’s and the one sequence number which is predicted, we decode the array to find the word and append it to a string. 

8)Now we build a bidirectional LSTM network with 1 layer and 256 neurons with a drop put rate of 40% and loss function as categorical cross entropy and optimizer as adam 

9)We repeat steps 5-7 
 
10)We compare both the models 

# IMPLEMENTATION & RESULTS
Firstly we scrapped the amazon site for fetching reviews of One plus phone(link: https://www.amazon.in/OnePlus-Mirror-Black-128GB-Storage/product-reviews/B07DJD1Y3Q/ref=cm_cr_getr_d_paging_btm_next_8?ie=UTF8&reviewerType=all_reviews&pageNumber=8) like wise we did the same for pages 6 & 7 as well. This scrapping part was done normally using local machine's jupyter notebook and after succesfully running we were provided with three datasets. During scrapping , we mainly took the columns from the site namely rating , title , date & body which were stored using tags like //a , //i , //span. Rest all were ignored . 

Now after fetching of datasets we were to run both uni-directional & bi-directional codes. Since the dataset acquired is quite large we used kaggle notebooks for running having a support of GPU. GPU was required for mainly training of such huge file and also as the size of the batch file we mentioned was 400 with 100 epochs. 

