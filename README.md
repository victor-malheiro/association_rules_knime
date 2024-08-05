# Association Rules
<div align="justify">Association rules are if-then statements that show the probability of a relationships between data items within large data sets in various types of databases. Association rule mining involves the use of machine learning models to analyze data for patterns.</div></br>

<div align="justify">An association rule has two parts: an antecedent (if) and a consequent (then). An antecedent is an item found within the data and a consequent is an item found in combination with the antecedent. The if-then statements form itemsets, which are the basis for calculating association rules made up of two or more items in a data set.</div></br>

## Table of Contents
1. [Project Statement](#project-statement)
2. [Objectives](#objectives)
3. [Data](#data)
4. [Association rule mining](#association-rule-mining)
5. [Conclusion](#conclusion)

## Project Statement
<div align="justify">For this project, the dataset from a supermarket containing products from transactions over one month was analyzed, the month was February, using market basket techniques.</div></br>

Excel was used to analyze the dataset and knime workflow that is below was created to study the frequent item sets and association rules.

![image](https://github.com/user-attachments/assets/f7fb1ca0-268f-4b70-a9aa-a3e0807dce79)


## Objectives
With this analysis i want to answer several question to help understand the supermarket sales performance.

1 - Study of the variation of the number of frequent item sets (free, closed and maximal) varying the support.
2 - Study of the variation of the number of association rules fixing the support.
3 - Selection of one of the rules with largest lift. Justify the value of the lift.
4 - What is the conviction of the rule used in 3?
5 - Are there differences among the frequent item sets in the beginning of the month and end of month?

## Data
<div align="justify">Analyzing the dataset in more detail, i could understand better the way this supermarket worked and the type and frequency of the clients and products sold. The dataset has 168 different items and 50 % of sales are for about 12 % of the products, around 20 products.</div></br>

<div align="justify">I wanted to see how many transactions were made every day and, as can be seen below, this number was constant on the first 20 days with 325 transactions and after that increasing for 415 on the rest of the days, excluding the last one that had 430.</div></br>

![image](https://github.com/user-attachments/assets/901bdfea-0a50-4457-8554-5f0a5755970c)

<div align="justify">The number of items sold per day, represented with the orange line on the upper image, had an interesting behavior because with this line we could identify what i think are the weekends, for example, the days 3 and 4 have an increase on the products sold and then we can see an identical increase on the days 10, 17 and 18 and on days 25 and 26, but i could not know this for sure. I could see another two increases for one or two days on the days 13, 14 and 21, this might be due to some holidays. And finally, i could note that the end of the month had more products sold than the beginning and maybe that is because of the salary income that the clients might have.</div></br>

<div align="justify">Another interesting fact noticed, is that the baskets that have at most seven items make more than 80% of the transactions on almost every day except on the days, that i refered before, with more products sold. Those days have more baskets with more than seven items, but in those cases, the lowest value is 72% on the day 14, and this can lead us to think that this supermarket is a small place where people do small purchases.</div></br>

![image](https://github.com/user-attachments/assets/18b6b165-60e7-4658-96c4-6a9108e684cb)

Therefore, with this understanding of the data i tried to answer the questions below.

## Association rule mining
**1. Study of the variation of the number of frequent item sets (free, closed and maximal) varying the support.** 

<div align="justify">Since the maximum support is 25,6% for the frequent item set with Whole Milk, i decided to study the number of frequent item sets for each value of support from 1% to 25%.</div></br>

<div align="justify">I choose the minimum value of support of 1% because i think that with a value lower than that i stop having enough information on the relationship between the items and because of that, no good conclusions can be achieved.</div></br>

![image](https://github.com/user-attachments/assets/1d9b8136-e2b9-4b45-999e-7db2663c69e9)

<div align="justify">I could see that, for the same confidence level, the number of closed item sets, which is always the same as the free item sets, are decreasing with the increase of the support. The rate of the decreasing lowers with the increase of the support because the number of frequent item sets is decreasing.</div></br>

<div align="justify">Being the maximal frequent item sets a subset of the closed item sets that have none of its super sets frequent, we can see on the table, that its number is lower than the one for the closed item sets for the lower levels of support, as expected.</div></br>

<div align="justify">When support reaches the value of 8%, we could see that the numbers are equal and this is explained by the fact that this frequent item sets doesn’t have frequent super sets. So maybe a support at 8% can be a good value to study the most important frequent item sets.</div></br>

**2. Study of the variation of the number of association rules fixing the support.**
<div align="justify">Fixing the minimum support at 0,01, beginning with the minimum confidence of 0,01 to the maximum of 0,55 and registering the number of association rules at every 0,05 increment of confidence, i got the results on the table below.</div></br>

![image](https://github.com/user-attachments/assets/0687118c-b14f-4142-b74f-8a40196e2f8e)

<div align="justify">Analyzing the numbers on the table, we see that the number of association rules are decreasing with the increase in the confidence, as expected, because we see a decrease of the most frequent associations between the products.</div></br>

<div align="justify">For instance, we can see that a client that already have yogurt and root vegetables will be more probable to buy whole milk (56,3%) than other vegetables (50%), as can be seen below.</div></br>

![image](https://github.com/user-attachments/assets/b5d924f1-1fdb-41cb-91ac-36fd6becc1fc)

![image](https://github.com/user-attachments/assets/5dc6f8fe-0801-47a2-8b2c-59a41d68ea88)

<div align="justify">With this analysis, we could see that for low values of confidence we have association rules with a less important meaning and with a too high value for confidence we can leave out some important association rules that must be studied.</div></br>

<div align="justify">Therefore, the value of confidence used must have in attention not only the confidence, but also the lift and support values, as we will see on the answers of the next questions.</div></br>

**3. Selection of one of the rules with largest lift. Justify the value of the lift.**
Considering the figure below i choose the lift (beef -> root vegetables).

<div align="justify">The lift value is a measure of importance of a rule. Lift is the ratio between confidence and the expected value for the confidence. In this case with the lift value greater than 1 (3.04) indicates a positive relation, it means that the rule beef and the rule root vegetables appear more often together than expected, this means that the occurrence of the rule beef has a positive effect on the occurrence of the rule root vegetables.</div></br>

![image](https://github.com/user-attachments/assets/5a1ab343-65c4-4441-bdd5-d56817e7e1e1)

**4. What is the conviction of the rule used in 3?**
The conviction is calculated consider the function,

![image](https://github.com/user-attachments/assets/b049e0c4-0870-4072-b083-242f333ba1f4)

<div align="justify">Can be interpreted as the ratio of the expected frequency that beef occurs without root vegetables, it means the frequency that the rule makes an incorrect prediction. In this example the rule show that beef -> root vegetables would be incorrect 33% more often with random association.</div></br>

In this example the sup(root vegetable) is 0.1089 and conf(beef->root vegetable) is 0.331.

**5. Are there differences among the frequent item sets in the beginning of the month and end of month?**
<div align="justify">We have created several scenarios assuming that the purchasing behavior is impacted by the monthly or weekly pay cycle, or even by events like holidays and weekends:</div></br>
  
Small basket – basket less than or equal than 7 items
Large basket – the others
Event - Assuming that the increase in “larger baskets” is related to some event, we analyze these days separately
End of month – the days when there is an increase in the number of baskets, subset day 21 to day 28.
Beginning of month - we have two branches:
	**1)** to maintain consistency in relation to the weekly cycle at the end of the month, day 05 to day 12.
	**2)** ignore the weekly cycle, subset day 01 to day 08.
**Note:** For this we used a support equal to 0,01. 

Considering the figure below with a top 15 of most frequent item sets, my conclusions are: 

<div align="justify">Most articles are common in all subsets. This is independent <strong>i)</strong> of the period of the month (beginning or end) and <strong>ii)</strong> of the type of purchase, be it a convenience purchase (small basket) or a larger purchase (larger basket).</div></br>
  
This is expected to happen once small baskets represent more than 80% of sales.
[Pastry] has a strong presence in the small baskets, which is reflected in the subsets beginning and end of the month.
[Canned beer] has a strong presence in the small baskets, and more influence in beginning of month.
[newspaper] are present in the “small basket”, however their importance is diluted in the total of transactions, being only relevant in the subsets: event and the end of the month.

![image](https://github.com/user-attachments/assets/6028167c-a8cf-4361-9fdb-2012743e13ff)

## Conclusion
<div align="justify">With this assignment, i had the opportunity to understand with a real world example the way the sales of a company work and the support that the management of those companies can have, with frequent patterns recognition and association rules estimation to make the everyday decisions needed to keep the business running well.</div></br>

<div align="justify">With the first question, i could see how the study of the number of frequent item sets and the different types of item sets is important to understand the products that are sold more to the clients and how the variation of support can have an impact on that understanding because with a too low support we don´t have enough information about the relationships between the items and with a too high one, we can ignore important relations.</div></br>

<div align="justify">Solving the second question i could see the impact that the confidence level can have on the number of association rules estimated. Once again, i could see that with a too low value, i have many rules computed but some of them are not very meaningful and with a high value for the confidence, i could lose some information about important association rules.</div></br>
  
<div align="justify">With the third question it’s possible i understood the relation between rules and in this case of supermarket, redefine the place of products consider the potential of joint sales or events to promote a cross sale. However, there is an associated error when i am predicting the occurrence, this is where question four comes in which allows me to measure the deviation or percentage of an incorrect prediction.</div></br>

<div align="justify">With the last question, i could see that i could use the market basket analysis techniques for parts of the dataset to focus my attention in important parts of the month for this business, to have a better understanding of the behaviors of the clients and products sold in those specific days.</div></br>

## Recommendations
<div align="justify">To run the KNIME workflow, open the KNIME file and load the data into the wrokflow and run it.</div></br>

## Copyright

© 2024 Victor Malheiro
