# Machine-learning-for-project-portfolios

# Purpose

- Apply machine learning to understand how to improve the project portfolio

- Taking portfolio data and applying ML for insight.

![](/images/image2.png)

# Introduction

There is a full description [here](https://lawrencerowland.github.io/ML-for-portfolios.html), suggesting different ways of approaching the topic. 

If you have reasonable data on your projects or work-packages, then the example below gives a prototype for making a forecast with your own data, after making adjustments to reflect the particular project attributes you have recorded. 

Further below is a summary of the business rationale for the example

# Or straight to code and examples
But if you want to go straight to details , then here are the folder choices:

1. [Project success Prediction](https://github.com/lawrencerowland/Machine-learning-for-project-portfolios/tree/master/project-success-prediction)

1. [Natural language processing for assessing your project domain using Orange](https://github.com/lawrencerowland/Data-Model-for-Project-Frameworks/tree/master/Project-frameworks-by-using-NLP-in-Orange-Datamining)

1. [Natural language processing for assessing your project domain using Gensim and other Python libraries](https://github.com/lawrencerowland/Data-Model-for-Project-Frameworks/tree/master/Project-frameworks-by-using-NLP-with-Python-libraries)

# Use cases currently written up

These are the ones I have currently written up. If you wish to see any of the use cases mentioned [previously](https://lawrencerowland.github.io/ML-for-portfolios.html) then please ask me, and I will prioritise writing these up. 

1. **Project success Prediction** This is possible if:
- you are able to label historical projects or work-packages as success / failure, or similar categories
- you have data for a significant number of these previous projects comprised of a number of project features or attributes per project
This can comprise a training set to train a model to look for early signs that projects may not succeed. During the training process, you will be able to examine model sensitivity and precision - to see whether the model will be able to make predictions for new data. If so, you will be able to:
- detect project anomalies in current project reports, or
- identify which project proposals are likely to succeed before starting them. 

1. **Natural language processing for assessing your project domain using Orange** Rather than a bulky framework of project-management tasks, it is worthwhile having a framework that meets the particular requirements of your clients, sector or company. There will be more emphasis on some tasks, and some will not be needed. 
Your business and portfolio will have  hundreds or thousands of documents relevant to project best-practice in your sector. Natural language processing is a way of mining the text to understand what the topics are within a business area. Orange is a no-code environment for doing this. 
Where the team is experienced in the business sector, or where there is time to interview appropriate experts, then this approach can be complemented by structuring the key project tasks - by working with these experts to explain the steps and principles they apply.

1. **Natural language processing for assessing your project domain using Gensim and other Python libraries**
This does the same as the above use case, but requires a little coding experience. The code is provided, so it is only necessary to run it on the document library that the team provides for their business sector. The code is provided in Jupiter notebooks, which lay out the steps at each stage. 


# Further use cases

|                    |                                                                                         |                             |                                    |                                                                                                                         |
| ------------------ | --------------------------------------------------------------------------------------- | --------------------------- | ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| **Order of value** | **Question**                                                                            | **Question type**           | **Dominant machine learning type** | **Training data**                                                                                                       |
| 1                  | Which projects will succeed ?                                                           | Classification              | Supervised learning                | Project lists, identifying which have succeeded, with additional columns of features that may be relevant               |
| 2                  | Which engagements will succeed ?                                                        | Classification              | Supervised learning                | Engagement lists, as above                                                                                              |
| 3                  | Which prospects are most likely to succeed ?                                            | Classification              | Supervised learning                | Historical data on which prospects converted and which didn’t, with additional columns of features that may be relevant |
| 4                  | Which services get the greatest uptake ?                                                | Classification              | Supervised learning                | Historical data on which prospects converted and which didn’t, clearly identifying type of service                      |
| 5                  | Which companies are most likely to become new clients ?                                 | Classification              | Supervised learning                | External market data on all our clients, clearly identified by sub sector                                               |
| 6                  | Which customers are we most likely to lose (churn)                                      | Classification              | Supervised learning                | External market data on all our clients, showing sector information, and showing length and size of each engagement     |
| 7                  | What delay / costs might this project incurr ?                                          | Numerical prediction        | Supervised learning                | Overspend or delay per project, relative to first estimate, and including other project features                        |
| 8                  | Find similar documents to use for writing proposals                                     | Natural language processing | Unsupervised learning              | Libraries of previous proposals, ideally already in pdf or Word rather than PPt                                         |
| 9                  | Look for common topics across (un) successful project / engagement folders / interviews | Natural language processing | Unsupervised learning              | Libraries of (un) successful proposals or engagements                                                                   |
| 10                 | Topic summarisation for an engagement                                                   | Natural language processing | Unsupervised learning              | Library of 1 Client or assignment data covering broad range of client contexts and challenges and approaches            |

# Example: Project Success Prediction on 12,000 projects

## What task/decision are you examining?

We are examining the way that a portfolio of projects is overseen by a large Institution. We have started with the World Bank as they have data on 12000 projects and which were ultimately successful. The decision we are seeking to improve is in identifying which projects are unlikely to succeed, and whether they should be cancelled, re-scoped, supported, or monitored as a result. This task can be selectively generalised to Client portfolios depending on the completeness of data and the type of features captured. 

## Prediction:

Predict during project implementation which World Bank projects will be evaluated as Satisfactory after the project completes. 

## Judgement:

The payoffs of being right for the Institution are being able to focus on shutting or intervening in projects that are likely to fail. The impact of false positives is cancelling projects that might otherwise be successful. The impact of false negatives is less serious as it would just lessen the improvement in project coverage

## Action:

The actions that can be chosen as a result of the judgement would be to:
1. Review a project forecast to fail
2. Strengthen resource on these projects

## Outcomes:

We would judge whether we are achieving our outcomes by monitoring whether Projects forecast to succeed actually do succeed. For the WB and this dataset, since accuracy achieved is 90%, this should be the target during production. 
What % projects forecast to fail do fail – anything over 50% would be good

## Training:

To do this we used a sample of the 12000 previous projects. Each project has been rated as Satisfactory, or Unsatisfactory, Highly Satisfactory etc. after the project concluded by the client. This rating label  has been used as the target for Learning. Each project has about 20 features recorded for it, and our model is trained to understand which combinations of these features are most predictive of success. This is a supervised learning approach, where we have ended up training and selecting a Random Forest Model as providing the best results. 

## Input:

Now that we have trained the model, we would need data on currently running projects as per the feature list used in training. These include forecast to completion, mid-project quality reviews and industry area. This could be fed into the model once a month by the portfolio manager. 

## Feedback:

During production, we will need to use measured outcomes along with input data to generate improvements to our predictive algorithm. This can be done semi-annually, re-running and refitting the whole model. A new model would then need to be issued to the portfolio manager.  

## How will this AI impact on the overall workflow?

Regularly predicting project success will focus management attention on the right projects. It will improve forecasting accuracy, and thereby should increase overall project completion. It may also have a lesser effect on early project scoping and project selection. The impact on the portfolio manager would be a day a month. Since there are likely to be project reviews and interventions for failing projects already, it is likely that the time taken on these from model predictions would be substitution of existing tasks rather than new tasks. As this is implemented, there would be a backlog effect and a higher turnover and reallocation of project teams. 

## To run this example or modify for your portfolio...

[Project success Prediction](https://github.com/lawrencerowland/Machine-learning-for-project-portfolios/tree/master/project-success-prediction)

# Alternative: Use AutoML on Microsoft Azure

If your team already works in a Microsoft environment, with Office, Azure and Power BI, then it is worth taking advantage of the AutoML capabilities. 

This allows data and results to remain within one environment. AutoML will find the best fit it can, selecting the most appropriate model. 

This can also be useful as a 'ranging shot', seeing if your data can support a useful prediction. Then, it can be useful to work on your own model, whether in Orange Data Mining, or in Python with SciKitLearn or Keras. I find follow up step helps in understanding what the model is doing, and gives more appreciation for understanding how to improve the data-set. 
AutoML is very useful, but it still using SciKitLearn under the hood. 

There are also useful low-code approaches with Azure. The examples below regarding preliminary data exploration on the interesting [World Management Survey](https://worldmanagementsurvey.org) dataset, which looks at what management features are associated with success. Please raise an issue if you would like me to prioritise writing up this example. 

![](/images/Output-of-World-Mgt-survey-on-Azure-LR.png)

![](/images/Output-World-Mgt-survey-on-Azure-LR-overview.png)

# Notes

Currently the approaches are conventional ML applied to project data from spreadsheets and relational databases. For ML applied to project data taken from graph databases,see (xx)[xx]

# Overview of other examples
Please raise an issue if you want any more of these uploaded - I haven't got around to it yet. 
 ![](images/ML-Project-models-status-LR.png)

# Acknowledgements

- Modelling Using Orange Data mining. 

- Data from World Bank.

- Questions from using AI canvas Template © Agrawal, Gans, Goldfarb 2019. 

