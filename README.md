# Association Rules
Association rules are if-then statements that show the probability of a relationships between data items within large data sets in various types of databases. Association rule mining involves the use of machine learning models to analyze data for patterns.

An association rule has two parts: an antecedent (if) and a consequent (then). An antecedent is an item found within the data and a consequent is an item found in combination with the antecedent. The if-then statements form itemsets, which are the basis for calculating association rules made up of two or more items in a data set.

## Table of Contents
1. [Project Statement](#project-statement)
2. [Objectives](#objectives)
3. [Data](#data)
4. [Association rule mining](#association-rule-mining)

5. ## Project Statement
For this project, the dataset from a supermarket containing products from transactions over one month was analyzed, it was the month of February, using market basket techniques.

Excel was used to analyze the dataset and knime to study the frequent item sets and association rules.

## Objectives
With this analysis i want to answer several question to help understand the supermarket sales performance.

1 - Study of the variation of the number of frequent item sets (free, closed and maximal) varying the support.
2 - Study of the variation of the number of association rules fixing the support.
3 - Selection of one of the rules with largest lift. Justification of the value of the lift.
4 - What is the conviction of the rule used in the previous question?
5 - Are there differences among the frequent item sets in the beginning of the month and end of month?

## Data
Analyzing the dataset in more detail, i could understand better the way this supermarket worked and the type and frequency of the clients and products sold. The dataset has 168 different items and 50 % of sales are for about 12 % of the products, around 20 products.

I wanted to see how many transactions were made every day and, as can be seen below, this number was constant on the first 20 days with 325 transactions and after that increasing for 415 on the rest of the days excluding the last one that had 430.

![image](https://github.com/user-attachments/assets/901bdfea-0a50-4457-8554-5f0a5755970c)

The number of items sold per day, represented with the orange line on the upper image, had an interesting behavior because with this line we could identify what we think are the weekends, for example, the days 3 and 4 have an increase on the products sold and then we can see an identical increase on the days 10, 17 and 18 and on the days 25 and 26, but off course i could not know this for sure. I could see another two increases for one or two days on the days 13, 14 and 21, this might be due to some holidays. And finally, i could note that the end of the month had more products sold than the beginning and maybe that is because of the salary income that the clients might have.

Another interesting fact that noticed, is that the baskets that have at most seven items make more than 80% of the transactions on almost every day except on the days, that i see before, with more products sold. Those days have more baskets with more than seven items, but in those cases, the lowest value is 72% on the day 14, and this can lead us to think that this supermarket is a small place where people do small purchases. 

![image](https://github.com/user-attachments/assets/18b6b165-60e7-4658-96c4-6a9108e684cb)

Therefore, with this understanding of the data i tried to answer the questions below.

## Association rule mining
1. Study of the variation of the number of frequent item sets (free, closed and maximal) varying the support. 
