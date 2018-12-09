---
layout: post
title: Smart Recommendation System
comments: true
---

Last week i went for my first 24 Hour's offline hackathon.
This hackathon was organized by the company named Rakuten(who is also official sponsor of Barcelona Football team).
The teams come for this hackathon were selected based upon there idea's which were submitted during Hackerearth or Techgig online hackathon.

so i'm writing about the idea which we have submitted and the part which were implemented during this 1 day hackathon.
So let's start by introducing the idea.

our idea were to create a smart recommendation System which can combine with both Image and Text Search.This implemented Image Search feature was a miniature version of the Amazon's newly implemented Product Image search feature.

![an image alt text]({{ site.baseurl }}/images/2oje7l.gif "Product Image Search")

So, by combining Object Detection & Image segmentation with Hybrid Recommendation we can personalize the search result for each user.

### Pipeline WorkFlow

![an image alt text]({{ site.baseurl }}/images/product_recomend.png "Recommendation Pipeline")

So here User would capture an image of a product in real time and can search for required product in the E-commerce site either by Product Image or it can search with Query regarding what product they want.

in the Backend we First Classify the broad category of product in the image whether it is a Shirt,jeans etc then map the image with available 1000 attributes.

if it is a Query then we first preProcess the query then map the preprocessed query with available 1000 tags/attributes.
in the final step we will recommend 10 matched products based upon transaction history of the user.

So,the Input to our Application is Product Image or Text Query while output is the 10 Recommended Products based upon various attributes.

Link to the Complete [Kaggle Notebook](https://www.kaggle.com/rednivrug/comprehensive-bus-boarding-analysis).

Comment below if you have any query.
