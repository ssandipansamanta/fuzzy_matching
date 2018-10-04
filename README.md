Recommendation-Engine: An Offline-Online Approach
===================================================

## Description

A simple approach to cluster the listings data into similar items. 
clusters that can be used in this way: If the items A and B are part of the
same cluster it is reasonable to recommend B to a user that is viewing or has
viewed A. Feel free to use the category information that sellers have used to
classify their listings in any way.

## Dataset

A sample of listings taken from the south african olx site as well as a list of popular recent keywords.


## Approach

The recommendation engine is build using 'sampleinputfile' present in Input Folder. It's a content based recommendation problem.
In the sample file, with Product and selling information, Category and location information also available. Geographical 
location is quite important to know as it's very unlikely to sell/buy a product to a different location. Recommendation is 
applied by location and category level.

**Offline**:(Asynchronous mode to run)
 
Product description i.e. listing are classified in multiple clusters to reduce dimensions/# of products. Key words are 
also listed for each clusters.

**Online**:(Synchronous mode to run)

Based on product listing, recommender will search the products for that particular cluster. As the # of entries are reduced
so it can be done in real time. Based on number of recommendation, recommender engine will provide the nearest match based on 
score and also report price for that product. If user will choose a big number(100X); engine will provide all the products
present in the cluster and ranking would be done based on search Scores.

**Newly Listed listing**:

In current methodology, Clustering at offline phase find key terms for each cluster. We can use these key words for the new product listing and get the cluster information and relevant products.

## Possible Shortcomings & Extensions

The methodology is simple and not robust. Definitely, the methodology mentioned in below paper can boost the performance. 
Using graph/network based recommendation also be a good choice. Sentiment analysis using listing descrtiion can also be used for ranking products.
 
In terms of efficiency, the code is not scalable at this point, it's taking long time to get the location, potentially multi-processing
would be the choice for offline phase. The set up can be run parallely for multiple categories at the same time using docker or using simple shell script.
                        
## Reading Materials
  [Recommending Similar Items in Large-scale Online Marketplaces](https://pdfs.semanticscholar.org/e107/0c60d926e69298263e9ca36c698b69a21914.pdf)
  