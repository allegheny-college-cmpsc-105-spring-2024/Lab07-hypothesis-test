
# Hypothesis Testing

## Technical purpose of the lab

The technical purpose of this lab is to put together various aspects of the
data exploration pipeline on your own. The
pipeline includes finding raw data, turning it into python-ready data
(preferably numpy arrays), testing a hypothesis, and writing up the
exploration in a technical report.

## Backstory for the lab

At many stores in the US, one can buy both food and non-food items. The food
could be more or less processed, the non-food could be clothing, cleaning, or
other items. One can also pay at these stores with cash or card. The purchases
could be done in the evening or morning. Totals could be more or less than $10.
Many other categorizations or divisions of store data are possible.

For this lab, pretend that you have been asked to carry out a data exploration
using store receipt data. You will need to find raw data, come up with
a hypothesis, test it, plot your results, and write up the exploration. Below
is a summary of what you will do:

- think of a hypothesis that you want to test, for example, average cost of
  non-food items purchased at Target are $20.
- find and download receipt data that will address your hypothesis with minimum
  of 30 samples
- document the sources of your data in a reference section (urls are fine)
- place data into a dedicated rawdata directory with a reasonable naming scheme
- convert receipt data into usable numpy array(s) (probably by hand)
- compute test statistics to determine if your hypothesis is accepted or rejected
- make a plot of your results (OPTIONAL!!!!!)
- write a brief technical report

### How to think of a hypothesis

For the technical purposes of this lab, choose a manageable and testable
hypothesis that will allow you to practice your skills. The hypothesis does not
have to be insightful right now. Your final projects will give you a chance to
find real data and ask a more meaningful question.


### How to find raw data

Receipt images are easy to find on google images. There are also some OCR
databases, linked below. But again, you can keep this project small as a way to
practice. I.e. as long as you have 30 images that have the data you need, that
is fine.

Possible sources besides google images:

- https://www.kaggle.com/datasets/trainingdatapro/ocr-receipts-text-detection?select=images
- https://universe.roboflow.com/jakob-awn1e/receipt-or-invoice/dataset/5/images
- https://github.com/JensWalter/my-receipts/tree/master/2019/us/retail
- https://github.com/JensWalter/my-receipts/tree/master/2021/us

If you are attempting to compare two samples, please note that you will
have to make 30 independent (unrelated) observations for each sample, i.e. find
60 receipts. Comparing independent samples is not required.

Download images that you want to use into the `rawdata` directory, and give
the images names that are simple but informative.

### How to document your rawdata

Please record the URLs of the images in a references section and the names you
gave to the images. For example, 

```md
## References

- target_01.jpeg - https://s14354.pcdn.co/wp-content/uploads/2021/06/Target-pic-2-1024x999.jpg
- target_02.jpeg - https://thoughtcatalog.com/wp-content/uploads/2013/12/targetrece.jpg
- target_03.png - https://expensesreceipt.com/assets/img/retail-electronic-chain-store.png?ver=1.231
- walmart_14.jpg - https://i.pinimg.com/originals/16/94/e2/1694e2273e86812783c995048ec8872d.jpg
- walmart_15.jpg - https://seosvideos.files.wordpress.com/2014/11/receipt.jpg
- walmart_16.jpg - https://i.pinimg.com/564x/a8/3e/84/a83e84142bf74fd65fc91fb5352c7576.jpg
- walmart_17.jpg - https://bloximages.chicago2.vip.townnews.com/nwitimes.com/content/tncms/assets/v3/editorial/a/bf/abf38d2f-6181-5400-9fc5-62503348f5a7/5a02450b05ba4.image.jpg?resize=375%2C500
- walmart_18.jpg - https://www.the-sun.com/wp-content/uploads/sites/6/2024/03/catnc4-walmart-receipt-plastic-shopping-882563193.jpg
- walmart_19.jpg - https://www.nfcw.com/wp-content/uploads/2014/05/walmart-qr-receipt.jpg.webp
- walmart_20.jpg - https://m.media-amazon.com/images/M/MV5BODc4Y2JhZWEtNzU2MC00ZTFmLTk2OWEtMWY3NmNjN2UwM2RiXkEyXkFqcGdeQXVyNDQ3NjMzNjg@._V1_.jpg
```

### Get data into usable format

This process will be ver much like lab 06. `data = np.array([])`. This can be
filled in in the `analysis.py` file. Optionally, fill out anything that you
find to be useful in processed.csv.

### Statistical Testing

Please compute in the `analysis.py` file the tests needed to either accept or
reject your hypothesis.

Formula for test statistic from Normal Distribution for single sample. $\mu$ is
the population mean (related to hypothesis), $\bar{x}$ is the sample  or
observed mean, $s$ is the observed standard deviation, $n$ is the sample size.

$$ T = {{\bar{x}_1 - \mu_1}\over{\sqrt{s_1^2\over{n_1}}}} $$

Formula for test statistic from Normal Distribution for two independent samples

$$T = {(\bar{x}_1 - \bar{x}_2) - (\mu_1 - \mu_2)\over{\sqrt{s_1^2/{n_1} + s_2^2/{n_2}}} } $$

### Make a plot OPTIONAL!!!!!!!

In `analysis.py`, import matplotlib, and make a figure to illustrate your
analysis results. This part is optional, we will talk about more figure types
next week.

### What to put in the technical report

In approximately one page, please include:

- INTRODUCTION
    - general opening sentence to contextualize the report
    - Hypotheses tested (null and alternative)
    - why you were motivated to ask the question
    - Why and for whom this would be useful to know
- METHODS
    - How did you find the data
    - how did you transform it into usable data?
    - for ^^ provide enough information that someone else could replicate your
      steps
    - fenced code block with code you wrote to complete the hypothesis test
    - explanation of the code
- RESULTS
    - describe what the stats and numbers tell you about your original hypothesis
    - describe how the information you found can inform additional questions
- LIMITATIONS
    - Describe any problems in the data set
    - describe any confounds
    - describe biases in how you chose the data and what could be done to ameliorate the biases
    - describe compromises you had to make regarding the data
    - describe what would have been better
- REFERENCES

