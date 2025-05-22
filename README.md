# Brazilian E-commerce Market Analysis

## Project Overview
This project analyzes customer reviews and behaviuor patterns in the Brazilian e-commerce market using the Olist e-commerce platform dataset alongside macroeconomic indicators. This analysis aims to uncover which 
have the greatest impact on customer revirewsrelationships between economic factors and e-commerce behavior in Brazil.

## Motivation and Goals
The Brazilian e-commerce market has experienced significant growth over recent years, becoming one of Latin America's largest digital marketplaces. This project aims to:

- Understand the dynamics of Brazil's e-commerce ecosystem
- Identify correlations between economic indicators and purchasing patterns
- Develop predictive models for sales trends based on economic conditions
- Create actionable insights for businesses operating in the Brazilian market
- Explore regional differences in e-commerce adoption across Brazil

## Data Sources

### Primary Dataset
- **Olist Brazilian E-commerce Dataset**: A comprehensive collection of data from orders made at Olist Store.
- **Source**: [Kaggle - Brazilian E-commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
- **Content**: ~100,000 orders from 2016 to 2018 across multiple marketplaces in Brazil

### Enrichment Data
- **Trading Economics Brazil Indicators**: Macroeconomic indicators for Brazil
- **Source**: [Trading Economics - Brazil Indicators](https://tradingeconomics.com/brazil/indicators)
- **Content**: Economic metrics including inflation rates, consumer confidence, GDP growth, unemployment figures, and interest rates

## Dataset Details

### Olist Dataset Structure
The Olist dataset contains the following key tables:

1. **olist_customers_dataset**: Customer information and location
   - `customer_id`, `customer_unique_id`, `customer_zip_code_prefix`, `customer_city`, `customer_state`

2. **olist_orders_dataset**: Order information including status and timestamps
   - `order_id`, `customer_id`, `order_status`, `order_purchase_timestamp`, `order_approved_at`, `order_delivered_carrier_date`, `order_delivered_customer_date`, `order_estimated_delivery_date`

3. **olist_order_items_dataset**: Items included in orders with pricing
   - `order_id`, `order_item_id`, `product_id`, `seller_id`, `shipping_limit_date`, `price`, `freight_value`

4. **olist_products_dataset**: Product details and categorization
   - `product_id`, `product_category_name`, `product_name_length`, `product_description_length`, `product_photos_qty`, `product_weight_g`, `product_length_cm`, `product_height_cm`, `product_width_cm`

5. **olist_sellers_dataset**: Seller information and location
   - `seller_id`, `seller_zip_code_prefix`, `seller_city`, `seller_state`

6. **olist_geolocation_dataset**: Geographic data for mapping
   - `geolocation_zip_code_prefix`, `geolocation_lat`, `geolocation_lng`, `geolocation_city`, `geolocation_state`

7. **olist_order_payments_dataset**: Payment information
   - `order_id`, `payment_sequential`, `payment_type`, `payment_installments`, `payment_value`

8. **olist_order_reviews_dataset**: Customer reviews
   - `review_id`, `order_id`, `review_score`, `review_comment_title`, `review_comment_message`, `review_creation_date`, `review_answer_timestamp`

9. **product_category_name_translation**: English translation of category names
   - `product_category_name`, `product_category_name_english`

### Data Enhancement Plan
I plan to enhance the Olist dataset (2016-2018) in several ways using Brazilian Economic indicatprs congruent to the period that the Olist data set was collected (2016-2018). I chose this particular enriching data since Between 2000 and 2014, Brazil was in an economic boom. However, the commodity-driven growth proved volatile, leading to The 2014-2016 economic recession, followed by a slow recovery, resulted in a slowdown of the GDP growth in the years before the pandemic. Hence, the purpose of this enrichment is to map the relation of the period of slow recovery in the BRazillian economy with the Olist Brazillian Ecommerce data, which coincides during the same period:

1. **Temporal Economic Context**: Merge the e-commerce transaction data with time-aligned economic indicators from Trading Economics:
   - Inflation rates
   - Unemployment figures
   - Consumer confidence index
   - Interest rates
   - GDP growth
   - Exchange rates

2. **Geographic Enrichment**:
   - Add socioeconomic data for different Brazilian regions
   - Include population density information
   - Incorporate internet penetration rates by region

3. **Calculated Features**:
   - Create seasonality indicators
   - Calculate customer lifetime value
   - Derive price elasticity metrics
   - Develop seller performance indicators

## Project Objectives

### Primary Objectives
1. **Economic Impact Analysis**: Determine how macroeconomic factors affect e-commerce purchasing patterns
2. **Regional Variation Study**: Identify geographic differences in e-commerce behavior across Brazil
3. **Temporal Trends**: Analyze how e-commerce has evolved during the observed period (2016-2018)
4. **Predictive Modeling**: Create models to forecast sales based on economic indicators

### Business Questions to Answer
- How do economic downturns impact different product categories?
- Are certain regions more resistant to economic fluctuations in their e-commerce behavior?
- What is the relationship between consumer confidence and average order value?
- How do interest rates impact payment installment choices?
- Can regional economic disparities explain differences in product preferences?

## Methodology Overview
1. Data preprocessing and integration
2. Exploratory data analysis
3. Feature engineering
4. Statistical analysis of relationships
5. Time series analysis
6. Predictive modeling
7. Visualization and reporting

## Future Work
- Extend the analysis with more recent data
- Incorporate text analysis of product reviews
- Develop interactive dashboards for business intelligence
- Compare Brazilian e-commerce patterns with other Latin American markets

## Contact Information
For questions or collaboration opportunities, please reach out at [your-email@example.com].

## Acknowledgments
- Olist for providing the e-commerce dataset
- Trading Economics for economic indicator data
- Kaggle community for support and inspiration
