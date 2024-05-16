# FB-Post-Classification-with-NLP-BERT

## Overview
This project develops a text classifier to categorize Facebook business page posts into three content categories: Appreciation, Complaint, and Feedback. The classifier aims to help businesses understand customer interactions on their Facebook pages by classifying posts into meaningful categories based on their textual content.

## Background
Facebook, being one of the largest social media platforms, serves as a crucial channel for businesses to engage with their customers. Businesses maintain Facebook pages where customers often leave posts that may include complaints, questions, or appreciations. These posts are rich sources of real-time customer sentiment and preferences.

## Dataset
The dataset used in this project, named FB_posts_labeled.txt, includes 7961 labeled posts. Each post has the following attributes:

- postId: Unique identifier for each post.
- message: Text content of the post.
- Appreciation: Binary indicator (0/1) if the post is an appreciation.
- Complaint: Binary indicator (0/1) if the post is a complaint.
- Feedback: Binary indicator (0/1) if the post includes feedback such as questions or suggestions.

These categories are mutually exclusive and were labeled by humans. For model evaluation, we use an unlabeled dataset, FB_posts_unlabeled.txt, which includes 2039 posts to predict categories. The labels for this dataset are held privately for objective evaluation of the model.

## Methodology
1. Preprocessing: 
Text data is preprocessed using TensorFlow operations, converting them into numeric token IDs, masks, and segment IDs suitable for input into BERT.
2. Model Architecture: We employ a BERT model from TensorFlow Hub to encode the text inputs. A classification layer is added on top of BERT’s output to determine the post category.
3. Model Training: The model is compiled with AdamW optimizer, loss function, and accuracy metrics. Training involves fine-tuning the BERT model on the labeled dataset.
4. Evaluation: The model's performance is evaluated using the average F-measure across the three categories on a holdout set.
Predictions are made on the unlabeled dataset for external evaluation.

## Result
The BERT Model ended up scoring F1 0.8347 on the training data set, and F1 0.8398809 the testing data set.
