# Airbnb Listings & Reviews in Paris

This repository contains a Jupyter Notebook exploring Airbnb listings and reviews in Paris, using a multi-table dataset with 5,652,855 records and 36 fields. The project focuses on understanding pricing patterns, neighborhood differences, host behavior, and long-term trends in the Paris market.

## Dataset Overview

The dataset supports geospatial, time-series, and travel-time analysis.  
It includes multiple related tables covering listings, hosts, and reviews.

### Key Characteristics
- Total records: 5,652,855  
- Total fields: 36  
- Data types: TravelTime, Time Series, Geospatial  
- Structure: Multiple tables (listings, reviews, host metadata)

### Core Fields
- listing_id, listing_name  
- host_id, host_since, host_location  
- host_is_superhost, host_listings_count  
- neighbourhood, city  
- latitude, longitude  
- property_type, room_type  
- accommodates, bedrooms  
- amenities  
- price, minimum_nights, maximum_nights  
- review_scores_* (rating, accuracy, cleanliness, etc.)  
- instant_bookable  

> Note: Prices are in local currency.

## Analysis Objectives

### Objective 1: Data Preparation & QA
- Clean and standardize fields (price, dates, amenities, coordinates)
- Handle missing values and inconsistent entries
- Validate geospatial and neighborhood information
- Ensure the dataset is ready for grouping and visualization

### Objective 2: Preparing Data for Visualization
Three analytical DataFrames are created to explore neighborhood pricing, accommodation capacity, and long-term trends.

- paris_listings_neighbourhood  
  Groups listings by neighbourhood and calculates average price, sorted in ascending order.

- paris_listings_accommodations  
  Filters the dataset to the most expensive neighbourhood identified above.  
  Groups by accommodates and computes average price, sorted in ascending order.

- paris_listings_over_time  
  Extracts the year from host_since.  
  Computes:
  - Number of new hosts per year
  - Average listing price per year

### Objective 3: Data Visualization
- Horizontal bar chart: Average rent price by neighbourhood  
  Highlights the most and least expensive areas in Paris.

- Horizontal bar chart: Average price by accommodates in the most expensive neighbourhood  
  Shows how pricing scales with guest capacity.

- Line charts: New hosts per year & Average price per year  
  Explores:
  - What happened to new hosts in 2015
  - Whether average price was impacted

- Dual-axis line chart  
  Combines both time series—new hosts and average price—into one visualization.
