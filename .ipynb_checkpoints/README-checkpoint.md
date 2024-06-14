# LLM Project

## Project Task

The objective of this project is to use a pre-trained model to analyze sentiments in the movie reviews dataset. 
Using that model we will help us understnad customer feedback and compare it to positives and negatives and it should give us overall perspective of reviewers on the movie. 

## Dataset
The original dataset is 'yelp_review_full' dataset accessed via this link(https://huggingface.co/datasets/Yelp/yelp_review_full). It has two feautres and 700,000 entries. As a text classfication, unique neeeds makes us believe that we may opt for a different model than what was used on the dataset from Hugging Face. 

## Pre-trained Model

As said above, the approach to the dataset was different. Most notably, the sheer size imposed so much computational requirements that the only decision was to randomly sample it. The understanding is however that whatever model evaluated will only be on the sample. However, we concluded by mentioning the best performing model from all the tried.

While deciding, we would be helped by understanding the data sample so that whatever model represent it well is said to perform well. The histogram in the file 1-preprocessing.ipynb shows us the sentiment distribution.  
pre-processing: during tokenization, the distilbert model was used to tokenize the selected damples. This made tokenzed splits ready for further preparation. 
1. training. The same distilbert model was used in training. The tokenizer was discarded at this step and the sequence classification was used to train our dataset using distilbert.
   
Results: This model shows us that among 300 reviews, 189 are positive and 111 are negative
Interpretation: This is a very convincing result because it is  what we see the histogram. Manually looking through the dataset, positive reviews are a majority. T

The model scores 0.63 on accuracy. It is not a perfect score but by chaning the hyper-parameters, the score changed. We can conclude that it is a good model since it correctly represent the dataset and its accuracy is not that bad. 


## Performance Metrics

1. eval_loss: measuers how well the model respons to unseen data. The actual scores decreases when we expose the model to new data. Even though the decrease is not that much, this is a good sign.

2. f1-score: In case the score of precision and recall do not make convincing conclusions, f1-score was used to decide what holds more wieght between the two, or even the overall signiifcance of the score. In other words, eval_f1 shows a balance between the two. Being that the score of 1 indicate a perfect precision and recall, the score of 0.77 is good if we compare it to other metrics.
    
3. accuracy score: the metric shows us how models accurately represent the dataset. By consulting this score, we were able to see at which level we can agree with the findings. The accuracy score of 0.63 was actually not that perfect, but it is acceptable. 

In general, we can see that the above scores show us a generally well performing model on our dataset. It is important in this case to combine all the scores and make a conclusion based on that because of two reasons: 1) we are dealing with a sampled data 2) there is an imbalance in the sampled data. 

Because of these two reasons, combining different scores gives us diversity in perspectives. Also, it leaves much room for improvement if we decide to increase our sample in the future. It is a way to keep all the options open. 

## Hyperparameters

* sample size n: throughout the whole process, the sample size was being adjusted so see the performance of the model overtime. This helped us see what the score looks like overtime.
  
1. Learning rate: The rate at which the model's parameters are updated during training.​
2. Number of epochs: The model iterates over the entire dataset these times during training.​
3. Batch size: The number of samples processed before updating the model during training.​
4. Weight decay: tuning this parameter helps prevent overfittting on unseen data by penalizing large weights during training. 


##
