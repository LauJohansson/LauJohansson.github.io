<h1>Hotdog or Not-Hotdog</h1>

<!-- wp:paragraph {"customFontSize":15} -->
<p style="font-size:15px"><em>Author: Lau Johansson<br>16th September 2020<br>Reading time: 5 min.</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>The wait is over... </h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Now you don't have to find out by yourself whether an object is a hotdog or not. The guys from<a href="https://dk.hbonordic.com/"> HBO's</a> <a href="https://en.wikipedia.org/wiki/Silicon_Valley_(TV_series)">Silicon Valley</a> have made an app where you can take a picture of an object - then, it tells you if it is a hotdog or not a hotdog.</p>
<!-- /wp:paragraph -->

[![IMAGE ALT TEXT HERE](https://duet-cdn.vox-cdn.com/thumbor/0x0:2544x1428/750x500/filters:focal(1340x656:1341x657):format(webp)/cdn3.vox-cdn.com/uploads/chorus_asset/file/8518031/jian_yang_hbo_silicon_valley.png)](https://www.youtube.com/watch?v=vIci3C4JkL0)
<!-- wp:heading -->
<h2>What is the point?</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>This seems like a simple problem for us humans. But how simple is it in terms of machine learning? We, at Explorifydata, will try to show how deep learning can solve such a binary classification problem. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Before you close the page down or look for another more interesting post, you could relate the problem into other domains. This could be:</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>Medical industry: Is the patient sick or not?</li><li>Quality assurance: Does a product contain defects?</li><li>Information:  Is an email spam?</li><li>Customer churn: Will the customer stop using your company?</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>The problems above has a common denominator: binary classification problems. Working deep learning and images, like hotdog-images, is called image classification. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Our post will emphasize on how neural networks can perform well in classification problems. This time we do NOT strive to make a "perfect" model. The goal is just to make a model that performs better than blind-guessing. </p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>From Silicon Valley to Explorifydata</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3>The model</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>We have tried to replicate the work of Jian Yang with a deep learning approach. To be able to classify hotdogs / not-hotdogs a Convolutional Neural Network (CNN) has been implemented. It takes a hotdog image and split it into three-layer image representing respectively the blue, red and green colors of the hotdog image. The CNN works by applying small filters on the image which then decompose the image to a smaller scale. Maxpooling is also a technique for decomposing images; a 2x2 filter runs through the image - for every stride it picks out the highest pixel-value.   </p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/cnn_explain.png)

<!-- wp:paragraph -->
<p>At last the decomposed picture is feed to a fully connected layer which represents the data as one vector. At last the network detects whether the image contains a hotdog or a not-hotdog. </p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>The data and augmentation</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>To slightly improve the network performance we've used dataaugmentation. In short, dataaugmentation is a technique for increasing the size of a dataset by e.g. transformation of the existing data. In this blogpost we apply three transformations: rotation, horizontal flipping and centercropping. To imply some randomness in the transformations each of them is done with a probability of 50%. </p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/cnn_explain_augmentation-1.png)

<!-- wp:heading {"level":3} -->
<h3>The results</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Even though we have implemented is a very simple network the model has a accuracy of almost 80%. How can we interpret this result? In general, the number of times the model guessed on hotdog and got it right!</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/cnn_explain_results-1.png)

<!-- wp:paragraph -->
<p>Evaluating a model is actually not that simple. One must also take a big dive into performance evaluation tools such as confusion matrix, precision and F1-score. These terms do not sound exactly exciting as a hotdog app - so this will not be examined here. But! We can look at some of our prediction! Take a look by yourself - did the model detect the hotdogs?</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/hotdog_predictions-1024x328-1.png)

<!-- wp:paragraph -->
<p>As you can see, the model fails to predict some of the images which are obviously not-hotdogs - at least it is obvious for you as a human. The way a neural network "interprets" an image is not always straightforward. Who would have thought that the network will think that the dog with the funny hair (left bottom corner) was a hotdog? </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Can we do better? Here we will refer to a <a href="https://towardsdatascience.com/building-the-hotdog-not-hotdog-classifier-from-hbos-silicon-valley-c0cb2317711f">Towards Data Science Post</a> which explains how using a pretrained <a href="https://en.wikipedia.org/wiki/Inceptionv3">InceptionV3</a> model on hotdog/not-hotdog dataset gave an <strong>accuracy of 96%</strong>! That seems pretty sufficient from our point of view. </p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>What can we learn?</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>The most important take home from this post is: A very simple convolutional neural network can perform with a high accuracy in binary (image) classification problems. To improve the performance of the model, the hotdog-images can be rotated, flipped and cropped. An app that predicts hotdog and not-hotdog can immediately seem silly - but by putting it into perspective with other problem domains - simple deep learning models could be a tool to solve many classification problems. </p>
<!-- /wp:paragraph -->
