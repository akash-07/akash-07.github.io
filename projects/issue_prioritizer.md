---
layout: default
---

## Github Issue Prioritizer - A tool to prioritize issues on Github

**Project:** Software Engineering Lab
**Team Members:** K.S.S Bhargav, Sai Sumanth
**Mentor:** Dr.Sridhar Chimalakonda
**Date:** Feb - March 2018

Issues are a common mode of tracking bugs in software projects. Integrators face challenges with regards to prioritizing work in the face of concurrent issues. We designed and implemented Issue-Prioritizer, a tool to prioritize issues based on machine learning techniques. Issue-Prioritizer works like a priority inbox for issues, recommending top issues the user should focus on based on his/her own priorities which can be set through some parameters.

**Architecture**

![image2](https://user-images.githubusercontent.com/24961068/48665363-f3da4580-ead2-11e8-9211-cac0f6270cf7.PNG)

**How do we assign priority?**

The priority ordering is based on the following three criteria:

1. Issue Lifetime predicted via machine learning techniques.
2. Hotness of the issues.
3. Category of the issues.

**List of features used**

| Feature  | Description  | Type  |
|---|---|---|
| Author of Issue  | Is the author a project member?  | Static   |
| Comments  |  Number of discussion comments | Dynamic|
| Assignees |  No. of assignees to look over the issue|  Static | 
| Title | The text associated with title and description of the issue| Static |
| Labels| The type and number of labels assigned to the issue| Static |
| Age| Days until today since creation| Dynamic|


**Issue lifetime prediction**

We predict the lifetime of the issue in days using three features: number of assignees, number of comments and author association of the issue. Choice of these features from all available set of features is intuitive from the fact that more the number of assignees, faster will the issue be closed. Likewise, an issue with author as a project member is more likely to get closed than the issues with authors who are non members.

**Hotness of the issue**

The model used for measuring hotness of the issues resembles the one used to find out trending videos on YOUTUBE. Following table compares the parameters used in both models. We use four features for measuring hotness: comments, assignees, author-association and label. 

| Youtube trending videos| Issue-Prioritizer |
| --- |--- |
| Age of video|Age of issue |
| Growth rate of views| Growth rate of comments|
| Where are the views coming from?| Author of comment|
| View count| Comment and label count|

We define hotness as:

![formula](https://user-images.githubusercontent.com/24961068/48665382-31d76980-ead3-11e8-9512-e76006c4baaa.PNG)

For more details about the formula, find the full report [here](report_issue_prioritizer.pdf).

**Category of the issue**

We need to identify the category of the issue, as some issues are more crucial to resolve immediately than others. For example an bug fix causing crashes would need immediate attention over an issue demanding feature addition. We use Latent Dirichlet allocation to identify the category of the issue from the issue description text.

**Snapshot of Issue Prioritizer**

![image3](https://user-images.githubusercontent.com/24961068/48665367-f9379000-ead2-11e8-8f7f-a7a0b33d8489.png)

**References**

1. <https://guides.github.com/features/issues>
2. Automatically Prioritizing Pull Requests, Erik van de Veen, Georgios Gousios and Andy Zaidman in the Proceedings of 12th Working Conference on Mining
Software Repositories, 2015
3. G. Gousios, A. Zaidman, M.-A. Storey, and A. van Deursen, Work practices and challenges in pull-based development: The integrator perspective,in Proceedings of the 37th International Conference on Softw are Engineering (ICSE), 2015.
4. <https://support.google.com/youtube/answer/7239739?hl=en>
5. <https://github.com/tensorflow/tensorflow>






