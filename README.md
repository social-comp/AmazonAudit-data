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


**2. Unpersonalized Audit**
* __Unpersonalised search results__: filename- *unpersonalized_seach_results.csv* [(download)](https://github.com/social-comp/YouTubeAudit-data/blob/master/all_results.csv?raw=true). The file contains a collection of 36,000 search results and their meta data collected over 15 days during our <i>Unpersonalized audit</i> run. It consists of the following fields:-
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

**2. Personalized Audit**
* __Account details__: filename- *account_details.csv* [(download)](https://github.com/social-comp/AmazonAudit-data/raw/main/account_details.csv). The file contains the details of accounts set up in the <i>Personalized audit</i>. Each account builds up its history by performing real-world actions on products that were either all annotated as promoting misinformation, neutral or debunking. The file contains the following fields:-
   * ```code:``` code assigned to the account
   * ```action:``` real-world action performed by the sock-puppet account 
   * ```account_history_built_by_performising_action_on_product_type:``` type of product on which the socket puppet account performs actions. The field can have one of the three values namely, promoting misinformation, neutral or debunking.
   * ```search_filter1:``` name of the first Amazon filter used to sort results by the account
   * ```search_filter2:``` name of the second Amazon filter used to sort results by the account
 
 A snippet:

```html
code	action	account_history_built_by_performising_action_on_product_type	search_filter1	search_filter2                                                        

p3	search+click+add_to_cart	neutral	featured	average customer review
```

* __Personalised search results__: filename- *personalization_search_results.csv* [(download)](https://github.com/social-comp/AmazonAudit-data/raw/main/personalization_search_results.zip). The file contains a collection of 2,68,800 search results collected over 7 days during our <i>Personalized audit</i> run. It consists of the following fields:-
   * ```topic:``` name of the vaccine-related search topic 
   * ```query_with_underscore:``` name of the query searched separated by underscore
   * ```query:``` name of the query searched
   * ```folder:``` code of the sock puppet account. The attributes of the suck-pupper accounts is present in *account_details.csv*  
   * ```filter:``` name of the Amazon filter used to sort search results
   * ```date:``` date on which the data collection occurred
   * ```rank:``` rank of the search result in the Search Engine Results Page (SERP)
   * ```url_code:``` URL code of the Amazon product. This code is extracted from the product URL
   * ```URL:``` URL of the Amazon product
   * ```title:``` title of the Amazon product
   
A snippet:

```html
topic	query_with_underscore	query	folder	filter	date	rank	url_code	url	title
                                              
vaccination	vaccination	vaccination	p22	search_results_priceLtoH	8/12/2020	3	B00NS42D28	http://www.amazon.com/Vaccine-Injuries-Documented-Reactions-Vaccines-ebook/dp/B00NS42D28/ref=sr_1_3?dchild=1&keywords=vaccination&qid=1597219049&sr=8-3	Vaccine Injuries: Documented Adverse Reactions to Vaccines
```

* __Pre-purchase recommendations__: filename- *pre_purchase_recommendations_.csv* [(download)](https://github.com/social-comp/AmazonAudit-data/raw/main/pre_purchase_recommendations_.csv). The file contains pre-purchase recommendations collected during <i>Personalized audit</i> run. Pre-purchase recommendations consist of product suggestions that are presented to users after they add product(s) to cart. Pre-page recommendations could be of the types Frequently bought together, Customers also bought these highly rated items, Related to items you'veviewed, etc. The file consists of the following fields:-
   * ```folder:``` code of the sock puppet account. The attributes of the suck-pupper accounts is present in *account_details.csv*  
   * ```date:``` date on which the data collection occurred
   * ```type_of_recommendation:``` this field indicates the type of pre-purchase recommendation
   * ```rank:``` rank of the amazon product in the recommendation list of type present in the field <i>type_of_recommendation</i>
   * ```url_code:``` URL code of the Amazon product. This code is extracted from the product URL
   * ```URL:``` URL of the Amazon product
   * ```annotation:``` annotation value assigned to the Amazon product
   
A snippet:

```html
folder	date	type_of_recommendation	rank	url_code	url	annotation
                                              
p3	8/12/2020	Customers who shopped	1	1441321659	http://www.amazon.com/gp/upsell-widgets/click-logger.html?widgetName=desktop-huc-carousels_huc-semantic-session-sims-scf&column=1&row=1&clickType=Title&url=%2Fdp%2F1441321659%3Fpsc%3D1%26pf_rd_p%3D995e9308-9761-4a71-9419-82fd033b88fd%26pf_rd_r%3DPSKTKDF89JM86WTTRXFX%26pd_rd_wg%3DNn0ES%26pd_rd_i%3D1441321659%26pd_rd_w%3D3ilS9%26pd_rd_r%3D39af52b4-1699-4cd5-924b-a0a89f52c26d%26ref_%3Dpd_luc_rh_crh_rh_sbs_sem_01_01_t_img_lh/	0
```

* __Homepage recommendations__: filename- *homepage_recommendations_.csv* [(download)](https://github.com/social-comp/AmazonAudit-data/raw/main/homepage_recommendations_.csv). The file contains homepage recommendations collected during <i>Personalized audit</i> run. These recommendations are present on the homepage of a user’s Amazonaccount. The homepage recommendations could be of three types Related to items you've viewed, Inspiredby your shopping trends and Recommended items other customers often buy again. The file consists of the following fields:-
   * ```folder:``` code of the sock puppet account. The attributes of the suck-pupper accounts is present in *account_details.csv*  
   * ```date:``` date on which the data collection occurred
   * ```type_of_recommendation:``` this field indicates the type of homepage recommendation
   * ```rank:``` rank of the amazon product in the recommendation list of type present in the field <i>type_of_recommendation</i>
   * ```url_code:``` URL code of the Amazon product. This code is extracted from the product URL
   * ```URL:``` URL of the Amazon product
   * ```annotation:``` annotation value assigned to the Amazon product
   
A snippet:

```html
folder	date	type_of_recommendation	rank	url_code	url	annotation
                                              
p14	8/12/2020	Related to items you've viewed	1	188121740X	http://www.amazon.com/Millers-Review-Critical-Vaccine-Studies/dp/188121740X/	1
```

* __Product page recommendations__: filename- *product_page_recommendations_.csv* [(download)](https://github.com/social-comp/AmazonAudit-data/raw/main/product_page_recommendations_.csv). The file contains homepage recommendations collected during <i>Personalized audit</i> run. These are the recommendations present on the product page. They could be of five types namely, Frequently bought together, What other items customers buy after viewingthis item, Customers who viewed this item also viewed, Sponsored products related to this item and Customerswho bought this item also bought. The file consists of the following fields:-
   * ```folder:``` code of the sock puppet account. The attributes of the suck-pupper accounts is present in *account_details.csv*  
   * ```date:``` date on which the data collection occurred
   * ```type_of_recommendation:``` this field indicates the type of product page recommendation
   * ```rank:``` rank of the amazon product in the recommendation list of type present in the field <i>type_of_recommendation</i>
   * ```url_code:``` URL code of the Amazon product. This code is extracted from the product URL
   * ```URL:``` URL of the Amazon product
   * ```annotation:``` annotation value assigned to the Amazon product
   
A snippet:

```html
folder	date	type_of_recommendation	rank	url_code	url	annotation
                                              
p29	8/12/2020	1	803657668	frequently bought together	http://www.amazon.com/New-Leadership-Challenge-Creating-Nursing/dp/0803657668/ref=pd_bxgy_img_2/131-1077905-1219437?_encoding=UTF8&pd_rd_i=0803657668&pd_rd_r=28c31f7a-ded6-4eea-8751-0ad00c46aabc&pd_rd_w=ELi0X&pd_rd_wg=UzbeC&pf_rd_p=ce6c479b-ef53-49a6-845b-bbbf35c28dd3&pf_rd_r=N9NDDMNCKY5Y8TB43V89&psc=1&refRID=N9NDDMNCKY5Y8TB43V89	0
```


**3. Annotations**: filename- *all_unique_products.csv* [(download)](https://github.com/social-comp/AmazonAudit-data/raw/main/all_unique_products.csv). The file consists of a dataset of 4,997 unique Amazon products collected and annotated for health misinformation during our first and second audit data collection. It contains the following fields:-
  
  * ```url_code:``` URL code of the Amazon product
  * ```url:``` URL of the Amazon product  
  * ```annotation:``` annotation value assigned to the Amazon product
  
   A snippet:
   
```html
url_code	url	annotation                                                                                  
B004ULLOIC	http://www.amazon.com/dp/B004ULLOIC	1
```
