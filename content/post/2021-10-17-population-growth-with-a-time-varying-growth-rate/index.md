---
title: "Population growth with non-constant growth rate"
bibliography: /Users/jb/Nextcloud/Zotero/my_library.bib
csl: /Users/jb/Nextcloud/Zotero/styles/demographic-research.csl
---
This article considers the case where the population growth rate is not constant over time.

I have just started working my way through Andrei Rogers' *Applied Multiregional Demography Through Problems: A Programmed Learning Workbook with Exercises and Solutions* [@rogers2020] and there was an exercise that had the population growth rate decline linearly to zero growth over a period of time. In the preceeding text the explanation on calculating growth had only looked at case where the growth rate is constant. The problem was that I was unable to generalise the method to give me an equation for a non-constant case.

I pulled out my old copy of *Demographic Methods* [@hinde2014] to see how it presented population growth. It had derived the case for constant growth using pretty much the same method as @rogers2020. So I was no further ahead.

First, I will detail the approach used in these books and then how I eventually came to a generalised method.

## Constant growth

The approached used in the two books move from an annual constant rate of growth to the continuous case.  Their derivation roughly follows the approach.

Say we had a population growing at constant rate of $r$ per annum. If the population at the start was $P_0$ then after a year the population would be $P_1 = P_0(1+r)$. Since this compounds over time then after year $n$ the population would be $P_n = P_0(1+r)(1+r)...(1+r) = P_0(1+r)^n$. The compounding in this formulation only happens once a year.

In order to move to the continous case, the growth can be spit into finer time periods. So for example, growth compounding six monthly would be $P_1 = P_0(1+\frac{r}{2})^{2}$ or for n years $P_n = P_0(1+\frac{r}{2})^{2n}$. If the compounding period is reduced to shorter time periods then the equation can be generalised to $P_n = P_0(1+\frac{r}{k})^{kn}$, where $k$ is the number of compounding time periods within a year.

At this point they move to focussing on increasing $k$ toward infinity and using a limit. Taking the compounding part of the formula they derive the limit as $e^r$:$$\lim_{k \to \infty}(1+\frac{r}{k})^{k} = e^r$$ 

This leads to the growth formula as: $$P_n = P_0e^{rn}$$

This is a rather beautiful mathematical result. @hinde2014 even takes a further step to show the binomial expansion of the $(1+\frac{r}{k})^{k}$ for $k=3$, and you can see how this looks like the power series expansion of the $e^x$.

## Constant growth now with calculus

So while above is very interesting, is it not generalisable to $r$ changing with time. So, I found I was struggling with how to solve Rogers' exercise. Surely, the answer involves calculus.

Now my calculus is very rusty, so I turned  to my old friend @thomas1988. With population growth we are looking change in the population over time. To express this idea as a differential equation we would write the constant growth rate expression as: $$ \frac{dP(t)}{dt} = rP(t)$$. 

In words, the change in the size of the population is proportional to the size of the population. With the proportion in our case being $r$. To solve this we can rearrange and then integrate. $$ \frac{1}{P(t)}dP(t) = r dt$$

This integrates to: $$ln(P(t)) + C = rt$$

Since we want $P(t)$ we can raise both sides to the power of $e$ and get rid of the log: $$P(t)e^C = e^{rt}$$

We can move the constant $e^C$ to the otherside and since at time zero the equation has to equal the starting population size we can set this to $P(0)$. This leaves as  with: $$P(t) = P(0)e^{rt}$$.

So we are now back at where we started, but now we have a nice method for moving to non-constant growth rate.

## Non-constant growth

Going back to our original calculus based formula and substuting the constant $r$ with a time based function $r(t)$ we get:
$$ \frac{dP(t)}{dt} = r(t)P(t)$$. 

So now we can solve this as:$$P(t) = P(0)e^{\int{r(t)dt}}$$

Ok, the $\int{r(t)dt}$ looks daunting. But, all we are doing is looking for the area under the $r(t)$ curve. In Rogers' example, he was using a linearly declining $r(t)$ and solved it using geometry — essentially he recognises that the area under of the $r$ curve is half of the $r \times n$ rectangle.

## A worked example

Say we have a city population that starts with 200,000 people in 2020. Let's say the growth rate starts at 2.5% but is declining, linearly, to zero over 25 years - ie 0.1 percentage points per year. What is the population expected to be in 2045?

Let's solve $\int{r(t)dt}$. From the description $r(t) = 0.025 - 0.001t$. So $\int_{t=0}^{25} (0.025 - 0.001t) dt$ equals $$0.025t - \dfrac{0.001}{2}t^2 \Big|_{t=0}^{25} = 0.3125$$

So, the population in 2045 would be $P_{2045} = 200000 e^{0.3125}$ or 273,368 people.

We could also check this geometrically. If we had constant growth of 2.5% we would have had the growth component as $e^{0.025 \times 25}$, but since the area under the curve is $r(t)$ is only half of the $r \times n$ we could write $e^{\dfrac{0.025}{2} \times 25}$ rectangle which equals $e^{0.3125}$ and we are back to where we were previously.

## Conclusion
It was quite fun for me to revisit calculus. I realise that introductory demography textbooks want to step away from this complexity, but I think that in  this case avoiding  calculus limited the class of problems that could be solved without feeling like I just  had to trust the author.

## References
