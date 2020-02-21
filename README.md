# MIT-Fintech-Challenge

## Datasets:
We provide three datasets:
1. **data_small** has trade/order activities for 2 securities. It has a file size of about 30MB, and it has around 200K rows. It would be a great starting point to analyze spoofying activity. 
2. **data_big** has trade/order activities for 4 securities. It has a file size of about 400MB, and it has around 2M rows. This data set would be suitable for someone who has more computational power and want to have a deeper understanding of the data
3. **data** has trade/order activities for 119 securities. It has a file size of about 1.5G, and it has around 8.5M rows. This is a very challening task for someone who want to deploy advanced computation or modeling tools. Good luck!

**data_small.zip**, **data_big.zip**, and **data.zip** can be downloaded from the following google drive link: https://drive.google.com/open?id=1h0BIGvj91L1hLErspeYkMRbnC2KzMxqK

## Code:
**wrapper.ipynb** can be found in the current repository. Functions to load datasets, to generate cohen's kappa score and to write results to csv files are provided. Students can code up the preprocessing step and classification model in the cell below **Insert Your Code Here**. Simple examples to preprocess data and to fit a logistic regression model is provided. More details are included in the wrapper.ipynb file. 

#### Classification guidelines
We encourage groups to come up with creative solutions. To give you a head start, we have come up with some simple suggestions and guidelins. The following points would be helpful for you to train a great classifier to identify spoofiers.
- K-fold cross validation can help you comparing across different classification methods and select your favorate classifier. Furthermore, for the groups looking at the whole dataset, you can try training on some securities for example obId A1-A3, and testing on other securities for example obId A4, and so on depending on how much computational power you have.

- Experimenting with introducing new inferred columns such as "time since last event for the endUserRef" would also be very helpful. For example some endUserRef ABCDEFG might insert an order at one time (1582082423000) and then cancel it one minute later (1582082483000). This would give the second event a "time since last event for the endUserRef" = 60000 millis.

- Another approach would be to randomly replace the endUserRefs for each epoch (e.g. shift the one-hot encoded vector or randomize the int map -- depending on how its represented). If we were to consider some ethical aspects of spoofying classification, it sounds a bit unfair to systematically skewing classification towards particular endUserRefs - i.e. if the user has spoofied before the classifier will think the user is very likely to spoof again in the future. Therefore, we encourage you to try to make this agnostic of endUserRef (i.e. not biased against any specific individual). To do so you can use data from multiple instruments, shuffle endUserRefs within each batch, or any other form of regularization.

## Submission:
Please upload your results to the **Submission folder** during DAY2 11:00 AM ~ 11:05 AM as a zip file with the following naming convension:
* **Team_teamname.zip** 

The zip file should include four files:
* **Team_teamname.ppt**
* **Team_teamname_wrapper.ipynb**
* Training prediction probabilities:
  * **y_train_prob_pred_small.csv** if you are analyzing the small dataset
  *or*
  * **y_train_prob_pred_big.csv** if you are analyzing the big dataset
  *or*
  * **y_train_prob_pred.csv** if you are analyzing the whole dataset
* Testing prediction probabilities:
  * **y_test_prob_pred_small.csv** if you are analyzing the small dataset
  *or*
  * **y_test_prob_pred_big.csv** if you are analyzing the big dataset
  *or*
  * **y_test_prob_pred.csv** if you are analyzing the whole dataset

There is an example submission in the folder called **Team_test.zip** which includes all the files expect for the slides for your reference.

In case there are unforeseen difficulties submitting the zip files, as an alternative. You can email the zip files to pdecrem@gmail.com or angelajin95@gmail.com

#### Test Submission: 
There is a chance to test submit at DAY2 9:00 AM to make sure you have the correct formats for actual submission. We will test grade your submitted zip files. All the zip files for the test submission will be collected and deleted before 9:30 AM. We will let you know if there is any issue with the submission format.

## Grading:
We will use Cohen's Kappa to evaluate the prediction results. https://en.wikipedia.org/wiki/Cohen%27s_kappa Extra points will also granted to teams which are working with more challenging datasets. 

## Bonus Points:
You will notice there is a file called y_masked_train_small.csv or y_masked_train_big.csv or y_masked_train.csv where we masked the class 3 as 0 in the training dataset. For those of you who have extra time/interest, feel free to try train with the masked y labels and figure out a way to identify class 3 (a variation of spooying) in both training and testing data set. 

You can create an extra folder named mask and zip it up with the other 4 files to be submitted. So **Team_teamname.zip** should include:
* **Team_teamname.ppt**
* **Team_teamname_wrapper.ipynb**
* Training prediction probabilities:
    * **y_train_prob_pred_small.csv** if you are analyzing the small dataset
    *or*
    * **y_train_prob_pred_big.csv** if you are analyzing the big dataset
    *or*
    * **y_train_prob_pred.csv** if you are analyzing the whole dataset
* Testing prediction probabilities:
  * **y_test_prob_pred_small.csv** if you are analyzing the small dataset
  *or*
  * **y_test_prob_pred_big.csv** if you are analyzing the big dataset
  *or*
  * **y_test_prob_pred.csv** if you are analyzing the whole dataset
* **Masked** folder. Masked folder shall contain
  * **Team_teamname_wrapper_masked.ipynb**
  * Training prediction probabilities:
    * **y_train_prob_pred_small.csv** if you are analyzing the small dataset
    *or*
    * **y_train_prob_pred_big.csv** if you are analyzing the big dataset
    *or*
    * **y_train_prob_pred.csv** if you are analyzing the whole dataset
  * Testing prediction probabilities:
    * **y_test_prob_pred_small.csv** if you are analyzing the small dataset
    *or*
    * **y_test_prob_pred_big.csv** if you are analyzing the big dataset
    *or*
    * **y_test_prob_pred.csv** if you are analyzing the whole dataset

If you don't have the probabilities, just a series of the labels \[0,1,2,3\] would be fine as well.

## Enjoy hacking!
