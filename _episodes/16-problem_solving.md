---
title: "Problem Solving"
teaching: 15
exercises: 25
questions:
- "How can I approach problem solving?"
- "How do I answer an unseen problem?"

objectives:
- "Develop an algorithm for an unseen problem"
- "Understand what an algorithm is"
- "Approach a problem in a strategic manner"

keypoints:
- "Follow standard Python style in your code."
- "Use assertions to check for internal errors"
- "Use docstrings to provide online help."
- "Use `__version__` to increase code reproducibility."
---

In this section of the course we learn how to develop a solution to an unseen problem.
The guidance here is not unique to physics, or even using a computer to solve a problem. This process can be used to solve a wide variety of problems, including those which are unrelated to computers.

## Algorithm development

An algorithm is a plan for solving a problem. An algorithm can take many forms: a written description (e.g. recipe), mathematical (e.g. steps for solving a quadratic equation) or graphical (e.g. an Ikea instruction booklet). 

In the context of computational physics, an algorithm allows us to translate a physics problem into a computer program. Algorithm development consists of several major steps, each of which is outlined below.

> ## Everyday example
>
> Boxes like this contain the guidance applied to an everyday example.
{: .callout}

## Step 1: Obtain a description of the problem.

In the context of a university degree, the description of the problem will be given as a written assessment question.  In a professional setting, you may receive written or verbal instructions from a client or colleague. 

Problem description is often the weakest part of the process. It's quite common for a problem description to suffer from one or more of the following types of problems:

- the description relies on unstated assumptions
- the description is ambiguous
- the description is incomplete
- the description has internal contradictions. 

These problems are often not due to carelessness. Instead, they are due to the fact that natural languages (English, French, Korean, etc.) can be imprecise. 

Part of the algorithm developer's responsibility is to identify defects in the description of a problem, and to work with your collaborators to remedy those defects. In this case, you must clearly communicate any decisions made to your collaborators.

> ## Everyday example
>
> Problem: I need you to a send a birthday card to my sister Ruby.
{: .callout}

## Step 2: Analyze the problem.

Read the instructions and determine the answers to the following questions:

- What data is available?
- How to access the data?
- What data or information is missing, ambiguous or contradictory?
- Which formulas relate to the problem?
- Which methods relate to the problem?
- Is there guidance/constraints for working with the data?
- Which resources can I use to help develop an algorithm?

When determining the ending point, we need to describe the characteristics of a solution. In other words, how will we know when we're done? Asking the following questions often helps to determine the ending point.

- What new facts will we have?
- What items will be created or changed?

> ## Everyday example
>
> Analysis: I don't have a card. I do have second-class stamps. I prefer to buy a card rather than make one myself. Ruby's birthday is in four days. Ruby lives in the UK. A second-class card will arrive in three days.
{: .callout}

## Step 3: Develop a high-level algorithm.

An algorithm is a plan for solving a problem, but plans come in several levels of detail. It's usually better to start with a high-level algorithm that includes the major part of a solution, but leaves the details until later. 

We can use an everyday example to demonstrate a high-level algorithm. This high-level algorithm can be written as pseudo-code.

> ## Everyday example
>
> High-level algorithm:
> 
> 1. Go to a shop that sells greeting cards
> 2. Select a card
> 3. Purchase a card
> 4. Attach a stamp
> 5. Post the card
{: .callout}

This algorithm is satisfactory as general guidance, but it lacks details that would have to be added were a computer to carry out the solution. 

These details include answers to questions such as the following.

- Which shop will I visit?
- How will I get there: walk, drive, ride my bicycle, take the bus?
- What kind of card does Ruby like: humorous, sentimental, risqué?

These kinds of details are considered in the next step of our process.

## Step 4: Refine the algorithm by adding more detail.

A high-level algorithm shows the major steps that need to be followed to solve a problem. Now we need to add details to these steps, but how much detail should we add? Unfortunately, the answer to this question depends on the situation. We have to consider who (or what) is going to implement the algorithm and how much that person (or thing) already knows how to do. 

> ## Everyday example
> 
> If I'm going to purchase a birthday card for somebody else, the instructions have to be adapted to whether or not I am familiar with the shops in the community and how well I understand their taste in greeting cards.
{: .callout}

When our goal is to develop algorithms that will lead to computer programs, we need to consider the capabilities of the computer and provide enough detail so that someone else could use our algorithm to write a computer program that follows the steps in our algorithm. As with the birthday card problem, we need to adjust the level of detail to match the ability of the programmer. When in doubt, or when you are learning, it is better to have too much detail than to have too little.

> ## Everyday example
>
> Refined algorithm:
> 
> 1. Take the 44 bus to Haymarket
> 2. Go to Hallmark shop on Northumberland street
> 3. Select the funniest birthday card you can find
> 4. Purchase the card using my bank card
> 5. Attach the second class stamp to the envelope
> 6. Write Ruby's address:
> 7. Place card in envelope
> 8. Go to the post box
> 9. Post card
{: .callout}

For larger, more complex problems, it is common to go through this process several times, developing intermediate level algorithms as we go. Each time, we add more detail to the previous algorithm, stopping when we see no benefit to further refinement. This technique of gradually working from a high-level to a detailed algorithm is often called stepwise refinement. At each step we may need to communicate with our collaborators to improve the problem description.

## Step 5: Review the algorithm.

The final step is to review the algorithm. First, we need to work through the algorithm step by step to determine whether or not it will solve the original problem. 

- Does it establish the facts required?
- Does it output or update the items as specified?

> ## Everyday example
>
> Will the card reach Ruby in time for her birthday?
> Will Ruby like the card?
{: .callout}

## Step 6: Implement the algorithm as code

At this point we have established an algorithm for tackling the problem, but it is not implemented as code.

In this step we translate the algorithm into a programming language of our choice. 

## Step 7: Review the results

Next we want to establish that our results are reasonable. 

- Are there related problems which we know the solution to? How does our solution compare?

For quantitative solutions we can also ask the following questions:

- Is our solution the correct order of magnitude?
- Are the units of measure consistent? 

## Step 8: Review the code

Once we are satisfied that the algorithm does provide a solution to the problem, we start to look for other things. The following questions are typical of ones that should be asked whenever we review an algorithm. 

- Does this code solve a very specific problem or does it solve a more general problem? 
- If it solves a very specific problem, should it be generalized?

> ## Simple example
>
> A code that computes the area of a circle having radius 5.2 meters (formula $π*5.22$) solves a very specific problem, but an algorithm that computes the area of any circle (formula $π*R^2$) solves a more general problem.
{: .callout}

- Can this algorithm be simplified?


> ### Simple example
>
> For example, one formula for computing the perimeter of a rectangle is: length + width + length + width
>
> A simpler formula would be: $2.0 * (\textrm{length} + \textrm{width})$
{: .callout}

- Is this solution similar to the solution to another problem? How are they alike? How are they different?


> ### Simple example
>
> Consider the following two formulae:
> 
> $\textrm{Rectangle area} = \textrm{length} * \textrm{width}$
>
> $\textrm{Triangle area} = 0.5 * \textrm{base} * \textrm{height}$
>
> Similarities: Each computes an area. Each multiplies two measurements.
>
> Differences: Different measurements are used. The triangle formula contains 0.5.
>
> Hypothesis: Perhaps every area formula involves multiplying two measurements.
{: .callout}

> ## Problem Solving applied to exponential decay
>
> This question is partly modelled on the a [blog post](https://towardsdatascience.com/modeling-exponential-growth-49a2b6f22e1f).
>
> We have the following (hypothetical) data for the number of Covid cases at a university over a two-week period: 
> `3, 4, 8, 15, 32, 65, 128, 253, 512, 1025, 2049, 4090, 8191, 16387`. Each data point corresponds to the positive test results received on a single day.
{: .challenge}

> ## Problem solving applied to exponential decay
>
> Ideally working in a group, apply the eight problem solving steps to solve the following problem.
> 
> We have the following data for the temperature of a metal film as it cools: 
> `16387, 8191, 4090, 2049, 1025, 512, 253, 128, 65, 32, 15, 8, 4, 3`. Between each measurement there is a one second gap.
> 
> By taking a logarithm of the data, fit a straight line to the case number data and predict the exponential decay factor.
>
> If you want to learn more about exponential relationships, there is a nice 
> [3Blue1Brown video on exponential growth in the context of Covid](https://www.youtube.com/watch?v=Kas0tIxDvrg).
{: .challenge}
