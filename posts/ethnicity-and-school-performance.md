
<!-- wp:heading {"level":6} -->
<h1>Challenging the myth - Does ethnic composition affect public school performance?</h1>
<!-- /wp:heading -->

<!-- wp:paragraph {"customFontSize":15} -->
<p style="font-size:15px"><em>Authors: Daniel Juhász Vigild, Frederik Kromann Hansen &amp; Lau Johansson<br>15th May 2020<br>Reading time: 8 min.</em></p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":1555,"sizeSlug":"large","linkDestination":"none","className":"is-style-default"} -->
<div class="wp-block-image is-style-default"><figure class="aligncenter size-large"><img src="https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/newspapers_introduction_v3.png" alt="" class="wp-image-1555"/><figcaption>News articles claiming a connection between school performance and share of students with foreign backgrounds</figcaption></figure></div>
<!-- /wp:image -->



<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">In Denmark, a prevalent opinion in the public discourse and mainstream media is that the performance of public schools becomes lower due to a higher share of students from foreign backgrounds.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">Is this true, or are there some deeper structural elements behind this narrative? Might social, economical and institutional variables impact this as well?&nbsp;</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">Public schools are the main arena for laying the seeds of social mobility. This narrative is stigmatising kids from an early age - which could create a self-fulfilling prophecy of poor performance from kids attending these schools.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"center","textColor":"primary","fontSize":"normal"} -->
<p class="has-text-align-center has-primary-color has-text-color has-normal-font-size">Try finding your school in the interactive map below</p>
<!-- /wp:paragraph -->

<!-- wp:media-text {"mediaId":1557,"mediaLink":"https://explorifydata.com/ethnicity-and-school-performance/share_foreign-2/","mediaType":"image"} -->
<div class="wp-block-media-text alignwide is-stacked-on-mobile"><figure class="wp-block-media-text__media"><img src="https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/share_foreign.gif" alt="" class="wp-image-1557 size-full"/></figure><div class="wp-block-media-text__content"><!-- wp:paragraph {"placeholder":"Content…","textColor":"primary","fontSize":"large"} -->
<p class="has-primary-color has-text-color has-large-font-size">Before diving into the analysis, check out the map below that shows an overview of the share of students from foreign backgrounds (in percent) for each school district. Try browsing through the different districts and see if you can find the one your school belongs to. By the way, you can click on the </p>
<!-- /wp:paragraph --></div></div>
<!-- /wp:media-text -->

[Link to plot](https://laujohansson.github.io/htmlfiles/map_with_foreign_12-May-1537_map.html)

<!-- wp:heading {"textColor":"primary"} -->
<h2 class="has-primary-color has-text-color">Going beyond the simple correlation</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>There are always at least two sides of a coin, but when you always see the same side, it is natural to believe that it is the only side. However, please hang in there and join us for a journey!</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">At first glance, it appears that the prevalent opinion regarding the effect of ethnic composition on school performance (a metric combining grade point average and student well-being) is confirmed if these are the only two parameters observed. But what if more dimensions are included in the analysis? Take a look at the scatterplot below, which implies a correlation between the share of students with foreign backgrounds and school performance. Try browsing through the tabs of the plot below and reflect on what you see.</p>
<!-- /wp:paragraph -->


[Link to plot](https://laujohansson.github.io/htmlfiles/scatter-html1.html)


<!-- wp:paragraph -->
<p>A darker colour means higher average household income and a big circle means high levels of education held by parents of the students attending the school. Both dimensions seem to be correlated with school performance as well. Already, we are starting to turn the coin and show another side of the story.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">Could it be that wealthier families move to school districts with better-performing public schools? Or maybe, the best opportunity for most immigrants, when moving to Copenhagen is to live in areas where families are generally less well-positioned compared to other areas, and that the general characteristics of families in these areas make it difficult for the parents to support their kids' education?</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">The correlation between the share of students with foreign backgrounds and school performance is still there, but it may not necessarily be because the students don't have Danish ancestors. Maybe the impact of these other dimensions are more profound than the apparent effect of the share of students with foreign backgrounds?</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2><span class="has-inline-color has-primary-color">Let's get down to the nitty gritty...</span></h2>
<!-- /wp:heading -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">Alright, after spending some time exploring the scatterplot above, it is now time to test our hunch – that school performance is better explained by other factors than the share of students from foreign backgrounds. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">Now, to do this we need to establish a common language we can use to communicate the results of the test. When testing this type of problem, data scientists use something called <em>linear regression</em>. Some important fancy words: <em>variables, coefficients, confidence intervals, significance</em>. <strong>Variables</strong> are things we are measuring, like the share of students from foreign backgrounds, average household income and parents' education. <strong>Coefficients</strong> are the effect of variables on our <strong>target-variable</strong> (the thing we are explaining: school performance). Coefficients can be negative or positive. When talking about a coefficient we show the <strong>confidence interval</strong>, which is the interval where we are 95 pct. sure that the true effect lies. If we are more than 95 pct. sure that a variable has either a positive or negative impact on our target variable, we say that the variable has a <strong>significant</strong> effect. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">Good. A quick example. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">Look at the plot below of a fake model that explains weight-loss (target-variable):   </p>
<!-- /wp:paragraph -->

  
 [Link to plot](https://laujohansson.github.io/htmlfiles/dan3.html)

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">Some of the variables are expected to impact weight-loss, like <strong>hours at the gym</strong> and <strong>portions of fast food</strong> eaten. Some of the variables are not expected to impact weight-loss as <strong>meetings attended</strong> and <strong>books read</strong>. And this is exactly what the plot shows! If one spends more <strong>hours at the gym</strong> it will probably result in a bigger weight-loss: a positive coefficient of a high magnitude with a small confidence interval, that does not overlap zero - indicating <em>significance</em>. Conversely for <strong>fast food</strong>: negative coefficient, high magnitude, small confidence interval, no overlap with zero. Finally, <strong>meetings attended</strong> and <strong>books read</strong> both have coefficients close to zero, with wide confidence intervals that overlap zero, indicating <em>insignificance.</em>   </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">Cool beans! Now you know all you need to know to be able to understand the plot we are about to show. The plot will show the coefficients and confidence intervals for the share of students with a foreign background in three different models that explain the school performance metric. These models are:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><span style="color:#3288bd" class="has-inline-color"><strong><span style="text-decoration: underline;">Model 1:</span></strong> </span>Where we only look at share of students with a foreign background.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>Share of students with foreign backgrounds</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p><span style="color:#fc8d59" class="has-inline-color"><strong><span style="text-decoration: underline;">Model 2:</span></strong> </span>Where we look at ethnic data and information about the institution.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>Share of students with foreign backgrounds</li><li>Number of students attending the school</li><li>Qualified coverage (share of hours taught by teachers with formal education in the subject)</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify"><strong><span style="color:#99d594" class="has-inline-color"><span style="text-decoration: underline;">Model 3:</span></span></strong> Where we look at ethnic data, institution information, and socio-economic conditions of the school district.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>Share of students with foreign backgrounds</li><li>Number of students attending school</li><li>Qualified coverage </li><li>Unemployment rate in school districts</li><li>Average household income in school districts</li><li>Education score (a metric describing the levels of education held by parents of the students, the higher the education score the more years spent in school) </li></ul>
<!-- /wp:list -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">Interact with the model below and see how the coefficients and confidence intervals change! (Use the tabs at the top of the plot to add data from the models)</p>
<!-- /wp:paragraph --></div></div>
<!-- /wp:group -->

[Link to plot](https://laujohansson.github.io/htmlfiles/dan1.html)

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">What have we learned from this? Two things:</p>
<!-- /wp:paragraph -->

<!-- wp:list {"ordered":true,"type":"1"} -->
<ol type="1"><li>In <strong><span style="color:#fc8d59" class="has-inline-color">Model 2</span>,</strong> where we have ethnic data and institution data, the coefficients of the share of students with foreign backgrounds barely change. So, adding information about the institution explains almost nothing regarding school performance. We anticipated that qualified coverage should have had an impact on performance, but the lack of this could be because the municipality and schools do a pretty good job of creating equal opportunities for successful teaching. This is done across all schools in the municipality by distributing teacher-resources in a way that is beneficial for the schools where performance has historically been lower.</li><li>When adding average household income, unemployment and parents' education level, the coefficient takes a big leap and becomes positive and insignificant. <mark class="wp-block-coblocks-highlight__content">So, school performance is explained by the socio-economic conditions in the school districts, not by share of students with foreign backgrounds.</mark></li></ol>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Dive into a plot of <span style="color:#99d594" class="has-inline-color"><strong>Model 3</strong> </span>and check out the impact of each individual variable:</p>
<!-- /wp:paragraph -->


[Link to plot](https://laujohansson.github.io/htmlfiles/htmlDAN2-3.html)

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify"><mark class="wp-block-coblocks-highlight__content">It seems that the share of students with foreign backgrounds is actually irrelevant for the performance of the school if we also take into account a few variables regarding the school itself, the average household income, unemployment and educational level in the school district.</mark> And now imagine <strong>ALL THE OTHER THINGS</strong> that could impact school performance as well - just naming a few: parents' interest in kids' life, the relationship between teachers and students, parents' willingness/ability to help kids with their homework, quality of leadership of the school, and teachers' skills within education and communication. All these things are not included in <strong><span style="color:#99d594" class="has-inline-color">Model 3</span></strong> and are pretty darn hard to measure. But imagine the small, insignificant impact that share of students with foreign backgrounds would have in that big, fully informed model. Probably just as small an impact as reading books has on weight-loss.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">In our humble opinion, this is a pretty convincing case, and we highly encourage politicians and authorities to think about this - and other challenges - facing Danish citizens from foreign backgrounds with more statistical nuance. Simply looking at the correlation between two variables is an oversimplification, but the consequences of this oversimplification are felt every day in the communities of the people who are affected by the way the media, politicians and authorities talk about them. Shouldn't it be possible to do better?   </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">Now that you have learned about the relations between the different variables, check out your local school district, or any other one in Copenhagen!</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3,"textColor":"primary"} -->
<h3 class="has-primary-color has-text-color">Find your school</h3>
<!-- /wp:heading -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">The first <span class="has-inline-color has-foreground-dark-color">orange map</span> shows the <span style="color:#ffa704" class="has-inline-color">performanc</span><span style="color:#f69700" class="has-inline-color">e</span><span style="color:#fa9b03" class="has-inline-color">s</span> of the schools - an orange-red school district has a good performance. According to our analysis, the average household income affects performance. Look at the <span class="has-inline-color has-foreground-dark-color">dark-green</span><span style="color:#3e8d16" class="has-inline-color"> </span>areas in the second map to identify the districts with the highest <span style="color:#17ab37" class="has-inline-color">average household income</span>. Dark purple areas in the third map represent districts with high <span style="color:#7319ae" class="has-inline-color">education score</span>. Try to compare the three new maps with the original map of the share of <span class="has-inline-color has-primary-color">students from foreign backgrounds</span>. </p>
<!-- /wp:paragraph -->

<!-- wp:image {"id":589,"sizeSlug":"large"} -->
<figure class="wp-block-image size-large"><img src="https://i1.wp.com/explorifydata.com/wp-content/uploads/2020/05/combine_images_15may.png?fit=750%2C580&amp;ssl=1" alt="" class="wp-image-589"/></figure>
<!-- /wp:image -->

<!-- wp:paragraph {"align":"justify"} -->
<p class="has-text-align-justify">Use the map below to identify the performance of the school you want to investigate. Use the tabs to navigate to the variables which affect the performance (average household income and education score). Did you forget the share of students from foreign backgrounds in your school district? Don't worry - you can find the map here also! When you are done investigating the variables you can go to the last tab <span style="text-decoration: underline;">"School webpages"</span>. Click on the district and you will be navigated to the school's .kk.dk webpage. </p>
<!-- /wp:paragraph -->

[Link to plot](https://laujohansson.github.io/htmlfiles/map_with_tab_15-May-1503_map.html)

<!-- wp:separator {"color":"primary"} -->
<hr class="wp-block-separator has-text-color has-background has-primary-background-color has-primary-color"/>
<!-- /wp:separator -->

<!-- wp:heading {"textColor":"primary"} -->
<h2 class="has-primary-color has-text-color">Summary</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>What have we learned from this analysis? We will sum up the main takeaways: </p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>The share of students with foreign backgrounds is irrelevant for the performance of the school if other variables are taken into account.</li><li>Average household income <strong>is the only</strong> variable which has a significant effect on school performance, while education score is almost significant but with an impact of a slightly larger magnitude than average household income.</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Thanks for reading!</p>
<!-- /wp:paragraph -->

<!-- wp:coblocks/accordion -->
<div class="wp-block-coblocks-accordion"><!-- wp:coblocks/accordion-item {"title":"References - (click to expand)"} -->
<div class="wp-block-coblocks-accordion-item"><details><summary class="wp-block-coblocks-accordion-item__title">References - (click to expand)</summary><div class="wp-block-coblocks-accordion-item__content"><!-- wp:paragraph {"placeholder":"Add content…"} -->
<p><a href="https://www.folkeskolen.dk/620393/ny-analyse-indvandrere-og-efterkommere-faar-lavere-karakterer-ved-afgangsproeven">www.folkeskolen.dk/620393/ny-analyse-indvandrere-og-efterkommere-faar-lavere-karakterer-ved-afgangsproeven</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://www.djoef-forlag.dk/openaccess/samf/samfdocs/2009/2009_1/samf_2009_1_10.pdf">www.djoef-forlag.dk/openaccess/samf/samfdocs/2009/2009_1/samf_2009_1_10.pdf</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://www.sondagsavisen.dk/politik-2/2016-04-01-her-er-der-flest-elever-med-udenlandsk-herkomst/">www.sondagsavisen.dk/politik-2/2016-04-01-her-er-der-flest-elever-med-udenlandsk-herkomst/</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="http://www.dst.dk/da/Statistik/Analyser/visanalyse?cid=29550">www.dst.dk/da/Statistik/Analyser/visanalyse?cid=29550</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="http://jyllands-posten.dk/indland/ECE7236159/De-st%C3%B8rste-indvandrergrupper-f%C3%A5r-de-laveste-karakterer-i-folkeskolen/">www.jyllands-posten.dk/indland/ECE7236159/De-største-indvandrergrupper-får-de-laveste-karakterer-i-folkeskolen/</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="http://www.sondagsavisen.dk/politik-2/2015-10-23-mange-indvandrerskoler-er-for-ringe/">www.sondagsavisen.dk/politik-2/2015-10-23-mange-indvandrerskoler-er-for-ringe/</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="http://box5496.temp.domains/~explorifwp-admin/www.dingeo.dk/data/grundskoler/">www.dingeo.dk/data/grundskoler/</a></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://uddannelsesstatistik.dk/Pages/main.aspx">https://uddannelsesstatistik.dk/Pages/main.aspx</a></p>
<!-- /wp:paragraph -->

<!-- wp:coblocks/accordion -->
<div class="wp-block-coblocks-accordion"><!-- wp:coblocks/accordion-item -->
<div class="wp-block-coblocks-accordion-item"></div>
<!-- /wp:coblocks/accordion-item --></div>
<!-- /wp:coblocks/accordion --></div></details></div>
<!-- /wp:coblocks/accordion-item --></div>
<!-- /wp:coblocks/accordion -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->
