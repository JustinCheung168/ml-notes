$$BLEU = \min(1, \frac{output\_length}{reference\_length}) * (\prod_{i=1}^4precision_i)^{\frac{1}{4}}$$

The left side is a "brevity penalty" penalizing translations shorter than the original.

$precision_i = \frac{correct}{output\_length}$ , i.e. the number of $i$-grams which appear in both output and reference, divided by the total number of $i$-grams in the output. Here, we take the geometric mean of the n-grams length 1 to 4.

Recall is unnecessary but would just change the denominator to be number of $i$-grams in the reference, rather than in the output.

## Example

REFERENCE:
Israeli officials are responsible for airport security
SYSTEM OUTPUT:
airport security Israeli officials are responsible

BLEU is $6/7 * (6/6 * 4/5 * 2/4 * 1/3)^{1/4} \approx 52\%$

Note that BLEU is NOT normally used on a single sentence. It is usually evaluated over thousands of test sentences.



BLEU has been found to be highly correlated with human scores of adequacy and fluency.