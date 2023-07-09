# A/B Testing~~~ (DID SOMEONE SAY BEES??)
<br>

![Funny GIF](https://media.giphy.com/media/2jukgZs1AECkGNxAL2/giphy.gif)

(im not apologizing for this stupid joke lol)

---

<br>
So, you, Mr/Mrs Boss of XYZ Company, got some UX/UI people who have come up with a new design for your app or website, and they're excited to push it. But then you remember 'whoa hey there my guy, I remember when Facebook did a major change, and I flippin HATED it'. How can we make sure that our customers won't feel like how I felt with Facebooks new change? How can I know the opinions of the change before it is fully implemented?
<br>
<br>
Well I have a very simple test for you: A/B testing~ (maybe even C??)
<br>
<br>
This testing would be a great answer to the scenario above, and any other scenario just like it! To give a quick rundown before we dive in a bit:

1. First prepare the new webpages/apps and original for testing and also get a sample population to test on
2. Declare a 'threshold' to determine whether a certain percentage of approval is enough to push the new changes
3. Show each variation + original to the sample population and gather data to determine which one performs better
<br>
<br>

This is a very simplified overfiew of A/B testing, but now lets get into why we do this in the first place:

## Why A/B test at all?
<br>
It doesn't take a genius to know it's not a good idea to 'yolo' a change to your well established website/app without a bit of guarantee the change is positive. Doing A/B testing will help you know how your user base will respond to changes. Some benefits and applications of this test are as such:
<br>

- Conversion Rate Optimization
    - By testing different variations of certain elements, like interactable buttons, logos, images, layouts, or headlines, you can identify which combiniation will drive the highest conversions
- Email Marketing
    - This may even be used for emails! Test out different subject lines, email contats, or visuals to determine which variation has the most open, click through, and conversion rate.
- Pricing and packaging
    - A/B testing can be used to try different pricing models, product bundles, or discount offers too! You can find the best variation that will maximize revenue and customer satisfaction.
- Ad Campaign
    - This is a major one, as there are many different ways to test for advertisements. Thanks to the internet, ads can get creative and A/B testing can help us find the best way to use your advertising budget and generate a better ROI.
- Mobile App Optimization
    - A/B testing can help improve user interaction with your app by testing out different layouts, notifications, messaging, and onboard signup processes.
- Cost effectiveness!
    - Pushing a change may lead to catastrophic losses, but A/B testing can prevent such losses by experimenting and seeing the impact of your changes to a smaller group before pushing to your main app/website.
<br>
<br>

There are many more uses and benefits for A/B testing, all depending on what you want to test!

<br>

# What do I need to begin A/B testing??
<br>

We're going to have to go back to statistics class again and recall a concept we've used before: hypothesis testing. And this is a relatively quick first step! You must make a statement/assumption about the expected outcome from the change, such as: "Changing the color of the checkout cart from green to red will increase click-through rates". The measure of success from these tests are called 'Conversion Goals'.
<br>
There are also metrics you can use to evaluate the performance of your conversion goal. The most common ones are: click through rate, average time spent, conversion rate, or any other relevant KPIs (key performance indicators)
<br>
<br>
Next we will need a 'control group'. This group will represent the original of your product/content being tested. 
<br>
And vice versa we will need a 'variation group'. This group will represent the change in your product/content being tested.
<br>
<br>
Now this is a ***VERY*** important aspect you must do: ***RANDOMIZATION***. The test groups must be randomly assigned to ensure no biases. Thgis can be done either by randomly assigning users to either control group or variation group.
<br>
<br>
Lets go back and talk about the group size a bit. There is a general rule of thumb that seems to hold true for most things data science/analyst related: more data = better. So that would also mean: larger sample size = better. A larger size will help reduce liklhood of random fluctuations and increase confidence in results.
<br>
<br>
Once weve gotten our groups and gathered data, we will analyze the results. There are many techniques to analyzing, such as hypothesis testing, confidence intervals, and p-values. These will help you determine whether your Conversion Goal was met or not.
<br>
<br>
And last; repeat! A/B is an iterative process and the results of your test can then be used to refine future tests. Ultimately, you can make a data driven decision to push your new changes or not.
<br>
<br>

# Cool, so what do these numbers mean??? 
WHAT DO THE NUMBERS MEAN MASON??

![MASON???](./images/NUMBERSMASON.png)


<br>
<br>

Now let's talk about the stats side of A/B testing~ (wahooooooo math) [ i say this with no irony, math is dope and yall should stop hating math >:( ]
<br>
<br>
What even is hypothesis testing in A/B testing? Well simply put: it is a method used to determine whether there is an observable difference or not between groups and if these differences are considered statistically significantly different or not. 
<br>
<br>
The first step to hypothesis testing is forming the Null Hypothesis (H0)

- This states there is no siginificant difference between groups, any difference is random chance at this point

<br>

The next step is forming the Alternative Hypothesis (H1).
- This is the opposite of H0, where we state there is a significant difference between groups. This suggests the difference in the groups are not random, and rather is the result from the variations of the test

<br>

Now we need to choose a significance level, otherwise known as alpha. This is the threshold for accepting or rejecting the Null Hypothesis.
- Common values for alpha are 0.05 or 0.01. Which value to pick? That depends on your circumstances.
- Typically; the lower the alpha the 'tighter' the conditions for significant difference become. 
    - In context; 0.05 is more forgiving than 0.01 in terms of declaring significant difference

<br>

If our calculated p-value (we'll talk about this soon) falls below the alpha (below 0.05 or 0.01), we will ***REJECT*** the Null Hypothesis, and therefore conclude the differences are considered significant and there is a reason for difference.
- So to understand this use a bit more; we have a test which determined group A had a higher click rate than group B. But was this by random chance? Or did group A perform better overall because of the variations? If a calculated p-value is ***less*** than alpha, we consider group A performing well not by random chance but because of the changes. If the p-value is ***above*** alpha, then we accept the Null Hypothesis and conclude the differences between Group A and B were random chances and not significant enough to choose group A over B.

<br>
<br>
And that about wraps it up for your overall steps on discovering significant difference or not in A/B testing! Of course doing this once doesn't mean you're done, A/B testing is an iterative process, so you'll be doing this over and over again until you get your desired results! Use the results of these tests to refine your future tests~

---

<br>
<br>
But everything discussed so far is for differences in groups, what if I wanted to know if a group falls within a certain range or not instead?
<br>
Good quesion me, there is a simple answer for this; confidence intervals! The process of null/alternative hypothesis doesn't change, except maybe a bit of the wording.

- Rather than looking for difference (p-value is above or below alpha), we are looking to see if our p-value is 'outside' the confidence interval. 

<br>
???? But what is the confidence interval? Easy! The simplest way to explain is with a perfect split of our alpha.

- Suppose we pick an alpha of 0.05, half of that would be 0.025 right? You'll take that number and let it be the two ends of our interval from 0 to 1. So our interval would look like:
    - 0.025 to 0.975 (add 0.025 to 0 and subtract 0.025 from 1)
- But it doens't have to be split this way! You may calculate the interval however you want to your needs.

<br>
<br>
We then calculate our p-value again (i swear how to do that is next) and compare to our confidence interval: 

- If p-value falls in range of our confidence interval, then we accept the Null Hypothesis since our group falls within the expected range.
- Vice versa, if p-value falls outside that range then we reject the Null Hypothesis since our group falls outside the expected range.

And again, thats about it! Rinse and repeat~

# But my dude, WHAT ARE P-VALUES?

Maybe the blog would flow if I put this before the previous 2 topics, maybe not, I don't know I'm a mathematician not a writer >:|
<br>
<br>
But now let's answer; what are p-values and how do I calculate? P-Values are a probability measure used to determine the statistical significance of the results. It represents the probability of observing the data or more extreme results under the assumption that the null hypothesis is true. 

There are many different tests, all depending on the circumstance of your data and samples. And some of these should be familiar from stats class if you ever took that in school~

- T-Stat:
    - Used for comparing means between two groups, often used when sample size is small or when population standard deviation is unknown.
- Z-stat
    - Similar to T-Stat, but is often used for larger groups or when the population standard deviation is known.
- Chi-Square Stat
    - Used for categortical data analysis, such as yes/no (in its simplest terms).
    - Measures difference in observed frequencies and expected frequencies for Null Hypothesis
- F-Stat
    - Otherwise known as ANOVA test, can compare means across multiple groups at the same time! 
    - Measures ratio of between-group variability to within-group variability.

<br>
There are a few more tests but these fall outside my scope of knowledge. I will mention them incase you wish to research on your own:
- Mann-Whitney U Statistic
- Kolmogorov-Smirnov Statistic
<br>
<br>
The results from any of these tests is the p-value, and is the value we use in the above above steps.
<br>
<br>
Now how do we calculate these? Sorry this is a blog not a full ass lecture :P there are many free resources out there with a quick google search and from my personal experience I can promise you its very easy using Python c: No need for hard calculations or flipping to the ass cheeks of a textbook like we did in high school. 

<br>
<br>

---

<br>
<br>
And with all that said, this is the basics of A/B testing! There are far more nuances to A/B testing but this blog has gone long enough already. I hope this blog helped you understand A/B testing more!
<br>
<br>
Samuel Song