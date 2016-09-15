# YarnTxtMining

##Text Mining / Document Clustering / Classification Modelling on yarn social media data

###Overview
Comments from users of Ravelry.com, a popular site for fiber artists community who knit and crochet to share knowledge/preferences was mined by web scraping.  Additional features from the backend database of other yarn attributes were also retrieved.
With over 6 million user accounts, many of them active monthly users, it is the largest and most active topic-specific social network

Each yarn in Ravelry’s database has a page of text comments, similar to reviews. We seek to gain information from these comments and use that information, in addition to the features already available in Ravelry’s database, to predict how likely a yarn is to pill or split, relative to the set of all yarns that have comments.  The two most unwanted yarn attributes to be pilling and splitting, obtained by polling the user community

We scraped data from the Ravelry API and from Ravelry.com. It was most efficient to retrieve attributes available
in the database from the API but comments and various popularity measures were available only from the website itself.

###Text Mining and Document Clustering
After scraping comments from the web, we started with a set of 33,752 comment rows for 3,743 yarns. Each comment
was retrieved into a separate row, and indexed by its yarn ID. Some exploratory testing revealed that it was best to
come up with our own unique list of stop words customized for the yarn comments dataset. We also explored keeping 2
special characters, ‘!’, and ‘?’ but decided they were not adding value as identifying sentiment. The Snowball Stemmer
was also preferred over the popular Porter Stemmer. This came from analyzing simple word frequencies that resulted
from exploration passes at simple clustering using K Means.

###Yarn Classifier Model Testing and Evaluation
Because the yarn data has been hand scraped from a web site, and we had to hand label data rows for training, we have
a small dataset for training relative to the final dataset yarn we will predict on
