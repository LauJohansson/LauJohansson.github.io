---
layout: post
title: Exploring Danish Driving Behavior
date: 2020-07-01 21:49
author: jonassoebro
comments: true
categories: [Ikke kategoriseret]
---
<!-- wp:paragraph -->
<p> <em>Authors: Jonas Christophersen, Alessandro Pasta &amp; Alex Incerti<br>1st July 2020<br>Read time: 17 minutes</em> </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"customFontSize":20,"fontFamily":""} -->
<p style="font-size:20px"><em>“The one thing that unites all human beings, regardless of age, gender, religion, economic status, or ethnic background, is that, deep down inside, we all believe that we are above-average drivers.” - Dave Barry</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Driving has a considerable impact on our lives and the landscape of our cities. Our behavior when driving is indeed a fascinating topic. In this report, we will investigate:</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>What percentage of Danish drivers exceed the speed limit?</li><li>Does driving behavior change across municipalities?</li><li>Do socioeconomic factors explain differences in driving behavior?</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Before we start, here is a video summarizing our project idea:</p>
<!-- /wp:paragraph -->

<!-- wp:html -->
<center><iframe width="560" height="315" src="https://www.youtube.com/embed/LNPDZ1TbVPU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe></center>
<!-- /wp:html -->

<!-- wp:heading {"level":4} -->
<h4><strong>Driving behavior in the Danish municipalities</strong></h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>On average, in Denmark, people drive at 50km/h, and 25% of cars drive above the speed limit. However, these numbers vary largely from municipality to municipality.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The map below displays the driving behavior in the Danish municipalities. Using the selector-bar you can choose which driving indicator you want to investigate. The color intensity denotes the value for the particular municipality, and if you mouse over a specific municipality you can see the exact numbers.</p>
<!-- /wp:paragraph -->

<!-- wp:html -->
<div><iframe src="https://explorifydata.com/wp-content/uploads/2020/05/trafficmap.html" style="border:0px #ffffff none;" name="traffic_map" scrolling="no" frameborder="1" height="700px" width="100%" allowfullscreen=""></iframe></div>
<!-- /wp:html -->

<!-- wp:paragraph -->
<p><strong>Observation 1</strong>: <em>People drive slower in urban areas. </em>Municipalities like Copenhagen, Odense, Aalborg exhibit a lower average speed, probably due to lower speed limits and more traffic.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Observation 2</strong>: <em>Municipalities vary largely in the percentage of people driving above the speed limit</em>. Ringkøbing-Skjern has a high percentage of speeders (44%), Copenhagen (10%), and Frederiksberg (5%) the fewest amount of speeders.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4><strong>Socioeconomic factors</strong></h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Why do people exhibit such a variation in their driving behavior across municipalities? Do socioeconomic factors also vary across municipalities?</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The map below displays some socioeconomic factors in the Danish municipalities.</p>
<!-- /wp:paragraph -->

<!-- wp:html -->
<div><iframe src="https://explorifydata.com/wp-content/uploads/2020/05/socioindex2.html" style="border:0px #ffffff none;" name="socio_map" scrolling="no" frameborder="1" height="700px" width="100%" allowfullscreen=""></iframe></div>
<!-- /wp:html -->

<!-- wp:paragraph -->
<p><strong>Observation 1</strong>: <em>People tend to commute from the city to nearby areas.</em> Municipalities close to the main cities (Copenhagen, Århus, Odense) have the highest percentage of ingoing commuters.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Observation 2</strong>: <em>Adults with higher education tend to live in the largest cities. </em>Municipalities like Copenhagen and Århus have a higher percentage of adults with higher education. It is interesting to notice that, near Copenhagen, there is a tendency for higher educated people to live in the northern municipalities, compared to the western ones.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4><strong>The relation between driving behavior and socioeconomic factors</strong></h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Having seen that the driving behavior differs throughout the different municipalities and that socioeconomic factors do too, we investigated whether there is a correlation between the two. For instance, it would be interesting to investigate:</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>Does the percentage of drivers over the speed limit decrease in densely populated municipalities?</li><li>Does the percentage of drivers over the speed limit decrease in municipalities with a higher number of commuters?</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>The visualization below enables the exploration of relationships between the percentage of people driving over the speed limit and various socioeconomic factors. Each dot corresponds to a municipality and the size of the dot is proportional to the number of inhabitants.</p>
<!-- /wp:paragraph -->

<!-- wp:html -->
<div><iframe src="https://explorifydata.com/wp-content/uploads/2020/05/corrplot2.html" style="border:0px #ffffff none;" name="corrplot" scrolling="no" frameborder="1" height="550px" width="100%" allowfullscreen=""></iframe></div>
<!-- /wp:html -->

<!-- wp:group -->
<div class="wp-block-group"><!-- wp:group -->
<div class="wp-block-group"></div>
<!-- /wp:group -->

<!-- wp:paragraph -->
<p><strong>Observation 1</strong>: <em>Municipalities with many elderly (65 years +) have an increased amount of speed limit violations.</em> There seems to be a positive correlation between the percentage of elderly and the percentage of speed violations. Do the elderly tend to drive more often over the speed limit? Maybe, but by exploring the points in the scatter plot, another interesting aspect appears. It seems like the municipalities presenting the high percentage of elderly are mostly rural areas (countryside of Jutland, Lolland, Bornholm), whereas cities such as Copenhagen, Aarhus or Odense, along with the municipalities in the Copenhagen areas show a lower percentage of elderly and a lower percentage of speed violations as well. The correlation could thus be due to the type of municipalities (hence type of roads, amount of traffic, amount of police checks), which is then reflected in the percentage of elderly.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Observation 2</strong>: <em>Commuting is negatively associated with speed limit violations.</em> Municipalities with high percentages of ingoing commuters, such as Frederiksberg, Rødovre, Herlev, tend to have a lower percentage of people driving above the speed limit, and vice versa.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4><strong>Predicting speed limit violations based on socioeconomic factors</strong></h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>How is a change in the socioeconomic factors associated with a change in the speed limit violations?&nbsp;To answer this, we trained a mathematical (linear regression) model using the socioeconomic factors. We let the model decide which factors were the most significant for the prediction and got the following coefficients:</p>
<!-- /wp:paragraph -->

<!-- wp:table -->
<figure class="wp-block-table"><table><thead><tr><th>Variable</th><th>Coefficient</th></tr></thead><tbody><tr><td>Intercept</td><td>119</td></tr><tr><td>Percentage of adults (18/66 years)</td><td>-0.957</td></tr><tr><td>Percentage of elderly (65+ years)</td><td>-0.0448</td></tr><tr><td>Percentage of ingoing commuters</td><td>-0.134</td></tr><tr><td>Percentage of adults with higher education</td><td>-0.300</td></tr><tr><td>Percentage of unemployed</td><td>-3.10</td></tr></tbody></table><figcaption>Coefficients for Linear Regression Model</figcaption></figure>
<!-- /wp:table -->

<!-- wp:paragraph -->
<p>An interactive prediction tool is provided below. The slider-values are restricted to values represented in the data, as to avoid extrapolation.</p>
<!-- /wp:paragraph -->

<!-- wp:html -->
<div><iframe src="https://explorifydata.com/wp-content/uploads/2020/05/barchart2-3.html" style="border:0px #ffffff none;" name="barchart" scrolling="no" frameborder="1" height="500px" width="100%" allowfullscreen=""></iframe></div>
<!-- /wp:html -->

<!-- wp:paragraph -->
<p><strong>Observation 1</strong>: <em>A 20% increase in the percentage of commuters causes a 2.7% decrease in the percentage of speeders</em>. Commuters usually drive during peak hours, causing traffic congestions. When stuck in traffic, speed limit violations are less likely to occur. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Observation 2</strong>: <em>A 20% increase in the percentage of adults with higher education causes a 6% decrease in the percentage of speeders.</em> It is hard to say if this is because highly educated drivers tend to respect the speed limits more or because they tend to live in urban areas (as seen in previous visualizations) which are less prone to speed limit violations.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>It should be noted that the <em>R<sup>2</sup></em> value is 0.48 indicating that the model is not great but still capable of explaining around half of the variance in the data.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4><strong>Predicting the missing municipalities</strong></h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>In the traffic dataset that we have been working with, not all municipalities had enough observations for us to include them in our analysis. Some municipalities are therefore missing in the driving behavior map previously shown. To alleviate this, the linear regression model is used to estimate the percentage of speed limit violations in those municipalities given their socioeconomic factors. Press the <em>Start Prediction </em>to apply the model.</p>
<!-- /wp:paragraph -->

<!-- wp:html -->
<div><iframe src="https://explorifydata.com/wp-content/uploads/2020/05/predictmunicipality.html" style="border:0px #ffffff none;" name="predict_municipality" scrolling="no" frameborder="1" height="700px" width="100%" allowfullscreen=""></iframe></div>
<!-- /wp:html -->

<!-- wp:paragraph -->
<p>As seen, all Danish municipalities now have their value (real or predicted).</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4><strong>Percentage over speed limit predictions for Danish neighborhoods</strong></h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>As a final added bonus we would like to show you one more thing. Since the driving behavior might vary within each municipality it would be interesting to have a prediction model of the percentage of speed limit violations on a neighborhood level.  And that's why we've used a K-Nearest-Neighbor algorithm to predict how driving behavior is across Danish neighborhoods. The visualization is seen below.</p>
<!-- /wp:paragraph --></div>
<!-- /wp:group -->

<!-- wp:html -->
<div><iframe src="https://explorifydata.com/wp-content/uploads/2020/05/knnplot2.html" style="border:0px #ffffff none;" name="knn_prediction" scrolling="no" frameborder="1" height="700px" width="100%" allowfullscreen=""></iframe></div>
<!-- /wp:html -->

<!-- wp:paragraph -->
<p>It is interesting to see how the color intensities fall around major cities. People really behave in the city! Try finding your own neighborhood and see what it's like.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>What a ride! Thank you so much for checking our project out.</p>
<!-- /wp:paragraph -->

<!-- wp:jetpack/markdown {"source":"You can find the behind-the-scenes jupyter explainer notebook [here](https://nbviewer.jupyter.org/github/IncioMan/socialdata/blob/master/FinalProject/TrafficDataProject.ipynb)."} -->
<div class="wp-block-jetpack-markdown"><p>You can find the behind-the-scenes jupyter explainer notebook <a href="https://nbviewer.jupyter.org/github/IncioMan/socialdata/blob/master/FinalProject/TrafficDataProject.ipynb">here</a>.</p>
</div>
<!-- /wp:jetpack/markdown -->

<!-- wp:media-text -->
<div class="wp-block-media-text alignwide is-stacked-on-mobile"><figure class="wp-block-media-text__media"></figure><div class="wp-block-media-text__content"><!-- wp:paragraph {"placeholder":"Content…","fontSize":"large"} -->
<p class="has-large-font-size"></p>
<!-- /wp:paragraph --></div></div>
<!-- /wp:media-text -->
