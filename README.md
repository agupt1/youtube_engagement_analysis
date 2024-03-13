# Youtube Engagement Analysis using Emprical Bayes
The scope of this analysis to adjust the raw enagement metrics using Emprical Bayes.

## Business Problem
The raw engagmenet metrics suffer from volume bias where content with same engagement rates get reated the same irrespective of volume of interactions. For example: a youtube video with 10 clicks out of 100 impressions will have the same CTR of 10% as another video with 1000 clicks and 10000 impressions. Clearly, we feel more confident about the second video being better in terms of CTR. However, the raw CTR does not allow us to separate these two videos out. Hence, we need to adjust the raw engagement rates by accounting for the volume of interactions.

## Solution
The engagement rates can be adjusted using Empirical Bayes with the goal of improving our estimate of a content's or a user's true engagement potential. The process includes fitting a beta distribution on the entire data to get the expected engagement rate. The observed enagemnet rate can be compared against the expected engagement to gauge how a given data point performs compared to expected engagement in general. This can be done as follows:

ctr_adjusted = (clicks + alpha) / (impressions + alpha + beta)

In the denominator we have imppressions + alpha + beta. For the given data point, if we have large enough impressions, alpha and beta will less of an impact. On the other hand, if impressions are small, alpha and beta will carry more weight and the adjusted ctr will be lot further away from observed ctr.

## Analysis
The attached python notebook goes through the same analysis for youtube videos but using likes and comments instead of clicks; and views instead of impressions. So, the two engagement rates we have for a given video are:

* likes_ratio = # of likes / # of views
* comments_ratio = # of comments / # of views

We will adjust the above two engagement rates using the Empirical Bayes approach and compare how the output changes using this approach.

