# Final Project

You will form teams of 4 to complete a final project that integrates all we've learned during this quarter. You will analyze a large text corpus to answer a question. The analysis will involve steps from each of the four modules in this course: (1) Text as data, (2) Text classification, (3) Information extraction, and (4) Text data visualization.

This project will be graded on both group and individual components to facilitate fair assessment.

**Due date:** Tuesday, December 12, 2023 EOD

**Total points:** Graded out of 125 points

## Milestones

To increase the feasibility and quality of your project, please observe the following milestones:

| Milestones     | Date          | Description |
| -----------   | -----------   | ----------- |
|               | Thu, Nov 16   | Final project is assigned     |
| 1             | Mon, Nov 20   | Form teams (add your team info to [this spreadsheet](https://docs.google.com/spreadsheets/d/1JZNsYyaaDDfRPWsxegt5Mdn98ZejhXI9y9dxWRAbbRQ/edit?usp=sharing) [Columns A-F])                   |
| 2             | Wed, Nov 22   | Identify topic, identify corpus and datasets (update Columns G-H of the [spreadsheet]((https://docs.google.com/spreadsheets/d/1JZNsYyaaDDfRPWsxegt5Mdn98ZejhXI9y9dxWRAbbRQ/edit?usp=sharing)))  |
| 3             | Wed, Nov 29   | Complete initial dataset description, begin training models |
| 4             | Wed, Dec 6    | Complete model training, analyze results, begin drafting report |
| 5             | Tue, Dec 12   | Report and video presentation **due**; Submit on Canvas and email to Jerry and Lucy |

## 1. Choosing a corpus

I recommend choosing from a corpus on this page: https://github.com/niderhoff/nlp-datasets 

You do not have to analyze an English corpus, though if you choose to analyze a corpus in a different language, you will need to translate any non-English content in your report into English to faciliate grading. **I encourage and support the use of non-English and/or non-recommended corpora.**

You also do not have to analyze the entirety of some of these corpora (they vary a lot in size). If the corpus is large (>1GB), you can sample a part of it for analysis. Though please make sure you extract an unbiased sample (randomize the order of documents before sampling).

You may also analyze 2+ corpora if your question involves comparing the representation of topics or entities across 2+ domains (e.g., comparing science and news, comparing social media and news).

## 2. Selecting a question to answer

Be motivated by your curiosity! Spend an hour with your teammates brainstorming interesting questions to answer with your corpus. Here are some example questions that represent the kind of scope that I'm expecting.

- What are the brands most associated with different sports teams on social media?
- Who were the major figures represented in different news arenas in the 2010s?
- What were the primary diseases studied by researchers in the 2010s? Does this agree with the rate of those same diseases mentioned in the news in the same time period?

**Share your choice of corpus and question with Lucy and Jerry by Nov 27 for feedback.**

## 3. Breaking down your question into modeling tasks

You will choose a modeling task(s) to do, e.g., from text classification, named entity recognition, relation extraction, word embedding analysis etc. The task(s) you choose should be directly informed by the question you are trying to answer. 

For example, if you are analyzing tweets and trying to figure out which brands were mentioned most in association with different sports teams, you may need to train and run an NER model(s) to extract brand names and sports teams, then tabulate their results to discover associations. 

As another example, if you are analyzing news articles from the 2010s to figure out who were the major figures associated with different domains, you may need to train and run a text classification model to classify articles into topics (business, sports, politics, science, etc) and an NER model to extract names of people in these articles before analyzing the associations between the two (topic and people).

## 4. Identifying datasets for modeling

Identify relevant training data for your modeling task(s). You can search for datasets on Huggingface, Kaggle, Zenodo, or the web. For example, if you are training a topic classification model, what topic classification labeled dataset will you use to train the model? 

You may opt to use some of the datasets you have used in the class projects, though if you are analyzing a corpus in a different domain, comparable datasets may exist in that domain and you should search for them. If no labeled dataset exists for your domain, you can use something more generic, such as a dataset of labeled web text.

If the dataset does not have a test split, you should make one(!), and reserve it to evaluate your trained model.

## 5. Making modeling decisions

For each modeling task, choose from among the modeling options we discussed in class. Note that earlier methods we discussed may not perform as well but can still be good choices. For any model you choose, you must evaluate its performance in your use case. When analyzing results, make sure you describe the model limitations and how they affect your confidence in your results.

You will train your model on the datasets your identified, or identify suitable off-the-shelf models for your use case. You will then run your trained or off-the-shelf model on your corpus and analyze the results.

Below is a list of modeling options we discussed in class. They are provided here as a reference to help you make choices for your final project.

**Word Representations:**
- PPMI
- word2vec
- BERT embeddings

**Document Representations:**
- Averaging word representations
- Using BERT [CLS] token representations
- Sentence-BERT representations

**Text Classification:**
- Naive Bayes
    - Using word counts
    - Using sparse word representations like tf-idf or PPMI 
- (Multinomial) logistic regression
    - Using hand-engineered features
    - Using sparse word representations like tf-idf or PPMI
    - Using dense word representations like word2vec
    - Using contextual representations like BERT embeddings
- Finetuned BERT model
- Prompting

**Named Entity Recognition:**
- Conditional random field (CRF)
    - Using hand-engineered features
    - Using sparse or dense word representations
    - Using contextual representations
- Off-the-shelf libraries
    - NLTK
    - spaCy / scispaCy
- Finetuned BERT model
- Prompting

**Relation Extraction:**
- Finetuned BERT model
- Prompting

## 6. Analyzing your results

**Evaluate**: make sure you evaluate your model performance on a relevant dataset. If you trained a model, you should present its performance on the test split of the dataset (make sure you don't train on the test split!). Present appropriate evaluation metrics as we discussed in class. If there are multiple classes in your output (e.g., multi-class classification, NER), report performance by class in addition to summative metrics.

**Descriptive statistics**: present descriptive statistics on the outputs of your model(s) on the corpus you are analyzing. This might include the counts of documents associated with each class (classification), or the number of named entities extracted from each document of each type (NER).

**Answer your question**: present results to answer your question. You should build on statistical and data visualization knowledge gained from this class and previous classes to do this.


# What to turn in

As a team, you will turn in two things: 
1. A final report (100 pt, 80% of your grade) in **PDF** format
    - 40 pts assessed based on individual component
    - 60 pts assessed based on group component
2. A 5-10 minute recorded presentation (25 pt, 20% of your grade)

Please include the UW Netids of everyone on your team in the files you turn in. For example: `<uwnetid1>_<uwnetid2>_<uwnetid3>_finalproj.pdf`. Turn the files in via Canvas **and** email a copy to Jerry and Lucy in case we have trouble accessing via Canvas. 

## Final report

Your final report should consist of the following sections. There is no length restriction for the report, but I would expect some thing around 4-5 pages. I've provided some minimum recommendations for each section as guidance.

### Title + team members
Give your project a spiffy title! And list all team members at the top.

### I. Introduction and motivation (1-2 paragraphs)
Provide some background on the topic of your project and why it's relevant/for whom is it relevant to study. 

### II. Corpus (1 paragraph, 1-2 tables/plots)
Describe the corpus you are working with (Where are the contents from?) and provide some basic statistics (Number of documents, split by source(?), split by topic(?), average length, etc). This is open-ended. You should inspect the documents in your corpus and report sufficient information for a reader to gain a basic understanding of the corpus's content. Refer to earlier projects if you're not sure what to do.

### III. Modeling

You will choose a modeling task(s) to do, e.g., from text classification, named entity recognition, relation extraction etc. The task(s) you choose should be directly informed by the question you are trying to answer. 

For example, if you are analyzing tweets and trying to figure out which brands were mentioned most in association with different sports teams, you may need to train and run an NER model(s) to extract brand names and sports teams, then tabulate their results to discover associations. 

As another example, if you are analyzing news articles from the 2010s to figure out who were the major figures associated with different domains, you may need to train and run a text classification model to classify articles into topics (business, sports, politics, science, etc) and an NER model to extract names of people in these articles before analyzing the associations between the two (topic and people).

- ### A. Training data (1 paragraph per dataset)
    For each dataset you identify and use, describe its origin, where the text came from, where the labels came from, and the original intended use of the dataset. If the labels were manually annotated, briefly describe the annotation procedure.

    If you use an off-the-shelf trained model (such as spaCy, scispaCy, or a finetuned BERT model), use this section to describe what data the model was trained on.

- ### B. Model architecture (2 paragraphs per model)
    
    If you are doing only a single modeling task, you must compare two model architectures for that task (e.g., trained logistic regression vs. pretrained BERT for classification, off-the-shelf spaCy vs. trained CRF for NER etc). If you are doing two modeling tasks (e.g., classification and NER), you do not need to compare two model architectures. **If you are unsure what constitutes two modeling tasks, ask Lucy.**

    For each modeling task, describe the task, what the form of the inputs and outputs are, and what are all of the labels the model can output. Describe the model architecture. If you are using an off-the-shelf trained model (such as spaCy, scispaCy, or a finetuned BERT model), describe how the model was trained and provide justification for why you believe the off-the-shelf model is appropriate for your use case.

    For each model that you trained, report appropriate metrics for model performance on the test split of the dataset you used to train it.

- ### C. Training considerations (optional) (1 paragraph per model)

    If you trained any models, provide a brief discussion of any decisions you made during training (e.g., preprocessing, feature engineering, prompt engineering etc).

### IV. Describing/visualizing results (2 paragraphs per model, 2-3 tables/plots per model)

Run each trained model on your corpus to obtain outputs. Compute summary statistics (e.g., number of documents classified into each label, number of named entities identified per document and their types). 

Use these results to answer your initial question. Use tables and visualizations to communicate your primary findings. For example, for the sports team-brand association question, a table with the most commonly mentioned sports teams and their top 3 brand associations and cooccurrence counts might be appropriate. For the news topic and person association, a word cloud of extracted people colored by topic with size determined by number of cooccurrences might be appropriate.

For each table or visualization, describe how it was produced and any main takeaways.

### V. Discussion (2-3 paragraphs)

Describe your main findings and any interesting observations you made from your analysis. Discuss whether these findings are intuitive based on your initial understanding of the problem; if the results didn't match your expectations, discuss what next steps you could take to obtain more evidence or be more certain of your results. Discuss any additional questions your results raise and how you might go about answering them.

If your modeling experiments from the previous sections didn't work, you can use this section to discuss the challenges you ran into and how you tried to resolve them. 

## Recorded presentation

You will record a 5-10 min presentation as a group highlighting the main components of your project. This presentation should draw directly from the content of the report. In your presentation, discuss the problem you studied, the corpus you analyzed, the modeling methods you used, your primary results, any challenges you encountered, and main findings and discussion points. I recommend recording this using Zoom to reduce the need for video editing.

# Individual vs. Group component

For the project, you will implement two models and analyze their results. To facilitate the splitting of work, each team member should take on one of the following tasks:

- Implementing model architecture A 
- Implementing model architecture B 
- Describing/visualizing results of model A
- Describing/visualizing results of model B

While each member is responsible for one of these sections, you should coordinate with the rest of the team and help each other accomplish these goals. Yes, describing/visualizing results depend on successful model execution! Please work closely with your modeling/visualization partner to facilitate seamless transition between these sections. Also, if a modeling section doesn't work out, please still attempt to conduct the description/visualization section by generating and analyzing some dummy data. The justification for how you decided to analyze the results is more important than what the results actually are.

For each of these sections, **make sure you clearly communicate the team member responsible for that section in the report.** Each team member will receive an individual grade for their section (out of 40 pts), while the entire report will receive a group grade (out of 60 pts).