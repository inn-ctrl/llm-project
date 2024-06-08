# LLM Project

## Project Task
(fill in details about your chosen project)
The objective of this project is to use a pre-trained model to analyze sentiments in the movie reviews dataset. 
Using that model we will help us understnad customer feedback and compare it to positives and negatives and it should give us overall perspective of reviewers on the movie. 

## Dataset
(fill in details about the dataset you're using)
The original dataset is 'yelp_review_full' dataset accessed via this link(https://huggingface.co/datasets/Yelp/yelp_review_full). It has two feautres and 700,000 entries. As a text classfication, unique neeeds makes us believe that we may opt for a different model than what was used on the dataset from Hugging Face. 



## Pre-trained Model
(fill in details about the pre-trained model you selected)
As said above, the approach to the dataset was different. Most notably, the sheer size imposed so much computational requirements that the only decision was to randomly sample it. The understanding is however that whatever model evaluated will only be on the sample. However, we concluded by mentioning the best performing model, but the project explores two. 

While deciding, we would be helped by understanding the data sample so that whatever model represent it well is said to perform well. The histogram in the file 4-optimization.ipynb shows us the sentiment distribution.  
1. roberta:
Overall this model is still lower but it is better compared to distilbert. therefore we combined that with the recoall score which interestingly falls at 0.73. That shows how the model is likely to indetify true positives in the dataset.
Results: This model shows us that among 300 reviews, 225 are positive and 75 are negative
Interpretation: This is not a very convincing result because it is different from what the histogram shows. However, manually looking through the dataset, positive reviews are a majority. This mixup must be properly fixed by looking at the full dataset which was not feasible as of this project due to computation requirements.
 
Therefore, an arbitrary sensible conclusion is that the movie reviews do include 225 positive reviews and 75 negative reviews. 

2. distilbert:
This model fails to representat the sampled data very well. Looking at both precision and recall (0.03 and 0.11 on weighted avg), we can see that the model did not represent negative and positive records enough. Recall falls at 1 which means that it perfectly indentified true positives in the dataset. Considering that score, lack of consideration for true negatives, and overall low model accuracy score of 0.15, we did not go with this models findings at this stage. 

Results: This model shows that all 300 move reviews are negative.
Interpretation: The model seems to be fully agreeing with the EDA, which begs the need for further exploration as it may even perform better if we consider the whole dataset. That remains something for future exploration due to the computational challenge for the full dataset. However, for now we can say that distilbert does not represent our sample very well. 

## Performance Metrics
(fill in details about your chosen metrics and results)
1. Precision/recall: Due to class imbalances in the sample dataset, precision and recall metrics are the best metrics to represent the data so that we avoid making any biased conclusions. 
2. f1-score: In case the score of precision and recall do not make convincing conclusions, f1-score was used to decide what holds more wieght between the two, or even the overall signiifcance of the score. 
3. accuracy score: the metric shows us how models accurately represent the dataset. By consulting this score, we were able to see at which level we can agree with the findings. 

## Hyperparameters
(fill in details about which hyperparemeters you found most important/relevant while optimizing your model)

* sample size n: throughout the whole process, the sample size was being adjusted so see the performance of the model overtime. This helped us see what the score looks like overtime.​
* Batch size: The number of samples processed before updating the model during training.​
* Learning rate: The rate at which the model's parameters are updated during training.​
* Number of epochs: The model iterates over the entire dataset these times during training.​

##
