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
query    topic                                                                                           
autism vaccine     mmr vaccine and autism
```


**2. Unpersonalized Experiment**
* Unpersonalised search results: all_results.csv* [(download)](https://github.com/social-comp/YouTubeAudit-data/blob/master/all_results.csv?raw=true) The file contains a collection of 36,000 search results and their meta data collected over 15 days. The file contains the following fields: -
   * ```query:``` name of the query searched
   * ```topic:``` name of the vaccine-related search topic 
   * ```date_exp_run:``` date on which the search was performed
   * ```filter:``` name of the Amazon filter used to sort search results
   * ```search_result_rank:``` rank of the search result in the Search Engine Results Page (SERP)
   * ```URL:``` URL of the Amazon product
   * ```url_code:``` URL code of the Amazon product. This code is extracted from the product URL
   * ```title:``` title of the Amazon product
   * ```category:``` category of the Amazon product
   * ```is_prime:``` this field indicates whether the product had an Amazon prime batch or not
   * ```price:``` price of the Amazon product
   * ```is_sponsored:``` this field indicates whether the product is sponsored on Amazon
   * ```reviews:``` number of reviews received by the Amazon product
   * ```rating:``` star rating of the Amazon product
   * ```date_of_publishing:```	date of publishing of the Amazon product
   * ```bestseller:``` indicates whether the Amazon product is a best-seller or not
   * ```annotation:``` annotation value assigned to the Amazon product. For details on the annotation scheme, please refer the paper

A snippet:

```html
query	topic	date_exp_run	filter	search_result_rank	URL	url_code	title	category	is_prime	price	is_sponsored	reviews	rating	date_of_publishing	bestseller	annotation
                                                        

andrew wakefield	andrew wakefield	5/2/2020	featured	2	http://www.amazon.com/Vaccine-Court-Americas-Compensation-Program/dp/1629144525/ref=sr_1_2?dchild=1&keywords=andrew+wakefield&qid=1588435229&sr=8-2	1629144525	The Vaccine Court: The Dark Truth of America's Vaccine Injury Compensation Program	Books	Y	$24.49 	N	28 ratings	5.0 out of 5 stars	11-Nov-14	N	1
```
