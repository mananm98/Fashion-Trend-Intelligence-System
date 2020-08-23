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

<p align="center"> <img src = ""\> <\p>


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

<p align="center"> <img src = ""\> <\p>


###
