# Case-Study-Ds
Data Science Case study - Verve

**Observations**

-   Price List = [0.01, 0.1, 0.2, 0.4, 0.5, 0.75, 1, 2, 5, 9], for the following case. Else we can have any price in a real life scenario.
-   bid_price greater than 0 always as a bid of 0 is not possible.
-   max bid_price we have is 9 in this case.
-   at bid_price of 9 we have 1 event and 1 win, hence 100% surity of a win.
-   max number of events ocur at bid_price of 0.2

**Hence we assume that at bid price of 0.2 we have the maximum number of biddings done**

## Solution 1 :

Total events and winrate table :
| app | bid_price | winrate | total_events |
| --- | --- | --- | --- |
| A | 0.01 | 0 | 100000 |
| A | 0.1 | 0.3 | 10000 |
| A | 0.2 | 0.2 | 10000000 |
| A | 0.4 | 0.3 | 1000000 |
| A | 0.5 | 0.2 | 100000 |
| A | 0.75 | 0.3 | 10000 |
| A | 1 | 0.6 | 1000 |
| A | 2 | 0.7 | 100 |
| A | 5 | 0.8 | 10 |
| A | 9 | 1 | 1 |

**We observe that as we go up in the table the total events increases by 10 times, till it reaches the maximum value at bid price of 0.2 after which it decreases.**



### winrate scatterplot : 
-   size of the blue balls are equivalent to relative size of total events.
![image](https://user-images.githubusercontent.com/31728237/184832366-d3fe8ac9-e57b-4b70-887d-ca2d8156f3a4.png)

## Solution 2 :
  Since pay by the advertiser is a constant, we can maximize the net income revenue by minimizing bid response or the bid price.
-     net revenue = advertiser pay - bid response

From total events and winrate table:
total win = total events * winrate

          = 10000000*0.2
          
          = 2000000 number of wins.
         
Also we assume net win from each successful bid is minimum of 0.01$(least possible amount)

Profit    = 0.01 * 2000000 

         Profit = 20000$
         
| app |	bid_price	| win |	events | net income revenue |
| --- | --- | --- | --- | --- |
| 0 |	A |	0.01 |0 | 100000 | 0.00 |
| 1 |	A | 0.01 | 1 | 0 |	0.00 |
| 2	|A | 0.10 |	0	| 7000 |	0.00 |
| 3	|A | 0.10 |	1	| 3000 |	30.00 |
| 4	|A | 0.20	| 0 | 8000000 |	0.00 |
| 5	|A | 0.20	| 1 |	2000000 |	20000.00 |
| 6	|A | 0.40	| 0	| 700000 |	0.00 |
| 7	|A | 0.40	| 1	| 300000 |	3000.00 |
| 8	|A | 0.50	| 0 |	80000 |	0.00 |
| 9	|A | 0.50	| 1 |	20000 |	200.00 |
| 10|	A	| 0.75 | 0 | 7000 |	0.00 |
| 11|	A	| 0.75 | 1 | 3000 |	30.00 |
| 12|	A	| 1.00 | 0 | 400 |	0.00 |
| 13|	A	| 1.00 | 1 | 600 |	6.00 |
| 14|	A	| 2.00 | 0 | 30 |	0.00 |
| 15|	A	| 2.00 | 1 | 70 |	0.70 |
| 16|	A	| 5.00 | 0 | 2 |	0.00 |
| 17|	A	| 5.00 | 1 | 8 |	0.08 |
| 18|	A	| 9.00 | 0 | 0 | 0.00 |
| 19|	A	| 9.00 | 1 | 1 |	0.01 |      


From the table we see maximum value or revenue is for bid of 0.2

Hence most optimal bid valuation we should send in our response is 0.2.
