---
layout: post
title: "Danish politicians - Does Twitter reflect real politics?"
---

# Danish politicians - Does Twitter reflect real politics?

<!-- wp:paragraph -->
<p> <em>Authors: Frederik Kromann Hansen, Lau Johansson &amp; Christian Petersen<br>4th March 2020<br>Read time: 17 minutes</em> </p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Introduction</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>In Denmark, the legislative power is in the hands of the elected politicians. These Danish politicians are therefore of great importance for how Denmark develops as a country. The politicians meet at the Danish Parliament to debate bills, and these meetings are publicly available. Outside the Parliament, the Danish politicians also figure on social media – there among Twitter. This platform allows the politicians to directly communicate with both the public and other politicians. It is interesting to examine how politicians are connected on Twitter, and how these connections correspond to the structure of the political system in Denmark. At the same time, it is interesting to analyze the topics of the politicians’ tweets, to shed light on whether the politicians’ opinions on social media correspond to what the parties debate in the Parliament.</p>
<!-- /wp:paragraph -->


![](https://LauJohansson.github.io/images/new_structure_gif_v5.gif)

<!-- wp:heading -->
<h2>Data Collection</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>To attempt to satisfy the curiosity expressed in the introduction, we will need data from three different kinds of sources. Firstly, some information on who the politicians are and what parties and regions they belong to. Secondly, some data on social interactions between the politicians as we want to investigate the network spanned by these and the contents of the network. Thirdly, some data on their official business, to investigate if it aligns with what they express to the public through their most easily accessible public statements on Twitter.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Twitter Data</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>On <a href="https://filip.journet.sdu.dk/twitter/politikere/">twitterpolitikere.dk</a>, Twitter profiles of 650 danish politicians have been collected (25 November 2020). The publishers of the data are journalists Ernst Poulsen and Filip Walberg in collaboration with the Center for Journalism. The website is continuously updated by the publishers, with data from Twitter’s open APIs. Danish politicians can choose to write to the publishers to be removed from the list. Each person’s profile is assessed manually by the authors before people are included on the lists. There is no information on the process of assessing the profiles. If interested, this <a href="https://twitter.com/ernstpoulsen/lists">link</a> has more lists with overviews of people in different industries: Politicians, journalists and people in managerial positions, etc.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>From the list of Danish politicians’ Twitter usernames, each of the profiles is going to represent a node in a graph that is going to be called: “Danish Politicians’ Twitter Network”. In order to make a network that connects the Danish politicians, this project uses tweets from Twitter. Initially, a developer account for twitter has been created. Tweets can then be assessed through Twitter’s API on <a href="https://developer.twitter.com/en">https://developer.twitter.com/en</a>. <a href="https://help.twitter.com/en/using-twitter/types-of-tweets">Tweets</a> are messages posted to Twitter containing text, photos, a GIF, and/or video. Both sender and receivers of tweets can see all tweets on a Home Timeline – a timeline that is different for each person – depending on who you are following.</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/sofiecn_tweet_28oct.png)

<!-- wp:paragraph -->
<p>This project is especially interested in <a href="https://help.twitter.com/en/using-twitter/types-of-tweets">mentions</a> because mentions are tweets that contain other profiles’ Twitter usernames. A mention in a tweet is preceded by the “@” symbol – which makes it possible to examine the mentions between Danish politicians. These mentions are the edges between politicians in the network.</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/network.png)

<!-- wp:heading {"level":3} -->
<h3>Political parties</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>In most cases, politicians are members of some party, sharing a general ideology that they agree with. Therefore, and because politicians might communicate equally as much in the role of a representative of their party, as they do for themselves personally, it is also interesting to investigate the network spanned by parties. For example if Mette Frederiksen mentioned Lars Løkke, then that would count as Social Demokratiet mentioning Venstre.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Since the parties were not on <a href="https://filip.journet.sdu.dk/twitter/politikere/">twitterpolitikere.dk</a>, the Parliament’s official website, <a href="http://ft.dk/">ft.dk</a> was scraped to achieve this extra data. Additionally, to get information on the politicians not in Parliament a multitude of places was scraped. The journey began looking at the five regions in Denmark, as each region had its own council with elected members. Doing this, inspired the addition of a region attribute to the politicians, in the project nothing was made of this but it is available for future work. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Examining the data, hundreds of politicians were still missing a party and a region, after looking up some of these politicians, it was clear that the large majority of the Twitter profiles belonged to politicians that were council members of their local municipalities. Unfortunately there are 98 municipalities in Denmark, so scraping all of these wasn’t feasible. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>In the end, about half of the 650 politicians were assigned a party and a region!</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Parliament Meetings</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>The most official business of the politicians must be what they say in the Parliament. The data related to the meetings in the Parliament is collected following the guide on its homepage <a href="https://www.ft.dk/-/media/sites/ft/pdf/dokumenter/aabne-data/oda-browser_brugervejledning.ashx">here</a>.<br>Transcripts from all meetings going back to 2009 are available for download in XML format using a login described in the guide and some specific FTP software. Because it is interesting to compare topics from Twitter with topics in the Danish Parliament, only the transcripts from the same period as the tweets are used for further analysis. 71% of the available tweets are posted in 2018 and after.<br><br>The years in the Danish Parliament do not follow the calendar year, as they start and end the first Tuesday of October. So, the meetings from 2017 are actually from October 2017 to October 2018. The data from 2017 are kept for the purpose of having slightly more data and because it is assumed that topics vary little enough for it to still be relevant.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>In total 395 meeting transcripts amounting to 218Mb of data has been downloaded and parsed for analysis.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>It is not stated how the transcripts are made, however, they are proofread before publication.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Network analysis</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3>Preliminary statistics</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>The network contains 561 Danish politicians who have a Twitter profile, but since some of the profiles do not interact with anyone, 555 are left. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The maximum distance between any two politicians in the network is 6, which actually relates to an interesting phenomenon called <a href="http://networksciencebook.com/chapter/3#small-worlds">“Six degrees of separation”</a>. The phenomenon states that between any two individuals on Earth, there’s a path of at most six acquaintances between them. However, the average distance between any Danish politician on Twitter is only 2.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The network can be visualized by coloring the nodes according to the associated party. By further having the distance between nodes relate to the similarity between them it gives an idea of potential polarization and groups within politics. Finally, the size of the nodes determine the “popularity” in the sense that bigger nodes means more mentions suggesting higher popularity. The network is shown below with these traits. Notice how the biggest node is the black one in the middle representing the Government’s official profile, regeringDK. From this it can be seen that this profile on Twitter is mentioned and/or mentions the most other profiles.</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/download-1-1024x506-1.png)

<!-- wp:paragraph -->
<p>The top 5 most central profiles on Twitter, the ones who connect to the most of the other politicians are: the Government (regeringDK), Lars Løkke Rasmussen (larsloekke), Jakob Ellemann (JakobElleman), Kristian Jensen (Kristian_Jensen) and Morten Østergaard (oestergaard). Surprisingly, the current Prime Minister Mette Frederiksen, among others, does not have Twitter.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3> Is it a random network?</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>This project aims to build models that reproduce the properties of real networks. To examine whether the graph reproduces a real network or if it is just a random network, the degree distribution of a random network is compared to this network. One thing influencing the structure of a network, is the probability of nodes linking together. For this network, the probability is 6.6 % meaning that there is a 6.6% chance that two randomly chosen nodes are connected.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>There are two extreme cases. If p=0, there’s zero probability that any node links to another – all nodes are isolated. If p=1, there’s 100% probability that any node links to another – the graph is complete, every node links to all other nodes. This network is in the so-called “connected regime”, which means that the Twitter network will emerge to a giant connected component (GCC), which absorbs all nodes and components. To further analyze the Twitter network, the GCC is extracted and it contains 555 politicians – that’s almost everyone!</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The degree of a random network follows a poisson distribution. Therefore to assess if the Twitter network is completely random or follows some general rules the degree is compared to that of a random network.</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/power_law_plot-1.png)

<!-- wp:paragraph -->
<p>To yet examine the randomness, the above plots can be inspected. On the log-log plot, the degree distribution of the GCC follows the power-law and therefore the GCC of the Twitter network is not random. According to <a href="http://networksciencebook.com/chapter/4">Network Science Book – section 4.2</a> it is even a scale-free network.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>A property of a scale-free network is the nature of preferential attachment. This affects the degree of the largest node, so new politicians joining Danish politics (and Twitter) will prefer to connect to some of the hubs in the network. One or a few large hubs connect to most of the notes, which can represent some of the most influential Twitter profiles. Or, at least be a great potential source of bringing a message.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The graph is in the connected regime, and the GCC of the Twitter network absorbs all nodes. The properties of the politician Twitter network are therefore consistent with some of the properties of other real-world networks!</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>House of Cards - the Danish version</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>If a politician should sow the seed of a political agenda among other politicians and the public who follows the politicians - who should he or she address?</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>This question reminds one of the plot from&nbsp;<a rel="noreferrer noopener" href="https://en.wikipedia.org/wiki/House_of_Cards_(American_TV_series)" target="_blank">House of Cards</a>:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>"<em>Congressman Frank Underwood (Kevin Spacey), a Democrat from South Carolina's 5th congressional district and House Majority Whip, and his equally ambitious wife Claire Underwood (Robin Wright). Frank is passed over for appointment as Secretary of State, so he initiates an elaborate plan to attain power, aided by Claire. The series deals with themes of ruthless pragmatism, manipulation, betrayal, and power.</em>" - Wikipedia</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>This story is possibly more dramatized than the real life of Danish politicians. Nevertheless, this case is called "House of Cards - the Danish version". If a few politicians on Twitter connect to many others, then these could potentially have a great influence on the formation of public opinion - and maybe also the opinion of other politicians.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>We have chosen a totally random Danish politician: <a href="https://twitter.com/StemClausson">StemClausson</a> (Jesper Clausson). On Twitter, he writes that he is a regional council member for Socialdemokratiet at Region Hovedstaden. He is now the main character for the case called "House of Cards - the Danish version". </p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/StemClausson_image-2.jpg)

<!-- wp:paragraph -->
<p>The social network graph representing all the Danish politicians on Twitter can help identify the connection between Jesper Clausson and all the other Danish politicians. In the graph below Jesper Clausson is the <span style="color:#13cc22" class="has-inline-color"><strong>green</strong></span> node. The politicians that he interacts directly with (mentions others or gets mentioned) are <span style="color:#e70a0e" class="has-inline-color">"1 step away"</span>. Politicians, who do not interact directly with him, but with the 1-step-away'ers, are <span style="color:#1279BE" class="has-inline-color">"2 steps away"</span>. Then you got the point with the <span style="color:#a815e2" class="has-inline-color">"3 steps away"</span> and <span style="color:#e4a908" class="has-inline-color">"4 steps away"</span>...</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/house_of_cards_gif2.gif)


<!-- wp:paragraph -->
<p>As you notice, many nodes are 2 steps away from Jesper Clausson, which is then consistent with the previously stated fact - that most politicians are 2 steps away from each other. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>One of the most central politicians in the network is Lars Løkke Rasmussen (<a href="https://twitter.com/larsloekke">larsloekke</a>) with connections to 213 other politicians on Twitter. According to Lars Løkke Rasmussen's profile, he is a member of The Danish Parliament, former chairman of the party "Venstre" and former Prime Minister. There is no doubt why he is central in the social network of Danish politicians. </p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/lars_billede.jpg)



<!-- wp:paragraph -->
<p>If Jesper should influence as central a person as Mr. Rasmussen, what should he then do? What if Jesper can not talk directly to Rasmussen, but is able to talk to some of the politicians closer to him. Who should he talk to directly? By finding the politicians which Lars Løkke connects to, we can identify the politicians he interacts with and thereby those who are more likely to influence him than Jesper Clausson. </p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/all_images_to_lars.jpg)

<em>Politicians that Lars Løkke Rasmussen connects with. From the top centre and clockwise around: Søren Pape Poulsen, Rasmus Jarlov, Louise Elholm, Bjørn Brandenborg, regeringDK, Statsmin, Frank Jensen, Rasmus Nordqvist, Jesper Petersen, Mai Mercado, Jan E. Jørgensen, Rasmus Stoklund, Jakob Ellemann and Kristian Thulesen Dahl.</em>

<!-- wp:paragraph -->
<p>Not surprisingly, a lot of the politicians that Lars interacts directly with on Twitter, are members of the Parliament. He also interacts with the Twitter-profile of the Prime Minister's Office and the official profile of the Danish government. Several of the politicians "closer" to Lars is from the party "Venstre", but among others are also "Det Konservative Folkeparti", "Socialdemokratiet" and "Dansk Folkeparti". So Jesper Clausson has around two handfuls of politicians to go directly to, if Lars Løkke is unavailable. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>What if Jesper Clausson should hope to have a more indirect influence? He does not necessarily want to go directly to all the members of the Danish Parliament. Maybe he does not know any of them personally or professionally - at least he does not interact with them on Twitter. In network theory, there's a term called "Shortest Path", which is the shortest path between two nodes through the graph. This method can help find the people making up the minimum number of interactions between Jesper Clausson and Lars Løkke Rasmussen. What is important to keep in mind is, that we need to find the shortest path FROM larsloekke TO StemClausson, since the network is directed, meaning that there is a difference between if Lars tags someone or someone tags Lars. We need to look at who Lars Løkke mentions on Twitter, then, who do these mentions, and who do these mention etc... The next House-of-Cards'ish question is: "Who should StemClausson talk to if words should spread through the shortest path form Jesper to Lars?"</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/way_to_lars.jpg)
<em>The path shortest path from StemClausson to larsloekke: Jesper Clausson (StemClausson) -&gt; Marianne Frederiksen (mariannefrede20) -&gt; Daniel Panduro (Danielpanduro) -&gt;  Jakob Ellemann (JakobEllemann) -&gt; Lars Løkke Rasmussen (larsloekke).</em>


<!-- wp:paragraph -->
<p>StemClausson interacts with marinannefrede20 on Twitter. <a href="https://www.regionh.dk/politik/politiske-udvalg-og-fora/regionsraadet/Sider/Medlemmer_af_regionsraadet_2018-2021.aspx">Regionh.dk</a> informs that both StemClausson and marianne20 are members of the Regional Board. mariannefrede20 is member of the party "Enhedslisten", a party, who also Danielpanduro is a member of. marinanne20 and Danielpanduro also interact on Twitter. He is among other titles <a href="https://org.enhedslisten.dk/kontakt/Frederiksberg">municipal board member of Frederiksberg</a>.  JakobEllemann is <a href="http://Medlem af Folketinget">member of the parliament</a>  and interacts with DanielPanduro on twitter. At the same time JakobElleman is also of the party "Venstre" - the party where larsloekke is member too.  Now we've found the shortest path from StemClausson to larsloekke. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The mapping of the shortest path was not necessarily easy to identify by browsing through Twitter. This insight shows how network theory can model complex social networks. If you should find the shortest path from Jesper Clausson to Lars Løkke Rasmussen how would you do it? With 555 politicians connecting with each other there's a lot of possible paths to asses.  </p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Text analysis</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3>Preliminary statistics</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>For the text analysis of Twitter data 83000 tweets has been collected using <a href="https://developer.twitter.com/en">Twitter's API</a>. The average length of the tweets is 22 words.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>   </p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/tweet_length_hist.png)

<!-- wp:paragraph -->
<p>For 312 of the 555 politicians, their last 200 tweets has been downloadet. If a politician has less than 200 tweets overall though time, all his/hers tweets are then downloadet. 25% of the politicians has 20 or less tweets. It should be kept in mind that there may be a time lag between tweets across politicians'.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Meetings at the Parliament</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Speech in the Danish Parliament is much more formal than it is on Twitter. Therefore, it is no surprise that the average sentiment for all parties is positive as shown in the bar chart below. They often start their speech by being appreciative towards the one posing the question as well as the moderator for receiving the word. Also, they often say that they understand the cause of the question or the like, which adds to a positive sentiment score as well. On the other hand, they primarily discuss disagreements on current issues, contributing to the negative side.</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/mean_sentiment.png)

<!-- wp:paragraph -->
<p>Notice that Nye Borgerlige, <a href="https://nyeborgerlige.dk/derfor-bliver-vi-kaldt-racister-og-fremmedhadere/">infamous for being xenofobic</a>, has the lowest average sentiment. One should also keep in mind, that one can choose to focus on negative aspects of a topic and another on the positive ones and thereby have different sentiments in the same conversation.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>So in relation to the above, it is important to be aware of how the sentiments are calculated as it is very simple. A lot of words in a range of different languages are given a value indicating the sentiment. In the package that we have used, the range is between -6 and 6 for each word. The total sentiment of a long speech or a tweet is then simply the sum of sentiments from all the words. To exemplify this, take a look at the below quote from the most negative speech in Parliament, made by Karina Adsbøl from Dansk Folkeparti.</p>
<!-- /wp:paragraph -->

<!-- wp:quote {"align":"center"} -->
<blockquote class="wp-block-quote has-text-align-center"><p><em>“Tak for det. Og I får æren af at høre ligestillingsordføreren i dag. At udøve vold er fuldstændig uacceptabelt – og det gælder alle former for vold. Lev Uden Vold har beskrevet flere voldsformer, og det er fysisk vold, psykisk vold, stalking, seksuel vold, materiel vold, økonomisk vold og digital vold. Den fysiske vold er den mest velkendte form for vold og er ofte kendetegnet ved slag, spark, skub, angreb med kniv eller kvælningsforsøg, som påfører den udsatte fysisk smerte og skade(...)”</em></p><cite>Karina Adsbøl, Dansk Folkeparti</cite></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>Notice how she uses the word <strong>'vold',</strong> which is Danish for <strong>violence</strong>, a lot. Each time the sentiment is decremented by 3 as it is considered a very negative word.<strong> This snippet of the text has a sentiment of</strong> <strong><span style="color:#a30013" class="has-inline-color">-36</span> </strong>and yet to the reader who understands Danish it leaves the impression of a more or less objective description of violence. This is important to be aware of when assessing the sentiments across people and parties, such that one does not jump to the conclusion that Karina Adsbøl is an angry person who scolds people or objects to everything. It may very well be that the topic of discussion is merely a negative one such as violence.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Cross-party sentiments</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>In order to examine cross party relationships on Twitter, each tweet was examined in terms of which party the tweet belonged to, and which party it mentioned. Then a sentiment score was given for each tweet. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>In the above table, an overview of the inter-party relationships are given. On the positive side, results are quite mixed and no apparent pattern can be found. However, on the most negative parties, the results indicated the most of the parties tweeted with negative sentiment towards the Government profiles and Nye Borgerlige profiles. For those that critisize the government profiles, it’s indicative of criticism towards certain decisions made. The data shows that the parties; <em>Dansk Folkeparti</em>, <em>Alternativet</em>, and those outside parliament disagree the most with the government. In Danish politics, the “red bloc” is in control right now, and these parties, are either in “blue bloc”, “green bloc” or no bloc at all, supporting this theory.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let’s also look at the overall sentiment per party, so without considering the mentions.</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/box.png)

<!-- wp:paragraph -->
<p>We see that every party has a median score of 0 or above. Furthermore, the Government, Venstre, and Det Konservative Folkeparti, seem to have a smaller variance in the sentiment of their tweets.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Furthermore, it can be seen that Nye Borgerlige, Alternative and Inuit Ataqatigiit have far fewer outliers when compared to the rest, this could be a result of fewer tweets but could also suggest less varying opinions. Lastly look at the outliers, excluding the UNKNOWNs the most negative tweet comes from Socialistisk Folkeparti and the most positive comes from Socialdemokratiet.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Lastly, a network could be generated where edge colors represent the mean sentiment between the parties</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/friendship-1024x514-1.png)

<!-- wp:coblocks/accordion -->
<div class="wp-block-coblocks-accordion"><!-- wp:coblocks/accordion-item {"title":"Click here to see table with sentiment scoring between the parties"} -->
<div class="wp-block-coblocks-accordion-item"><details><summary class="wp-block-coblocks-accordion-item__title">Click here to see table with sentiment scoring between the parties</summary><div class="wp-block-coblocks-accordion-item__content"><!-- wp:table -->
<figure class="wp-block-table"><table><thead><tr><th>Party</th><th>Highest scoring party: sentiment</th><th>Lowest scoring party: sentiment</th></tr></thead><tbody><tr><td>Socialdemokratiet</td><td>Alternativet: <strong>2.04</strong></td><td>Inuit Ataqatigiit: <strong>0</strong>*</td></tr><tr><td>Venstre</td><td>Radikale Venstre: <strong>2.06</strong></td><td>Inuit Ataqatigiit: <strong>0</strong>*</td></tr><tr><td>Det Konservative Folkeparti</td><td>Venstre: <strong>1.59</strong></td><td>Nye Borgerlige: <strong>-1.0*</strong></td></tr><tr><td>Radikale Venstre</td><td>Inuit Ataqatigiit: <strong>8.0</strong>*</td><td>Nye Borgerlige: <strong>-0.66</strong></td></tr><tr><td>Enhedslisten</td><td>Dansk Folkeparti: <strong>1.17</strong></td><td>Nye Borgerlige: <strong>-1.6</strong>*</td></tr><tr><td>Inuit Ataqatigiit</td><td>Enhedslisten: <strong>3.5</strong>*</td><td>Socialdemokratiet: <strong>-4.0</strong>*</td></tr><tr><td>Dansk Folkeparti</td><td>Det Konservative Folkeparti: <strong>1.37</strong></td><td>Government: <strong>-0.61</strong></td></tr><tr><td>Uden for folketingsgrupperne</td><td>Nye Borgerlige: <strong>3.0</strong>*</td><td>Government: <strong>-0.33</strong></td></tr><tr><td>Nye Borgerlige</td><td>Venstre: <strong>1.37</strong></td><td>Socialistisk Folkeparti: <strong>-2.33</strong></td></tr><tr><td>Government</td><td>Socialistisk Folkeparti: <strong>1.67</strong></td><td>Enhedslisten: <strong>-0.5</strong>*</td></tr><tr><td>Socialistisk Folkeparti</td><td>UNKNOWN: <strong>1.21**</strong></td><td>Nye Borgerlige:<strong> -0.86</strong></td></tr><tr><td>Alternativet</td><td>Radikale Venstre: <strong>3.33</strong></td><td>Government: <strong>-0.097</strong></td></tr><tr><td>Liberal Alliance</td><td>Radikale Venstre <strong>1.45</strong></td><td>Uden for folketingsgrupperne: <strong>-1.33</strong></td></tr></tbody></table><figcaption>* low amount of tweets so might be misleading **UNKNOWN party for these profiles are unknown </figcaption></figure>
<!-- /wp:table --></div></details></div>
<!-- /wp:coblocks/accordion-item --></div>
<!-- /wp:coblocks/accordion -->

<!-- wp:paragraph -->
<p>See that the sentiments are close to 0 in sentimentscore indicating no apparent polarization between the parties. The most immediate observation is the positive score between Radikale Venstre and Iniut Ataqatigiit. Nye Borgerlige and the Government appear most on the lowest score of average sentiment between parties. </p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Parties and word clouds</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>In this subsection, the examination of the following questions will be carried out: "<em>Do the parties tweet about the same topics as they talk about at the parliament?</em>"</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Each of the politicians are grouped in their associated political parties. Then word clouds are generated based on the text from all tweets belonging to the members of each of the parties. Additionally, word clouds are generating using meetings from the Parliament - now also grouped by the parties.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Now the topics of tweets and topics of the meeting can be compared. This comparison takes the eight main topics of meetings and twitter for each party. Notice that we manually de-select all words that are verbs or non-important words like adverbs. The following three parties shows some of the interesting results.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let’s start by looking at Socialdemokratiet.</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/Socialdemokratiet-1024x400-1.png)

<!-- wp:paragraph -->
<p>Top 8 <strong>Meeting</strong> topics: work, people, children, possibilities, folks, forward, time, people's party</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Top 8 <strong>Twitter</strong> topics: "spolitik", new, good, children, regions, "randers", "venstredk", "s"</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Socialdemokratiet talks about work, people and children at the meetings. The topic "børn" (children) corresponds to some of the main topics at Twitter - which is also children. The topics at the meetings (people, possibilities, time) are more general terms, where the topics on Twitter are more specific. One of the Twitter topics is "randers", which is a city in Denmark in Jutland. Socialdemokratiet also mentions "venstredk" which relates to the party Venstre. What is interesting to see is that the word "børn" is a topic of the cloud. At the new-years speech, Mette said that she stand up for the children in Denmark <a href="https://www.socialdemokratiet.dk/da/partiet/vi-er-paa-boernenes-hold/">link</a>.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Lets have a look on Nye Borgerlige…</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/Nye-Borgerlige-1024x395-1.png)

<!-- wp:paragraph -->
<p>Top 8 <strong>Meeting</strong> topics: "nye borgerlige", people, folks, money, "venstre", foreigners, possibilities, Islam</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Top 8 <strong>Twitter</strong> topics: "nye borgerlige", "dkmedier", "klr15", children, "madswibeck", the Danes, EU, foreigners</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Nye Borgerlige's mentions the party "venstre" in the meetings, and the more unique topics in relation to the other parties, is the topics "udlændinge" (foreigners) and Islam. At Twitter, foreigners is also a topic! Theres som similarity in that topic. At Twitter Nye Borgelige also talks about children and the EU.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let’s look at Radikale Venstre…</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/Radikale-Venstre-1024x395-1.png)

<!-- wp:paragraph -->
<p>Top 8 <strong>Meeting</strong> topics: "radikale venstre", decline, people's party, children, work, folks, people, money</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Top 8 <strong>Twitter</strong> topics: "radikale", "dkgreen", "oestergaard", eu, "sofiecn", "s", children, "næstved"</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Radikale Venstre's meeting topics related to children, people and work. At Twitter the topics relate to clima ("dkgreen"), the EU and children. The topic "næstved" relates to a city in Jutland. One could perhaps question whether the tweets topic concerning e.g. clima corresponds to the topics they actually talk about in the Parliament.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Now we’ve provided some insights into three of the Danish parties. This project can not with certainty conclude whether the <em>parties tweet about the same topics as they talk about at the parliament</em>. But the word clouds gives some indication: some parties tweets and meetings seems very alike. Other parties talk more “conceptual” about people, work and money. In the end - we’ll let the readers judge by themselves. Word clouds are generated for all of the parties and located in the bottom of this webpage in the section “<strong>The word clouds for the parties”.&nbsp;</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Community detection and word clouds</h3>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3>Community detection</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>By translating Twitter relationships and mentions into a network, it is possible to shed light on how politicians are connected. Some politicians may be more connected than others, and with the use of network theory, it is possible to divide the policies into groups so that those who are most connected belong to the same group.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>This connection can provide new insights into how politicians can perhaps more effectively gather up and discuss relevant political issues with other politicians talking about the same thing.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>To generate communities from the Twitter network, the best partition algorithm was used. It seeks to maximize the modularity of each community using Louvain heuristics. More on this <a href="http://networksciencebook.com/chapter/9#modularity">here</a>. Below is a visualization of the best partitioning of the network.</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/website_plots_v5_wComNames-1024x420-1.png)

<!-- wp:paragraph -->
<p>With the communities in place, it was of interest to see what these communities talked about, so a series of words clouds were produced to summarize this data.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>For example the word cloud for the first community looks like this;</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/commu.1-edited.png)

<!-- wp:paragraph -->
<p>The three most central profiles in this community, (Morten Østergaard, Sofie Carsten Nielsen, and Kristian Hegaard) are all from the same political party “Radikale Venstre”, which could be the reason why “Radikale” are one of the main topics of this community. After looking into the community members, it is observed that there are a lot of members from the “Radikale Venstre”. Some of the main topics from the community are also <a href="https://www.opdagdanmark.dk/">opdagdanmark</a>, which is a webpage dedicated to informing about the activities in Denmark. Furthermore, the community talks about “gin”, which indicates a more non-formal language.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let’s have a look on another community word cloud.</p>
<!-- /wp:paragraph -->

![](https://LauJohansson.github.io/images/community1-2.png)

<!-- wp:paragraph -->
<p>Marianne Vind ("Socialdemokratiet"), Karen Melchior ("Radikale Venstre"), and Jan E. Jørgensen ("Venstre") are the most central politicians in this community. This community tweets the most about the EU. Marianne and Karen are both members of the EU-Parliament and Jan is EU-moderator for "Venstre". Therefore it is not surprising, that these are the main topics of these politicians. Regardless, this could support that these politicians, which officially are attached to political posts regarding the EU - are actually also tweeting about the EU. There is therefore some link between their political role and their tweet topics.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Looking across all of the most central politicians in each of the communities, each of the communities actually represents the parties. This applies to four of the identified communities. Most of the communities even only contain members of the same political party. This indicates, that the partitioning of the network did not give any surprisingly new communities. Other than it emphasizes that politicians on Twitter connect the most with members of their own party. However, the community described above is an example of how politicians connect (potentially) in relation to which topics they tweet about. If a more efficient way of gather with other politicians, should be based on this analysis - it could be recommended that members of the community should meet up and discuss topics like the EU.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Summary</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>A network based on tweets from Danish politicians. It revealed that the constructed network has the properties of a true social network. An interesting finding, is that the average distance between any two politicians on Twitter is only 2 acquaintances!&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Sentiment analysis on the meetings in the Parliament and on Twitter reveals a more formal language in the Parliament - but more personal communication on Twitter.&nbsp; There’s a difference between the parties' overall sentiment score in the Parliament. The least positive party at the Parliament meetings is Nye Borgerlige. Interestingly, Nye Borgerlige and the Government has the lowest sentiment score from other parties on Twitter.&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Looking at word clouds from Twitter vs. the Parliament for the party Socialdemokratiet, it can be observed <em>children</em> is one of the main topics - both at Twitter AND in the Parliament meetings. Could this mean that Mette Frederiksen is actually the Prime Minister of the children?</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Using cool network theory, the politicians have been divided into communities depending on the mentions on Twitter. Most of the communities are very similar to the actual political parties of the community-members. However, one community is different! The community-members do not belong to the same party BUT are all especially engaged in the EU. This information could in the future be used to more efficiently gather politicians based on their political engagements and make the shortest path EVEN shorter. Potentially, if a politician realizes who he/she is in a community with, they could have more in common than initially thought, which could lead to greater discussions of relevant political issues.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Downloads</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Link for explainer: <a href="https://colab.research.google.com/drive/1ezGDpo4C-tn6zqIPBhYVd97n-_C4MV1W?usp=sharing">https://colab.research.google.com/drive/1ezGDpo4C-tn6zqIPBhYVd97n-_C4MV1W?usp=sharing</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>If you are interested in doing network science yourself, you can clone our <a href="https://github.com/98christianp/politiker">Github repository</a>.  Please keep in mind - the files containing access-keys for the Twitter APIs are removed.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>The word clouds for the parties can be found here - [LINK](https://github.com/LauJohansson/LauJohansson.github.io/tree/main/images/party_clouds) </h3>
<!-- /wp:heading -->
