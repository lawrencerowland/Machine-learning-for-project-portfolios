# Machine learning for project portfolios

Earlier explorations of how project information might support portfolio decisions. The Orange demonstration dates from 2019; the collection also holds later notes and unfinished experiments.

## Start with the illustrated Orange walkthrough

**Could completed-project records help a portfolio manager decide where to look next?** Follow the data preparation, model comparison, mistakes and proposed management use in the [World Bank project-rating walkthrough](project-success-prediction/READme.md).

[![Original Orange workflow: data preparation branches into model comparison and visual exploration.](images/project-success-prediction/image2.png)](project-success-prediction/READme.md)

The target is IEG **Bank Performance**, rather than general project success. The retained screenshots, film, script and workflow are useful teaching material. The original workbook is absent, and the historical 89.7% score has not been reproduced or validated as an early forecast.

[Read the walkthrough](project-success-prediction/READme.md) · [Film, script and workflow](project-success-prediction/READme.md#resources) · [Methods guide](https://lawrencerowland.github.io/ML-for-portfolios.html#orange-project-ratings) · [Library](https://lawrencerowland.github.io/library.html#library-methods)

*Navigation and explanations reviewed 1 October 2026. Original models and media retained unchanged.*

# Purpose

- Apply machine learning to understand how to improve the project portfolio

- Taking portfolio data and applying ML for insight.

![Original map of machine-learning approaches for project and portfolio questions.](images/image2.png)

# Introduction

There is a full description [here](https://lawrencerowland.github.io/ML-for-portfolios.html), suggesting different ways of approaching the topic. 

The example explains a prototype workflow to study before adapting it to another portfolio. Reuse would require an explicit target, features available at the intended forecast date, and fresh validation; changing the data columns alone would not establish a useful forecast.

The proposed business rationale is retained below, with its assumptions separated from demonstrated results.

# Or straight to code and examples
But if you want to go straight to details , then here are the folder choices:

1. [Project success Prediction](https://github.com/lawrencerowland/Machine-learning-for-project-portfolios/tree/master/project-success-prediction)

1. [Natural language processing for assessing your project domain using Orange](https://github.com/lawrencerowland/Data-Model-for-Project-Frameworks/tree/master/Project-frameworks-by-using-NLP-in-Orange-Datamining)

1. [Natural language processing for assessing your project domain using Gensim and other Python libraries](https://github.com/lawrencerowland/Data-Model-for-Project-Frameworks/tree/master/Project-frameworks-by-using-NLP-with-Python-libraries)

# Use cases currently written up

These were the topics written up for this earlier collection. The [methods guide](https://lawrencerowland.github.io/ML-for-portfolios.html) supplies the broader context.

1. **Project success Prediction** This is possible if:
- you are able to label historical projects or work-packages as success / failure, or similar categories
- you have data for a significant number of these previous projects comprised of a number of project features or attributes per project
This could support a training set. Evaluation would need to test whether features known at the decision date predict an appropriately defined later result. Sensitivity and precision on held-out historical rows alone do not establish that. Possible applications include flagging current reports for review or assessing proposals; neither is demonstrated as a deployed capability here.

1. **Natural language processing for assessing your project domain using Orange** Rather than a bulky framework of project-management tasks, it is worthwhile having a framework that meets the particular requirements of your clients, sector or company. There will be more emphasis on some tasks, and some will not be needed. 
Your business and portfolio will have  hundreds or thousands of documents relevant to project best-practice in your sector. Natural language processing is a way of mining the text to understand what the topics are within a business area. Orange is a no-code environment for doing this. 
Where the team is experienced in the business sector, or where there is time to interview appropriate experts, then this approach can be complemented by structuring the key project tasks - by working with these experts to explain the steps and principles they apply.

1. **Natural language processing for assessing your project domain using Gensim and other Python libraries**
This does the same as the above use case, but requires a little coding experience. The linked repository retains earlier explanations and notebook material; parts of the former toolkit are now a navigational skeleton. Treat it as source material to inspect, not a promise of a complete runnable service.


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

*Historical proposal accompanying the 2019 Orange demonstration. The archive was described as roughly 12,000 project records; the displayed comparison evaluated 667 records. The complete explanation, original pictures and unfinished development list are in the [walkthrough](project-success-prediction/READme.md).*

## What task/decision are you examining?

A portfolio manager wants to decide which projects deserve review, support, re-scoping or closer monitoring. The World Bank archive supplied a concrete setting in which to explore that question. This was independent work on public data, not a World Bank engagement.

## Prediction:

The saved example classifies IEG Bank Performance ratings. It does not establish early prediction of project failure or benefits. In particular, its input records include other evaluation ratings and eventual financial/date information that may be unavailable at a forecast date.

## Judgement:

Define the positive class and the decision before assigning error costs. If positive means “needs review”, a false positive prompts an unnecessary review and a false negative misses a project needing attention. The earlier assertion that false negatives are inherently less serious was unsupported. A decision to cancel a project requires more than a predicted rating.

## Action:

The proposal was to review flagged projects and consider strengthening their resources, with re-scoping, monitoring or cancellation among the wider management choices. These are proposed responses, not actions shown to improve outcomes by this study.

## Outcomes:

The saved Random Forest comparison shows 89.7% classification accuracy (598 of 667), previously described as either 89% or 90%. That historical result is not a production target. The proposed “over 50%” threshold for identifying failure also lacked a stated baseline or cost model. Useful reviews, missed problems, workload and realised benefits would matter alongside statistical accuracy.

## Training:

The original account used roughly 20 attributes and compared several supervised learners, selecting Random Forest for the displayed result. The target is a multi-category Bank Performance rating, distinct from IEG's Outcome rating. The workbook is missing, and the result has not been reproduced. Other evaluation ratings can help reconstruct the target without establishing forecasting skill.

## Input:

The proposed monthly feed would need project information genuinely available at that point. Later evaluations and eventual delay cannot substitute for information known during delivery. New portfolios would require a fresh assessment of features, labels and timing.

## Feedback:

A six-month retraining cycle was suggested. It remains a proposal, whose cadence and validation requirements would depend on the application.

## How will this AI impact on the overall workflow?

The hoped-for effects were more focused reviews, better scoping and selection, and better allocation of project support. “One day a month” was an operating-cost estimate, not a measurement. Improved prediction would not by itself prove improved delivery; those effects would need their own evaluation.

## To run this example or modify for your portfolio...

[Read the illustrated explanation and reconstruction requirements](project-success-prediction/READme.md#resources). The saved workflow needs an external workbook and configuration checks. The demonstration does not include a fitted model or a working deployment.

# Alternative: Use AutoML on Microsoft Azure

This earlier alternative considered automated model selection within a Microsoft environment. The screenshots below retain that exploration; they are not a current Azure setup guide or a validated comparison with the Orange model.

This allows data and results to remain within one environment. Automated search compares candidate models under configured data and evaluation choices; it does not establish that the target, features or decision are appropriate.

This can also be useful as a 'ranging shot', seeing if your data can support a useful prediction. Then, it can be useful to work on your own model, whether in Orange Data Mining, or in Python with SciKitLearn or Keras. I find follow up step helps in understanding what the model is doing, and gives more appreciation for understanding how to improve the data-set. 
The service and library details are historical and would need checking before reuse.

There are also useful low-code approaches with Azure. The examples below regarding preliminary data exploration on the interesting [World Management Survey](https://worldmanagementsurvey.org) dataset, which looks at what management features are associated with success. Please raise an issue if you would like me to prioritise writing up this example. 

![Historical Azure exploration of the World Management Survey dataset.](images/Output-of-World-Mgt-survey-on-Azure-LR.png)

![Overview of the earlier Azure World Management Survey workflow.](images/Output-World-Mgt-survey-on-Azure-LR-overview.png)

# Notes

In these earlier examples the approaches are conventional ML applied to project data from spreadsheets and relational databases. For related graph representations, see the [worked data models](https://lawrencerowland.github.io/Portfolio-data-model.html#read-the-worked-models). Those examples are not themselves evidence of predictive performance.

# Overview of other examples
This original status map records other ideas and examples from the period. It is retained as historical context, not a current delivery plan.
 ![Original status map of machine-learning project examples.](images/ML-Project-models-status-LR.png)

# Acknowledgements

- Modelling Using Orange Data mining. 

- Data from World Bank.

- Questions from using AI canvas Template © Agrawal, Gans, Goldfarb 2019. 

