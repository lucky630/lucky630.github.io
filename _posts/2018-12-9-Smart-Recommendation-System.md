---
layout: post
title: Smart Recommendation System
excerpt: Shop Smatter
permalink: /Smart-Recommendation-System
publish: true
comments: true
images:
  - url: /images/2oje7l.gif
---

<link href="https://afeld.github.io/emoji-css/emoji.css" rel="stylesheet">
<h2><span style="text-decoration: underline;"><strong>Introduction</strong></span></h2>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Last week i went for my first 24 Hour's offline hackathon.
This hackathon was organized by the company named Rakuten(who is also official sponsor of Barcelona Football team).</p>
<p>
The teams come for this hackathon were selected based upon there idea's which were submitted during Hackerearth or Techgig online hackathon.
</p>

so i'm writing about the idea which we have submitted and the part which were implemented during this 1 day hackathon.
So let's start by introducing the idea.

our idea were to create a smart recommendation System which can combine with both Image and Text Search.This implemented Image Search feature was a miniature version of the Amazon's newly implemented Product Image search feature.

![an image alt text]({{ site.baseurl }}/images/2oje7l.gif "Product Image Search")

So, by combining Object Detection & Image segmentation with Hybrid Recommendation we can personalize the search result for each user.

<h2><span style="text-decoration: underline;"><strong>Pipeline WorkFlow</strong></span></h2>

![an image alt text]({{ site.baseurl }}/images/product_recomend.png "Recommendation Pipeline")

So here User would capture an image of a product in real time and can search for required product in the E-commerce site either by Product Image or it can search with Query regarding what product they want.

in the Backend we First Classify the broad category of product in the image whether it is a Shirt,jeans etc then map the image with available 1000 attributes.

if it is a Query then we first preProcess the query then map the preprocessed query with available 1000 tags/attributes.
in the final step we will recommend 10 matched products based upon transaction history of the user.

So,the Input to our Application is Product Image or Text Query while output is the 10 Recommended Products based upon various attributes.

<h2><span style="text-decoration: underline;"><strong>Dataset</strong></span></h2>

Deep learning model were trained on DeepFashion Category and Attribute Prediction Dataset.

This is a very rich dataset having both bounding boxes and category label information for the images.

This Dataset having 300k images which were categorized into 47 categories and those categories were further divided into 1000 different attributes.

link to [Dataset](http://mmlab.ie.cuhk.edu.hk/projects/DeepFashion.html)
.First we have created training,testing and validation sets.

<h2><span style="text-decoration: underline;"><strong>Model Training</strong></span></h2>

We have used transfer learning to fine tuned the last 12 layers of Resnet50 model.
This model having two branches.

The First part is for image to category where loss was 'categorical_crossentropy' & accuracy were 'top_k_categorical_accuracy'.

Second branch was for image to bounding boxes where loss & accuracy both calculated in 'Rmse'.

Finally used the tfidfvectorizer & countvectorizer to do Text Similarity for getting the similar context products.

<h2><span style="text-decoration: underline;"><strong>Tech Stack</strong></span></h2>

we have designed two frontends for this application first one is a Android App which were part of the final submission and second one is a web based console.

backend was running on a flask web server and models were trained on Google colab free Gpu servers.

<h2><span style="text-decoration: underline;"><strong>Experience</strong></span></h2>

Me and my friend done overnight train journey from chennai to bangalore to attend this hackathon.

![an image alt text]({{ site.baseurl }}/images/smart_recommend/team.JPG "Team Member")

Link to the Complete [Kaggle Notebook](https://www.kaggle.com/rednivrug/comprehensive-bus-boarding-analysis).

Comment below if you have any query.
