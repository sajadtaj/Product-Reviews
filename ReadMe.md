```

```

# get data about product rating and review.

first start by google and amazon (api):

### Google:

Google doesn't currently offer a public API specifically for retrieving product reviews

### Amazon :

No Direct Review Text: Unfortunately, the PA API doesn't provide access to the actual text of customer reviews.
Individual Review Scores: You cannot access the individual ratings assigned by each reviewer.
Breakdown by Rating: The API doesn't provide details on how many reviews fall under each star rating (1-star, 2-star, etc.).

## Alternative Approaches:

* Web Scraping
* Third-Party APIs :
  * `Rainforest` API for Amazon Product Reviews and Ratings
    Rainforest API offers a solution to access product data from Amazon, including reviews and ratings, potentially providing a more robust alternative to Amazon's PA API. Here's a breakdown of what Rainforest API offers:
  * Customer Reviews: You can retrieve the full text of customer reviews for a product on Amazon. This allows you to analyze sentiment, identify specific aspects mentioned in reviews, and gain deeper insights into user experience.
  * Reviewer Information: Rainforest API provides details like reviewer name (if available), helpful votes received, and the date of the review.
    Rating Data:
  * Average Customer Rating: Similar to the PA API, Rainforest API provides the average customer rating (out of 5).
  * Review Rating Breakdown (Optional): While not always guaranteed, some Rainforest API plans might offer a breakdown of how many reviews fall under each star rating (1-star, 2-star, etc.). This provides more granular information on user sentiment.


# problems
###  1-find Product :
  + each product have `many seller`
  + each product have `many parameters` (phone , TV , pillow) each one , have many different parameters.
  + `Irrelevant` findings 

  ![alt text](./pic/Screenshot%20from%202024-07-16%2015-35-34.png)
  ![alt text](./pic/Screenshot%20from%202024-07-16%2015-37-06.png)
  ![alt text](./pic/Screenshot%20from%202024-07-16%2015-37-43.png)
### 2-Rating :
  In addition to product quality, the following factors also play a role in scoring:
  + How to send
  + Seller
  + Shipping time
  + healthy

## Rainforest API

> Rainforest API Pricing: https://www.rainforestapi.com/pricing

> Rainforest API Getting Started Guide: [https://www.rainforestapi.com/docs](https://www.rainforestapi.com/docs)

## Search Product

### Search : `apple iphone 15 pro max`
#### You can set parameter for search:
> for  `Irrelevant` findings use : `direct_search : true`
```python
params = {
    'api_key'       : api_key,
    'type': 'search',
    'amazon_domain': 'amazon.com',
    'search_term': 'apple iphone 15 pro max',
    'direct_search':'true'
    }
```
### Result:

|FIELD1|title                                                                                                                                                                                                   |rating|asin      |ratings_total|
|------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------|----------|-------------|
|0     |Apple iPhone 15 Pro Max Silicone Case with MagSafe - Winter Blue                                                                                                                                        |4.1   |B0CHWVCV1Y|4075.0       |
|1     |Apple MagSafe Charger - Wireless Charger with Fast Charging Capability, Compatible with iPhone and AirPods                                                                                              |4.5   |B08L5NP6NG|71868.0      |
|2     |Boost Infinite iPhone 15 Pro Max (256 GB) — Natural Titanium [Locked]. Requires unlimited plan starting at $60/mo.                                                                                      |4.3   |B0CHBQTL9Z|218.0        |
|3     |Boost Infinite iPhone 15 Pro (128 GB) — Natural Titanium [Locked]. Requires unlimited plan starting at $60/mo.                                                                                          |4.1   |B0CHBMRD1G|74.0         |
|4     |Boost Infinite iPhone 15 Plus (128 GB) — Pink [Locked]. Requires unlimited plan starting at $60/mo.                                                                                                     |4.6   |B0CHBPTX1P|52.0         |
|5     |Boost Infinite iPhone 15 (128 GB) — Pink [Locked]. Requires unlimited plan starting at $60/mo.                                                                                                          |4.0   |B0CHBNXW73|50.0         |
|6     |Apple iPhone 15 Pro Max, 256GB, Natural Titanium - Unlocked (Renewed)                                                                                                                                   |4.1   |B0CMZD7VCV|50.0         |
|7     |Apple iPhone 15 Pro Max, 256GB, Blue Titanium - Unlocked (Renewed Premium)                                                                                                                              |2.8   |B0CRHZZLYR|5.0          |
|8     |Apple iPhone 15 Pro Max, 512GB, Black Titanium - Unlocked (Renewed)                                                                                                                                     |4.5   |B0CMZH1SGK|8.0          |
|9     |Apple iPhone 15 Pro Max, 256GB, Black Titanium - Unlocked (Renewed Premium)                                                                                                                             |3.6   |B0CRJJBBPY|6.0          |
|10    |Apple iPhone 15 Pro Max, 256GB, Blue Titanium - AT&T (Renewed)                                                                                                                                          |5.0   |B0CMZ58ZN7|2.0          |
|11    |Apple iPhone 15 Pro Max, 256GB, Black Titanium - Unlocked (Renewed)                                                                                                                                     |4.4   |B0CMZ4FQL4|32.0         |
|12    |Apple iPhone 15 Pro Max, 256GB, Natural Titanium - Unlocked (Renewed Premium)                                                                                                                           |3.2   |B0CRJSBN5M|8.0          |
|13    |Apple iPhone 15 Pro Max, 512GB, Blue Titanium - Unlocked (Renewed)                                                                                                                                      |4.3   |B0CMZ46PHR|15.0         |
|14    |Apple iPhone 15 Pro Max, 512GB, White Titanium - Unlocked (Renewed Premium)                                                                                                                             |      |B0CRJP4H1M|             |
|15    |Apple iPhone 15 Pro Max / 256GB / Black Titanium - MU663LL/A (SIM Free)                                                                                                                                 |4.4   |B0CLMGHDBV|15.0         |
|16    |Apple iPhone 15 Pro Max, 256GB, Natural Titanium - AT&T (Renewed)                                                                                                                                       |3.2   |B0CMZ3HT9K|8.0          |
|17    |Apple iPhone 15 Pro Max, 512GB, Blue Titanium - Unlocked (Renewed Premium)                                                                                                                              |2.5   |B0CRJ3HN3X|3.0          |
|18    |Apple iPhone 15 Pro Max, 256GB, White Titanium - Unlocked (Renewed)                                                                                                                                     |4.3   |B0CMZDY2ZV|29.0         |
|19    |Apple iPhone 14 Pro Max, 128GB, Deep Purple - Unlocked (Renewed)                                                                                                                                        |4.1   |B0BN9P1GXC|1907.0       |
|20    |Apple iPhone 15 Pro Max, 256GB, Blue Titanium - Unlocked (Renewed)                                                                                                                                      |4.1   |B0CMZDBVWT|37.0         |
|21    |Apple iPhone 15 Pro Max, 256GB, Blue Titanium - Verizon (Renewed)                                                                                                                                       |5.0   |B0CMZ4463K|1.0          |
|22    |Boost Infinite iPhone 15 Pro Max (1 TB) — White Titanium [Locked]. Requires unlimited plan starting at $60/mo.                                                                                          |4.3   |B0CHBQB7NY|218.0        |
|23    |【Upgraded】 SUPERONE Retractable Car Charger 4 in 1, Fast Car Phone Charger with Cord 2.6ft, USB C and Apple Car Charger Adapter, Compatible with iPhone 15/15 Pro Max/14/13/12/11, Galaxy, Pixel        |4.5   |B0CJDTC6ZB|934.0        |
|24    |DIMONCOAT 4-PACK for iPhone 15 Pro Max Privacy Screen Protector [Auto Alignment Kit] [10X Military Protection] Compatible iPhone 15 Pro Max 6.7 inch Tempered Glass Film [Case Friendly]                |4.1   |B0CP3SZC7V|3249.0       |
|25    |【MFi Certified】iPhone 15 Car Charger Fast Charging, Braveridge 75W USB-C PD&QC Car Power Cigarette Lighter USB Car Charger + 6FT Type-C Coiled Cable for iPhone 15 Pro/15 Pro Max, Galaxy S24/S23, Pixel|4.5   |B0CPM2LPH7|5544.0       |
|26    |[2 Pack] USB-C Wall Charger, 40W Durable 4Port QC+PD 3.0 Power Adapter, Double Fast Plug Charging Block for iPhone 15/15 Pro/ 15 Pro Max/15 Plus/14/13/12, XS/XR/X, Watch Series 8/7 Cube(White)        |4.6   |B0B5SQMCXG|2979.0       |
|27    |2-Pack 40W USB C Wall Plug, 4 Port Fast Charging Block PD 3.0 Multi Port Type C Adapter Cube for iPhone 15/13/13pro/12/12pro/XR/SE, iPad Pro/Mini/Air, Google Pixel/Pixel 3a/ XL/3/2XL                  |4.6   |B0C4Y9DXX9|268.0        |
|28    |For iPhone 15 Pro Max Case For Magsafe [2 Camera Lens +2 Privacy Screen Protector] For iPhone 15 Promax Case Protective Shockproof Translucent Matte Cover For iPhone 15 Pro Max Phone Case Black       |4.5   |B0C6B4TZS2|116.0        |


### output as json include :

+ Product :

  + title
  + availability
  + categories
  + link
  + image
  + prices
+ related_searches
+ related_brands
+ pagination :

  + total_results
  + current_page
  + next_page_link
  + total_pages




| Parameter          | Required | Description                                                                                                                  |
| ------------------ | -------- | ---------------------------------------------------------------------------------------------------------------------------- |
| amazon\_domain     | No       | The Amazon domain to search on. Defaults to "US" if not specified.                                                           |
| search\_term       | Yes      | The search query to use. This parameter is mandatory                                                                         |
| refinements        | No       | A list of refinement filters to narrow down your search.                                                                     |
| category\_id       | No       | The category ID to filter by.                                                                                                |
| sort\_by           | No       | The field to sort the results by.                                                                                            |
| exclude\_sponsored | No       | A boolean value indicating whether to exclude sponsored products from the search results.                                    |
| page               | No       | The page number to return.                                                                                                   |
| max\_page          | No       | The maximum page number to return.                                                                                           |
| url                | No       | A product URL to get details for a specific product.                                                                         |
| direct\_search     | No       | A boolean value indicating whether to perform a direct search on Amazon instead of using the Rainforest API product catalog. |

## Reviews

ASIN : for Each product is unique

Example for apple 15 pro max asin : B0CMZD7VCV

```python
# set up the request parameters
params = {
  'api_key': 'FDFF1602461F43BCAB27E81D648A7E27',
  'type': 'reviews',
  'amazon_domain': 'amazon.com',
  'asin': 'B0CMZD7VCV',
  'review_stars': 'all_critical',
  'sort_by': 'most_recent'
}
```

Output:

+ product
  + title
  + link
+ summary
+ rating
+ ratings_total
+ reviews_total_filtered
+ reviews_total
+ rating_breakdown
+ reviews:
  + id
  + title
  + body
  + asin
  + link
  + rating
  + date
  + verified_purchase
  + is_global_review
  + review_country

### You can set parameter for search:


| Parameter      | Required | Description                                                                                                                                                                           |
| -------------- | -------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| amazon\_domain | No       | The Amazon domain to retrieve reviews from. Defaults to "US" if not specified.                                                                                                        |
| asin           | No       | The Amazon ASIN (product ID) to retrieve reviews for. Required to retrieve reviews for a specific product.                                                                            |
| gtin           | No       | A GTIN, ISBN, UPC or EAN code to retrieve results for.                                                                                                                                |
| reviewer\_type | No       | The type of reviewer to retrieve reviews from. Valid values are "verified\_purchase" and "all".                                                                                       |
| review\_stars  | No       | The star rating of reviews to retrieve. Valid values include "all\_stars", "five\_star", "four\_star", "three\_star", "two\_star", "one\_star", "all\_positive", and "all\_critical". |
| sort\_by       | No       | Determines the sort order of reviews to return. Valid values are "most\_helpful" and "most\_recent".                                                                                  |
| search_term    | No       | A search term to use to search reviews.                                                                                                                                               |
| page           | No       | The current page of reviews to retrieve. Inspect the pagination.total_pages property in the Reviews results to see how many pages of reviews are available.                           |
| max_page       | No       | Use the max_page parameter to get multiple pages of results in one request. The API will automatically paginate through pages and concatenate the results into one response.          |

## ratings

We can find rating for each Asin :

### Step 1

```python
params = {
  # like before params
  api_result = requests.get('https://api.rainforestapi.com/request', params)
}
```

### Step 2

```python
dict_result = api_result.json()
```

### Step 3

```python
dict_result['summary']
```

### Ouput:

```json
{'rating': 4.1,
 'ratings_total': 50,
 'ratings_total_filtered': 11,
 'reviews_total_filtered': 4,
 'reviews_total': 4,
 'rating_breakdown': {'five_star': {'percentage': 73, 'count': 36},
  'four_star': {'percentage': 3, 'count': 1},
  'three_star': {'percentage': 3, 'count': 1},
  'two_star': {'percentage': 0, 'count': 0},
  'one_star': {'percentage': 21, 'count': 10}}}

```

![alt text](./pic/Screenshot%20from%202024-07-16%2015-24-11.png)
