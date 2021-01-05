## Data Description
This webpage contains details about the data accompanying CHI 2021 paper Auditing E-Commerce Platforms for Algorithmically Curated VaccineMisinformation. The data was collected during two sets of audit experiments---<i>Unpersonalized audit</i> and <i>Personalized audit</i>. Through these audit experiments, we investigate the role of search and recommendation algorithms employed by Amazon in surfacing and amplifying vaccine misinformation. In the <i>Unpersonalized audit</i>, we determine the amount of health misinformation users are exposed to when searching for vaccine-related queries. In particular, we examine search-results of 48 search queries belonging to 10 popular vaccine-related topics without logging in to Amazon to eliminate the influence of personalization. Our <i>Unpersonalized audit</i> ran for 15 consecutive days, sorting the search results across 5 different Amazon filters each day: featured, price low to high, price high to low, average customer review and newest arrivals. The first audit resulted in 36,000 search results and 16,815 product page recommendations which we later annotated for their stance on health misinformation—promoting, neutral or debunking.
 
In our second set of audit---<i>Personalized audit</i>, we determine the impact of personalization due to user history on the amount of health misinformation returned in search results, recommendations and auto-complete suggestions. User history is built progressively over 7 days by performing several real-world actions such as search, search + click, search + click + add to cart, search + click + mark top-rated all positive review as helpful, follow contributor and search on third party website. The second audit resulted in  search results and  recommendations. The audit data is spread across four files. The description of each file along with their downloadable link is listed below
  
  
**1. Queries file**  
filename: *queries.csv* [(download)](https://raw.githubusercontent.com/social-comp/AmazonAudit-data/main/queries.csv)
   The file consists of a complete list of 48 search queries used in the audit study. It contains the following fields: -
  
  * ```query:``` name of the search query
  * ```topic:``` name of the vaccine-related search topic  
  
   A snippet:
   
  
```html
query              topic
andrew wakefield	     andrew wakefield
```
