---
layout: post
title:  "Deliveroo experimentation principles"
authors:
  - "Ella Johnson-Watts"
  - "Jamie Edgecombe"
  - "Matleen Makko-Boronad"
excerpt: >
  Experimentation at Deliveroo has significantly boosted our innovation as a company. It has allowed us to explore new ideas, protected us from unforeseen challenges by preventing wasted time and resources on ineffective initiatives, and promoted intellectual honesty by validating our assumptions. 
date: 2025-01-13
---

Experimentation at Deliveroo has significantly boosted our innovation as a company. It has allowed us to explore new ideas, protected us from unforeseen challenges by preventing wasted time and resources on ineffective initiatives, and promoted intellectual honesty by validating our assumptions.
Over time, the breadth of our experimentation programme, our tooling and our culture have undergone significant development.
Each year, we run hundreds of experiments, testing a wide array of features. These experiments range from simple UI modifications to complex algorithm adjustments.
We employ a variety of methods, from standard A/B testing to advanced techniques like interleaving, multi-armed bandits and switchbacks.
We've moved from teams using ad-hoc methods for deploying and analysing experiments to a mature experimentation platform, which standardises and automates much of the experiment process.

<p align="center" width="100%">
<img align="center" width="335" alt="experimentation" src="https://github.com/user-attachments/assets/97bba9d1-f23a-43a7-a480-6c8e1455ba8e" />
</p>


But successful experimentation requires more than just technical expertise and tooling. It requires an experimentation "culture" – a shared set of principles and values that embeds experiments in the broader organisational context, and ensures that experimentation is done in a way that is maximally impactful.
As we have matured technically and increasingly democratised our technical capabilities, we have also evolved a set of such principles, which codifies that cultural side.
These enable us to uphold high-quality experimentation whilst achieving our current goal of broadening the pool of Deliveroo employees capable of running experiments.


## Principle 1: Every experiment starts with a clear hypothesis and success criteria. 

Experiments work best when they are specific. We formulate our hypothesis based on past experiments, anecdotes, user research, and competitive analysis - leveraging existing learnings helps us design better experiments. We avoid experimenting aimlessly just to ‘see what happens’, risking learning nothing.
Experiments are a highly valuable resource and unstructured experimentation is wasteful.

We set success criteria for rollout before the experiment starts. It may be tempting to decide on the roll out decision rule once results are observed; but in that case, we are more likely to be biased towards forming a hypothesis that supports the observed impact, rather than admitting the experiment results challenged our initial assumptions.

**Table 1: Good vs. bad alternative hypothesis for an “Order again” carousel**

<table>
  <tr><td>:x: Another carousel will increase conversion.</td><td>:heavy_check_mark: By introducing a new carousel which shows customers where they have previously ordered from, we will reduce the search time customers need to find the items they want - customers will be able to find their favourite partners and meals easier. This will increase conversion.</td></tr>
  <tr><td></td><td> :heavy_check_mark: We will roll out if we observe higher engagement with the new carousel and an increase in overall conversion, without observing a statistically significant decline in any health metrics.</td></tr>
</table>


## Principle 2: You don’t have to be a data scientist to engage with and run experiments

We follow standardised processes and use common tooling (our Experimentation Platform), so that people across our tech org can test their ideas safely. We also want to avoid stakeholders having to do mental gymnastics when comparing one team's impact vs. another's. By making the results accessible to everyone, we disseminate learnings, amplifying their value. 

**Example: Changing the search bar placeholder text in the Consumer app**

Based on previous experiments, we have identified content changes in our consumer, rider, and restaurant applications as an area with significant potential for optimisation and impact. 

To facilitate additional experimentation in this area, we have recently enhanced our experimentation back-end to integrate our Experimentation Platform with our content tool. This integration empowers the content team to design and execute experiments without requiring coding expertise.

In a recent experiment, we tested alterations to the search bar placeholder text in the consumer app. The content team hypothesised that by framing the prompt as a question, consumers would find it easier to search for what they wanted. This experiment gave significant insights into conversion and other metrics to enable decision making.

<table align="center">
  <th><tr><td><b>Control</b></td><td><b>Variant</b></td></tr></th>
  <tr><td><img width="283" alt="image" src="https://github.com/user-attachments/assets/2a46c83b-2620-4d12-ac77-b0113ab75408" />
</td><td><img width="283" alt="image" src="https://github.com/user-attachments/assets/41329463-3919-4188-9325-94cdff391851" />
</td></tr>
</table>

## Principle 3: We communicate the uncertainty of our experiment results. 

Although experiment results give us our most precise insight into the effects of the changes we make, limitations in experiment design and natural sample variability inherently result in uncertainty. We interrogate our results carefully in the broader context of our business and openly acknowledge the limitations of our results. For example, are there trends that might change our interpretation if the experiment was run for longer? This empowers stakeholders to make informed decisions. 

To communicate effectively, consistency is valuable. While there are various effective ways to convey uncertainty, using diverse approaches increases the risk of misinterpretation. Our experimentation platform computes and presents statistical uncertainty in a consistent manner. We also maintain a style guide, with recommendations on how to describe experimental results in written documents and make deductions based on uncertainty levels.

**Figure 2: Experimentation Platform tool results[^1]**

<p align="center" width="100%">
<img width="679" alt="image" src="https://github.com/user-attachments/assets/f22e8820-e4f5-4abc-a941-5b545c32f6ec" />
</p>

**Figure 3: Experimentation Platform tool results[^1]**

<p align="center" width="100%">
<img width="674" alt="image" src="https://github.com/user-attachments/assets/8fe90015-e2ed-4b9a-836f-3abc5d24a6e7" />
</p>

[^1]: Examples for illustrative purposes only

## Principle 4: We only experiment if the value of the experiment outweighs its cost.

Every experiment comes with a cost. Developing our tooling and processes can reduce the experiment setup and analysis costs to effectively zero but some costs will always remain. Whilst we can't precisely estimate an experiment's value upfront, we should still consider it. Each experiment should aim to minimise costs and maximise value and if the tradeoff isn't sensible, we shouldn't proceed. We have a framework to evaluate the value and cost of potential experiments, as shown in the following figure.

**Figure 4: “When to experiment?” Value and cost framework**

<p align="center" width="100%">
  <img width="674" alt="image" src="https://github.com/user-attachments/assets/5d959180-1f30-4e25-902b-f0e55b827caa" />
</p>

**Example: The ‘favourites’ feature**

We recently re-introduced the ability to 'favourite' restaurants, without running an experiment. We believe this  was the right decision, because:

- This was a high-conviction feature. It had proved popular in consumer research and had already been rolled out to employees.
- We know that inconsistent user experience is costly. It would have been painful to roll it back for those users who had been exposed to it during the experimental period.
- There was value in moving quickly by exposing our whole user base to the feature and maximising adoption, since it was a prerequisite for future features that we did want to experiment on (e.g., creating a ‘favourites’ carousel).
- The experiment would have needed to run for a substantial amount of time for us to detect any change in business metrics because we needed to first give users the opportunity to adopt the feature.

## Principle 5: Experiments guide, not rule, our decisions. 

Experiments provide real-world data to either support or challenge our intuition. Whilst experiments can give us robust results in the short term, they only provide information for a specific change for a snapshot in time and provide limited answers on long-term behavioural changes of our consumers, riders and partners. We also need to use a broader set of information such as the seasonal changes, where we are in the business cycle, user research, trends in customer preferences, leadership experience and knowledge of our industry. With this understanding of the broader context of our business, we will then use various quantitative methods, including experiments, to develop our understanding by assessing our hypotheses.

In this blog post, we've outlined five key experimentation principles that underpin our culture, enabling high-quality experiments and increased employee involvement. As we continue to refine our approach to experimentation, these principles will remain essential in guiding our decision-making and shaping our attitude towards uncertainty and trade-offs.
