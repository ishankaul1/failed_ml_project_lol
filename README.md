# cs5262
The goal of this analysis will be to create profiles of certain aspects of an individual's lifestyle to predict overall mental well-being. These profiles could drive the product portfolio of an advertising company, allowing them to market mental health and lifestyle improvement products to potential customers that may need them.
For the purpose of this assignment, we will assume that our advertising service charges customers $1.50 per click. These numbers are rough estimates based on Facebook's $0.94 and Google's ~$3 'Cost-per-click' models.
https://www.shopify.com/blog/facebook-ads-cost
https://www.wordstream.com/blog/ws/2015/05/21/how-much-does-adwords-cost.
Taking up ad-space on the internet will cost us money as well. According to this article from TopDraw https://www.topdraw.com/insights/is-online-advertising-expensive/, online advertising can cost anywhere from $3-$10 per 1000 people reached. To make calculations easier, we will assume $5/1000 people, or $.005 per person.
The net value of our proposed model can be determined by analyzing the effect of the 4 different metrics in a binary classification Confusion Matrix.
    1. True positive: A true positive in this scenario would mean we advertised to a customer, and they decided to click on the advertisement. The net revenue of a true positive would be equal to `(revenue of 1 click) - (cost of advertising to 1 person)` = `$1.50 - $.005` = `$1.495`.
    2. True negative: A true negative would mean we decided to not advertise, and the user wouldn't have been interested anyways. This is obviously good for us, as we avoided wasting money on advertising. However, it doesn't actually generate any net positive or negative revenue.
    3. False positive: A false positive would mean we advertised to a customer, and they did not engage. This results in a net loss of the advertising cost, `-$0.005`.
    4. False negative: A false negative would mean we didn't advertise to a customer, but they would have engaged if we did. We definitely want to avoid this to maximize revenue, but since it results in no spending on our end, it won't actually affect the net revenue of our model.

The final evaluation of this model will be determined by its net impact on the business's revenue per sample of population ran on. This can be evaluated by the formula `(((net revenue of 1 TP) * (# of TPs)) + ((net revenue of 1 FP) * (# of false positives))) / (total # data points)` =  `(($1.495 * # of TP) - ($.005 * # of FP))/(total # data points)`. Models will be evaluated by this formula on a holdout set of data to determine their value to the business.

Note that False and True Negatives will *indirectly* affect the model value using this method, since we divide by the total # of data points fed to the model. A False Negative will mean missed revenue per population, which will actually drive down the score for the final model evaluation.
