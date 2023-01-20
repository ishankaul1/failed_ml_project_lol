# cs5262
The goal of this analysis will be to create profiles that target certain aspects of a lifestyle that are shown to predict mental well-being overall. These profiles can drive the product portfolio of the advertisting company.
For the purpose of this assignment, we will assume that our advertising service charges $1.50 per person advertised to, and that our revenue model generates an average of $20 per customer that signs up. These numbers are rough estimates based on Facebook's $0.94 and Google's ~$3 'Cost-per-click' models.
https://www.shopify.com/blog/facebook-ads-cost
https://www.wordstream.com/blog/ws/2015/05/21/how-much-does-adwords-cost

Based on these numbers, the net revenue of a True Positive in the Confusion Matrix would be $20 - $1.50 = $18.50. The cost of a False Positive would be $1.50, since we'd be advertising to someone and not getting any revenue. True Negatives and False Negatives will not affect our revenue stream directly, since a Negative prediction results in inaction on our side. Therefore, the main business goal to be reached by the model is to maximize the ratio of True Positive to False Positive predictions on the Mental Health score. Our model will be net 'valuable' if this formula holds:
18.5 * (# of true positives) > 1.5 * (# of true negatives)
