# Overview of the Analysis: 

The goal of this project was to help Alphabet Soup, a non-profit organization, improve their rate of successful ventures through machine learning and neural networks. 

The dataset provided by Alphabet Soup included 34,000 organizations that have previously received funding and information such as, application type, classification, and success status. It is important to confidently and accurately select recipients in order to continue this practice and provide support to organizations that are successfully making a difference.

This dataset was uploaded to Google Colab and converted to a data frame using Pandas, and evaluated as a neural network model using scikit-learn and tensorflow.

# Results

* Data Preprocessing
    * The target variable for this model was the boolean response from the "IS_SUCCESSFUL" column (0 = not successful, 1 = successful).
    * The feature variables are all other variables not eliminated from the data frame, including AFFILIATION, APPLICATION_TYPE, CLASSIFICATION, USE_CASE, ORGANIZATION	STATUS, INCOME_AMT,        SPECIAL_CONSIDERATIONS, and ASK_AMT. Both the APPLICATION_TYPE and CLASSIFICATION variables were simplify to remove outliers to provide a better focus on the dataset.
    * The first attempt, both the NAME and EIN were removed from the data frame as they are seen as irrelevant as they are not numerical.

* Compiling, Training, and Evaluating the Model
    * For both the original and optimized models I used 2 hidden layers with 80 neurons in layer 1 and 30 neurons in layer 2. Having more than 1 hidden layer is needed in deep learning to develop an understanding of there non-linear relationships. There are only about 10 input features so the number of neurons should remain around 5x that amount, I chose 30 and 80 to provide a variety. The rectified linear unit activation function was selected due to the need for a simplified and non-negative output for this complex model.
 <img width="913" alt="defineModel" src="https://github.com/mhanson16/deep-learning-challenge/assets/119544491/a8275601-924a-4efb-98f6-530fedc3f739">

    * The first model included the layers and functions mentioned above with both the EIN and NAME variables removed. This model resulted in a 73.07% accuracy rate, not meeting the goal of 75% accuracy. 
    <img width="684" alt="model1acc" src="https://github.com/mhanson16/deep-learning-challenge/assets/119544491/1be4c412-b28d-4588-b8fb-6b898f4fdcfc">

    
    After many attempts of changing the model in ways of removing non-numerical columns, adding layers, adding and removing neurons and epochs, I saw little to no improvement in the accuracy levels. I then decided to start back from the original model, and make small adjustments from there. I added back the NAME variable and followed the same practice of filter done on the other variables. There were 19,568 unique organization names, therefore many must have multiple instance of observation. Using the value_counts() function, I removed any names with less than 100 instances. Keeping the layers, functions, and neurons the same as the first model I was able to achieve 75.65% accuracy.
    
    <img width="626" alt="model2acc" src="https://github.com/mhanson16/deep-learning-challenge/assets/119544491/d08d42e9-c403-45e7-b7d7-c680e1399a78">


* Summary
    With the use of deep learning, I was able to develop a model resulting in the desired accuracy level without removing too much of the original data. Though the NAME variable was originally seen as irrelevant it ended up being a key factor in reaching the end goal. I would recommend this process in for Alphabet Soup to determine their future ventures.


Crediting Module 21 - Neutral Networks Deep Learning Module of UC Berkeley Data Analytics Bootcamp for source code to develop and assist with the creation of this model.
