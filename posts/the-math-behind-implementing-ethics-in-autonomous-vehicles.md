<h1>Implementing Ethics in Autonomous Vehicles</h1>
<!-- wp:paragraph {"customFontSize":15} -->
<p style="font-size:15px"><em>Author: Lau Johansson<br>11th August 2020<br>Reading time: 15 min.</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>This blog post elaborates on how the three ethical theories from my previous blogpost has been mathematically formalized. Before continuing reading I recommend to spend some time understanding <a href="https://github.com/LauJohansson/LauJohansson.github.io/blob/main/posts/implementing-ethics-in-autonomous-vehicles.md">this post. </a></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Mathematical formalization</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>I propose three mathematical formalizations of the ethical theories. Mathematical formalization used in this blog is a process where mathematical logic is used for examining problems in the world around us.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Symbols that are often used are: </p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/math_1.png)


<!-- wp:paragraph -->
<p>Here’s an example:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>“If you go in the rain and don’t have any rain gear or umbrella, you will get wet”</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/rain.png)

<!-- wp:paragraph -->
<p>This could be formalized as:</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/math_2.png)

<!-- wp:paragraph -->
<p>If it does not seem very intuitive for you – you should not worry. I will try to keep the rest of the article in a “human” language and only provide few formulas for the interested reader.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Formalizing risk</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>To incorporate risk in the formalizations, some assumptions are made. Two stages of risk are distinguished, where the variable r<sub>1, T</sub> represents the aggregated risk that decision <em>d</em> causes, at time T. r<sub>i, t0</sub> represents the risk before a decision is made, and r<sub>i, t1</sub> is the risk after the decision is chosen.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>It is assumed, that the risk before and after a decision is made can be compared. The following applies:</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/math_3.png)

<!-- wp:paragraph -->
<p>Where the values of C represent some kind arbitrary of risk-value.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Risk can be calculated as:</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/math_4.png)

<!-- wp:paragraph -->
<p>The project does not include probability theory and harm. The trolley scenarios are limited to people dying or not. Therefore, risk is formulated as:</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/math_5.png)

<!-- wp:heading -->
<h2>The risk framework</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>In general, I use a kind of “risk framework”. Some of the research papers I have been inspired by can be found in the reference project in the bottom of the post.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The following variables are used:</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/math_update_1.png)

<!-- wp:paragraph -->
<p>D are all possible decisions.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The predicates:</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/math_update_2.png)

<!-- wp:heading -->
<h2>Formalizing utilitarianism</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Using the risk-framework, I have formalized utilitarianism in natural language as: <em>“Choose the decision, if the aggregated risk involved is the smallest (minimal) possible in an accident-scenario”.</em> </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Formalized mathematically:</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/math_8.png)

<!-- wp:paragraph -->
<p>This formula can be read as <em>“For all possible decisions in an accident-scenario, the correct decision is the one, where the aggregated risk after the decision has been made, is one, where the risk is as smallest as possible”</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Formalizing duty ethics</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>The phrase “To be treated as a means” must be put in relation to risk. Here two interpretations are investigated (called F1 and F2 from now on):</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>F1: You are treated as a means if you are affected by an action</li><li>F2: You are treated as a means if you actively are used to achieving something else</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>The first interpretation (F1) are formalized (natural) as:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>“A person is treated only as a mean if the decision causes the person's risk to increase. Therefore, a decision is morally correct if it affects a person's risk so that the risk is either diminished or unchanged. All involved in a decision must have increased or unchanged risk”</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Formalized mathematically (F1):</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/math_9.png)

<!-- wp:paragraph -->
<p>This formula can be read as <em>“For all possible decisions in an accident-scenario, the correct decision is one, where – for each person - the risk after the decision has been made, is the same or has been decreased”</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The second interpretation (F2) are formalized (natural) as:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><em>“A person is treated only as a means if the decision causes the person's risk to increase. Therefore, a decision is morally correct if it affects a person's risk so that the risk is diminished. Moreover, all OTHER involved in a decision must have increased or unchanged risk”</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>This can more easily be read as “the decision must not make it worse for some people and it must make it better for at least one”</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Formalized mathematically (F2):</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/math_10.png)

<!-- wp:paragraph -->
<p>This formula can be read as <em>“For all possible decisions in an accident-scenario, the correct decision is one, where – for each person - the risk after the decision has been made, is; lowered for one person AND the risk for all other are the same or has been decreased”</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Formalizing rights ethics</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>According to rights ethics, humans have the right to live. This can also be viewed as humans having the right not to be assaulted. This right (or claim) protects humans against harm. Relating to the risk framework, it could be rephrased viewed as humans have a right not to get their risk affected/changed. The mathematical formalization of rights ethics assumes that the individual has a Hohfeldisk claim that others must not affect the individual's risk.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Formalized naturally: <em>“For each person in a scenario must ensure that the risk before and after a decision is made must be equal with each other, which corresponds to an unchanged risk”</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Formalized mathematically:</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/math_11.png)

<!-- wp:paragraph -->
<p>This formula can be read as <em>“For all possible decisions in an accident-scenario, the correct decision is one, where – for each person - the risk after the decision has been made, is the same as before”</em></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>How the theories could work out in real life</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->

<p>This section looks very similar to the <a href="https://github.com/LauJohansson/LauJohansson.github.io/blob/main/posts/implementing-ethics-in-autonomous-vehicles.md"> previous post.</a> You have already seen one of the scenarios - but I will introduce another one for you.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Scenario 1</h3>
<!-- /wp:heading -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/scenario_1_movie_cropped_gifversion.gif)

<!-- wp:paragraph -->
<p>An autonomous car drives with a person, person A.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Two persons, B1 and B2, stand in the middle of the road.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The car has two options.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Option 1: The car can drive into person B1 and B2.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Option 2: The car can turn off the road and drive into a pedestrian, person C.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>If the car drives into one or more persons, these will be killed.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>The moral decision must be made by Person A’s autonomous car.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Scenario 2</h3>
<!-- /wp:heading -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/scenario_2_movie_cropped_gifversion.gif)

<!-- wp:paragraph -->
<p>An autonomous car drives with a person, person A.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Five persons, B1, B2, B3, B4, and B5 stand in the middle of the road.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>They will be killed if the car hits them</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Another autonomous vehicle is parked, inside is person C.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The car, where person C sits, can drive out in front of person A’s car. This will save the five persons on the road. But, unfortunately, kill person C.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Option 1: Person C stay parked.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Option 2: Person C drives out in front of Person A.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>The moral decision must be made by Person C’s autonomous car.</strong></p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Moral "correct" decisions of the scenarios</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Please keep in mind, that the following conclusions are based on mathematical formalization made in the bachelor-thesis. The conclusions are therefore conditioned by the underlying assumptions.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Decisions can either be:</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/correct_or_not.png)

<!-- wp:heading {"level":3} -->
<h3>Scenario 1</h3>
<!-- /wp:heading -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/table_sc_1.png)

<!-- wp:paragraph -->
<p>Hopefully, it is clear for you as a reader, that a utilitarian would prefer to kill person C instead of B1 and B2. This is the exact same conclusion the formalizations make.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Using duty ethics (F1), which reminds the most of Kant's formulation, B1 and B2 already stand in the direction where the car is headed towards. Killing person C will result in using person C only as a means to an end (to save B1 and B2).</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>None of the involved persons' risks will be decreased by any of the options. Therefore, according to &nbsp;duty ethics (F2), the more strict version, neither of the options is morally correct!</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Using the formalized version of rights ethics, it is morally correct to kill B1 and B2. An important assumption is that it is B1’s and B2’s own fault, that they are at risk of getting killed. If this assumption was not made, rights ethics would have concluded the decision as morally incorrect.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Scenario 2</h3>
<!-- /wp:heading -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/table_sc_2.png)

<!-- wp:paragraph -->
<p>What is interesting to see is the conclusion of duty ethics (F1). It is morally incorrect to choose to kill Person C to save B1, B2, B3, B4, and B5. This scenario then shows, that according to Kant, it is morally incorrect to use YOURSELF as only a means to an end.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Using the formalized version of rights ethics, it is morally correct to kill B1, B2, B3, B4, and B5. An important assumption is that it is B1, B2, B3, B4, and B5 own fault, that they are at risk of getting killed. If this assumption was not made, rights ethics would have concluded the decision as morally incorrect.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>One could question whether it is true, from a rights ethics perspective, that it is morally incorrect to kill person C. If rights ethics assumes that a person is free and independent, then it must be “allowed” to choose to kill itself to save another person. But…. Will this interfere with B1, B2, B3, B4, and B5 rights to stand on the road with the risk of getting killed? Wow… this can get complex to analyze! I will not dig any deeper into this.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Reflections</h2>
<!-- /wp:heading -->

<!-- wp:heading {"level":3} -->
<h3>Math and human language</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Mathematical is a great tool for translating human language so that computers can understand it. Though, the implementation of formalized ethics is limited by a lot of assumptions. Changing one assumption can change the outcome of a decision completely. Moreover, mathematical logic is often more “strict” than human language. If someone says to you: “You can either take an apple or a piece of watermelon”. I bet you would think you could take either an apple or a piece of watermelon. But, could someone might think that it is OK to take both? A robot would actually think that it is allowed to take both the fruits. These ambiguities in human language is a major challenge when “translating” human language to AVs.</p>
<!-- /wp:paragraph -->

![](https://github.com/LauJohansson/LauJohansson.github.io/blob/main/images/human_language.png)

<!-- wp:paragraph -->
<p><em>In the context of ethics and AVs, the fruits could represent human lives. The robot could be an AV.   </em></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>Quantifying risk</h3>
<!-- /wp:heading -->

<!-- wp:html -->
<p>Using the term “risk” when implementing ethics in AV’s, it is necessary to explicitly define what risk is related to traffic. In a simple setting risk consist of a combination of harm and the probability of harm. Probability theory will definitely have an important role in the implementation of machine learning algorithms and ethics in AVs. However, this is not a research area I have dived into. Regarding quantification of harm, I have come across a paper, which proposes to use a mathematical collision model combined with multi-criteria decision making (MCDM). <a href="”https://www.researchgate.net/publication/328989846_Model-to-Decision_Approach_for_Autonomous_Vehicle_Convoy_Collision_Ethics”">Find the paper here.</a></p>
<!-- /wp:html -->

<!-- wp:paragraph -->
<p id="block-d71d230e-e93a-4acb-97a1-3fb47d256896">Thanks for reading the post! </p>
<!-- /wp:paragraph -->

<!-- wp:coblocks/accordion -->
<div class="wp-block-coblocks-accordion"><!-- wp:coblocks/accordion-item {"title":"Links"} -->
<div class="wp-block-coblocks-accordion-item"><details><summary class="wp-block-coblocks-accordion-item__title">Links</summary><div class="wp-block-coblocks-accordion-item__content"><!-- wp:paragraph {"placeholder":"Add content…"} -->
<p>The content of this post is mainly based on the bachelor thesis by Lau Johansson. It is unfortunately only exists in a danish version.  </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><a href="https://findit.dtu.dk/en/catalog/2450655064">https://findit.dtu.dk/en/catalog/2450655064</a></p>
<!-- /wp:paragraph --></div></details></div>
<!-- /wp:coblocks/accordion-item --></div>
<!-- /wp:coblocks/accordion -->
