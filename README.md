# MIT-Fintech-Challenge

## Datasets:
We provide three datasets:
1. **data_small** has trade/order activities for 1 security. It has a file size of about 30MB, and it has around 180K rows. It would be a great starting point to analyze spoofying activity. 
2. **data_big** has trade/order activities for 3 securities. It has a file size of about 100MB, and it has around 550K rows. This data set would be suitable for someone who has more computational power and want to have a deeper understanding of the data
3. **data** has trade/order activities for 119 securities. It has a file size of about 1.5G, and it has around 8.5M rows. This is a very challening task for someone who want to deploy advanced computation or modeling tools. Good luck!

**data_small.zip** and **data_big.zip** can be found in the current repository, while **data.zip** can be downloaded from the following google drive link: https://drive.google.com/open?id=1h0BIGvj91L1hLErspeYkMRbnC2KzMxqK

## Code:
**wrapper.ipynb** can be found in the current repository. Functions to load datasets, to generate cohen's kappa score and to write results to csv files are provided. Students can code up the preprocessing step and classification model in the cell below *Insert Your Code Here*. Simple examples to preprocess data and to fit a logistic regression model is provided. More details are included in the wrapper.ipynb file. 

## Submission:
Please submit your results to the **Submission folder** as a zip file with the following naming convension:
* **Team_teamname.zip** 

The zip file should include four files:
* **Team_teamname.ppt**
* **Team_teamname_wrapper.ipynb**
* Training prediction probabilities:
  * **y_train_prob_pred_small.csv** or **y_train_prob_pred_big.csv** or **y_train_prob_pred.csv**
* Testing prediction probabilities:
  * **y_test_prob_pred_small.csv** or **y_test_prob_pred_big.csv** or **y_test_prob_pred.csv**

There is an example submission in the folder called **Team_test.zip** which includes all the files expect for the slides for your reference.

In case there are unforeseen difficulties submitting the zip files, as an alternative. You can email the zip files to peter@decrem.com or angelajin95@gmail.com

## Grading:
We will use Cohen's Kappa to evaluate the prediction results. https://en.wikipedia.org/wiki/Cohen%27s_kappa Extra points will also granted to teams which are working with more challenging datasets. Enjoy hacking!
