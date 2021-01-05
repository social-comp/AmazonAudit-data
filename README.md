## Data Description
This webpage contains details about the data accompanying CHI 2021 paper Auditing E-Commerce Platforms for Algorithmically Curated VaccineMisinformation. The data was collected during two sets of audit experiments---<i>Unpersonalized audit</i> and <i>Personalized audit</i>. Through these audit experiments, we investigate the role of search and recommendation algorithms employed by Amazon in surfacing and amplifying vaccine misinformation. In the <i>Unpersonalized audit</i>, we determine the amount of health misinformation users are exposed to when searching for vaccine-related queries. In particular, we examine search-results of 48 search queries belonging to 10 popular vaccine-related topics without logging in to Amazon to eliminate the influence of personalization. Our <i>Unpersonalized audit</i> ran for 15 consecutive days, sorting the search results across 5 different Amazon filters each day: featured, price low to high, price high to low, average customer review and newest arrivals. The first audit resulted in 36,000 search results and 16,815 product page recommendations which we later annotated for their stance on health misinformation—promoting, neutral or debunking.
 
In our second set of audit---<i>Personalized audit</i>, we determine the impact of personalization due to user history on the amount of health misinformation returned in search results, recommendations and auto-complete suggestions. User history is built progressively over 7 days by performing several real-world actions such as search, search + click, search + click + add to cart, search + click + mark top-rated all positive review as helpful, follow contributor and search on third party website. The second audit resulted in  search results and  recommendations. The audit data is spread across four files. The description of each file along with their downloadable link is listed below
  
  
**1. Queries file**: filename- *queries.csv* [(download)](https://raw.githubusercontent.com/social-comp/AmazonAudit-data/main/queries.csv). The file consists of a complete list of 48 search queries used in the audit study. It contains the following fields:-
  
  * ```query:``` name of the search query
  * ```topic:``` name of the vaccine-related search topic  
  
   A snippet:
   
```html
query	topic                                                                                  
vaccination book	vaccination
```


**2. Unpersonalized Experiment**
* __Unpersonalised search results__: filename- *unpersonalized_seach_results.csv.csv* [(download)](https://github.com/social-comp/YouTubeAudit-data/blob/master/all_results.csv?raw=true). The file contains a collection of 36,000 search results and their meta data collected over 15 days. It contains the following fields:-
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

* __Unpersonalised recommendations__: filename- *unpersonalized_recommendations.csv* [(download)](https://raw.githubusercontent.com/social-comp/AmazonAudit-data/main/unpersonalized_recommendations.csv). The file contains the product page recommendations of first three Amazon products present in the search results. The product page recommendations could be of five types namely, Frequently bought together, What other items customers buy after viewingthis item, Customers who viewed this item also viewed, Sponsored products related to this item and Customerswho bought this item also bought. We extracted the first product present in each recommendation type for analysis. The file contains the following fields:-
   * ```query:``` name of the query searched
   * ```topic:``` name of the vaccine-related search topic 
   * ```date_exp_run:``` date on which the search was performed
   * ```filter:``` name of the Amazon filter used to sort search results
   * ```search_result_rank:``` rank of the search result in the Search Engine Results Page (SERP)
   * ```URL:``` URL of the Amazon product
   * ```url_code:``` URL code of the Amazon product. This code is extracted from the product URL
   * ```title:``` title of the Amazon product
   * ```annotation:``` annotation value assigned to the Amazon product present in the search results.
   * ```type_of_recommendation:``` this field indicates the type of product page recommendation
   * ```destination_url:``` URL of the Amazon product present in the recommendation
   * ```destination_url_code:``` URL code of the Amazon product present in the recommendation
   * ```recommendation_annotation:``` annotation value assigned to the recommended Amazon product
 
A snippet:

```html
query	topic	date_exp_run_x	filter	search_result_rank	URL	url_code	title	source_annotation	type_of_recommendation	destination_url	destination_url_code	recommendation_annotation                                                        

andrew wakefield	andrew wakefield	5/2/2020	featured	1	http://www.amazon.com/Callous-Disregard-Autism-Vaccines-Tragedy-ebook/dp/B004N62HRQ/ref=sr_1_1?dchild=1&keywords=andrew+wakefield&qid=1588435229&sr=8-1	B004N62HRQ	Callous Disregard: Autism and Vaccines: The Truth Behind a Tragedy	1	customer_view_after_viewing	http://www.amazon.com/Vaccine-Illusion-Tetyana-Obukhanych-ebook/dp/B007AW2CLG/ref=pd_sbs_351_1/138-6517699-9726254?_encoding=UTF8&pd_rd_i=B007AW2CLG&pd_rd_r=aa42a33a-515e-4a68-9e04-4e59632333be&pd_rd_w=BE30s&pd_rd_wg=MlD9i&pf_rd_p=d13bb895-21d3-4e96-94a7-553aaae51224&pf_rd_r=QXT0TP71K2BNMZSXVGB5&psc=1&refRID=QXT0TP71K2BNMZSXVGB5	B007AW2CLG	1

```

**2. Personalized Experiment**
* __Personalised search results__: 

**4. Annotations**: filename- *all_unique_products.csv* [(download)](https://github.com/social-comp/AmazonAudit-data/raw/main/all_unique_products.csv). The file consists of a dataset of 4,997 unique Amazon products collected and annotated for health misinformation during our first and second audit data collection. It contains the following fields:-
  
  * ```url_code:``` URL code of the Amazon product
  * ```url:``` URL of the Amazon product  
  * ```annotation:``` annotation value assigned to the Amazon product
  
   A snippet:
   
```html
url_code	url	annotation                                                                                  
B004ULLOIC	http://www.amazon.com/dp/B004ULLOIC	1
```
