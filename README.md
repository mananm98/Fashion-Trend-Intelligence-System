# Fashion-Trend-Intelligence-System
## Recommender system to predict current and upcoming fashion trends

Fashion Retailers try to draw inspiration from external sources such as e-commerce portals and
online fashion magazines to design the next set of fashion products that they can launch in order
to delight the customer. However, it is a manual effort intensive process, requiring a large team of
fashion designers.
In order to reduce dependency and make the overall process more efficient, we have created
a scalable tech solution to extract winning designs of apparels to design upcoming batch of fashion products.

## Use Cases
- Discover the current and future trends for fashion industry
- This software gives a second pair of creative eyes to fashion designers and forecasters. They do not have to spend hours, manually analysing images and producing trend reports
- Give power to small fashion designers and retailers to identify upcoming fashion trends quickly. Through this they can quickly capture winning trends and have a fighting chance against big fast fashion giants like zara and H&M

## Approach 
### Defining the notion of *trendiness*
- To define *trendiness* we scraped latest fashion images from social media platforms like instagram and Pinterest
- We used hashtags and searches like :
  - Instagram :- #InstaFashion, #FashionBlogger,  #Fashionista,  #StreetStyle,  #Stylish,  #InstaStyle
  - Pinterest :- mens fashion, fashion show, fashion week, new york fashion week, fashion trends, london fashion week
- These social platforms are very active and up to date. Moreover many people use these platforms to get inspiration for current fashion trends
- Images extracted from these platforms indicate what is currently in Fashion. Using searches like `fashion week`, `new york fashion week` and `london fashion week` we can also spot 
the upcoming fashion trends and forecast in this way.

<p align="center"> <img src = "https://github.com/mananm98/Fashion-Trend-Intelligence-System/blob/master/images/1.JPG"\> </p>


### Scrape images from Online Fashion Portals
- We scrape images from Online fashion portals like :
  - Blog.patternbank.com
  - collezioni.info
  - trendsense.com
  - vogue.co.in
  - vogue.co.uk/ 
  - stylebubble.co.uk
  - fashion.vignette.blogspot.com
  - nordstrom
  - mrporter
  - asos
- The images obtained from these websites denote the products currently in market
- Now we will extract the most hit designs from these products

### Recommendation System
- To extract winning designs from these real world products, we use a recommendation engine
- We feed `trendy clothing items from social media` to the recommender system.
- The job of the recommender system is to find the most similar images from the images obtained from `Online Fashion Portals`

<p align="center"> <img src = "https://github.com/mananm98/Fashion-Trend-Intelligence-System/blob/master/images/2.JPG"\> </p>


- For our Recommendation system we use Deep Learning CNN model (EfficientNet-B3 model).
- Given an input image the CNN produces a 2304 vector
- The hope is that our model can learn a good enough embedding space, so that similar clothing items should lie close together.

<p align="center"> <img src = "https://github.com/mananm98/Fashion-Trend-Intelligence-System/blob/master/images/3.JPG"\> </p>
  
  
### Training the model
- To learn a good embedding space, we used triplet siamese network
- A triplet siamese network is trained with a group of 3 images i.e two siilar images (anchor and positive) and one dissimilar image (negative). The network has shared weights. For each image an embedding is generated. Then these three embeddings are given to the hinge loss function which is responsible for pushing the embeddings of anchor and positive images together and it pushes away the negative embedding.

<p align="center"> <img src = "https://github.com/mananm98/Fashion-Trend-Intelligence-System/blob/master/images/4.JPG"\> </p>
  
 - By training on good triplets, model can learn to group together clothing items with similar patterns and features.
 
 
 ## Dataset 
 - The dataset we use is the [DeepFashion](http://mmlab.ie.cuhk.edu.hk/projects/DeepFashion.html) dataset. DeepFashion is a large clothing database. This database has consumer shop pairs for each product. That means for each clothing item, the dataset contains well posed shop photos and real world consumer photos.
  
- Our model is only trained on `mens T-shirts`. So we used only mens images from this dataset.
- To generate/mine [triplets](https://github.com/mananm98/Fashion-Trend-Intelligence-System/blob/master/Triplet_mining.ipynb) we used the shop-consumer pairs. We took consumer images as anchors and shop images as positives. This is because anchors resemble real world images extracted from social media and positives resemble shop images obtained from Fashion portals.
- For the negatives, for each anchor-postive pair we sampled three in-class negatives (same category but different product) and two out-class negatives (different categories)

<p align="center"> <img src = "https://github.com/mananm98/Fashion-Trend-Intelligence-System/blob/master/images/5.JPG"\> </p> 
  
- Link to [DeepFashion](http://mmlab.ie.cuhk.edu.hk/projects/DeepFashion.html)

## Results
- *First image is the query image and corresponding 4 images in each row are the recommended images*
- *These results were performed on a test dataset, not on images from social media and websites*

<p align="center"> <img src = "https://github.com/mananm98/Fashion-Trend-Intelligence-System/blob/master/images/6.JPG"\> </p> 
<p align="center"> <img src = "https://github.com/mananm98/Fashion-Trend-Intelligence-System/blob/master/images/7.JPG"\> </p> 


## References
- [Deep Learning based Large Scale Visual Recommendation and
Search for E-Commerce](https://arxiv.org/pdf/1703.02344v1.pdf)
- [Street Style Research Paper](https://arxiv.org/abs/1706.01869)
- [Using Artificial Intelligence to Analyze Fashion Trends](https://arxiv.org/pdf/2005.00986.pdf)  
- [FashionPedia](https://arxiv.org/pdf/2004.12276.pdf)
- https://fashionpedia.github.io/home/index.html 
  

