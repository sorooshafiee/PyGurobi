# PyGurobi

This repository solves the factory planning example available on the [Gurobi website](http://www.gurobi.com/resources/examples/factory-planning-I). We use the code in [GurobiVideos](https://www.youtube.com/watch?v=5mct7ltVeVc) channel in Youtube. 

**Note that the problem description and code are exactly the same as Gurobi website.**

## Problem Description
A factory makes seven products (Prod 1 to Prod 7) using a range of machines including:

- Four grinders
- Two vertical drills
- Three horizontal drills
- One borer
- One planer

Each product has a defined profit contribution per unit sold (defined as the sales price per unit minus the cost of raw materials). In addition, the manufacturing of each product requires a certain amount of time on each machine (in hours). The contribution and manufacturing time value are shown below. A dash indicates the manufacturing product for the given product does not require that machine.

|     | PROD 1 | PROD 2 | PROD 3 | PROD 4 | PROD 5 | PROD 6 | PROD 7 |
| ------------ | ------------- | ------------ | ------------- | ------------ | ------------- | ------------ | ------------- |
| Contribution to profit | 0.5 | 0.7 | - | - | 0.3 | 0.2 | 0.5 |
| Grinding | 0.1 | 0.2 | - | 0.3 | - | 0.6 | - |
| Vertical drilling | 0.1 | 0.2 | - | 0.3 | - | 0.6 | - |
| Horizontal drilling | 0.2 | - | 0.8 | - | - | - | 0.6 |
| Boring | 0.05 | 0.03 | - | 0.07 | 0.1 | - | 0.08 |
| Planing | - | - | 0.01 | - | 0.05 | - | 0.05 |

In each of the six months covered by this model, one or more of the machines is scheduled to be down for maintenance and as a result will not be available to use for production that month. The maintenance schedule is as follows:

| Month | Machine | 
| ------------ | ------------- |
| January | One Grinder | 
| February | Two Horizontal Drills | 
| March | One borer | 
| April | One vertical drill | 
| May | One grinder and one vertical drill | 
| June | One horizontal drill | 

There limitations to how many of each product can be sold in a given month. These limits are shown below:

|     | PROD 1 | PROD 2 | PROD 3 | PROD 4 | PROD 5 | PROD 6 | PROD 7 |
| ------------ | ------------- | ------------ | ------------- | ------------ | ------------- | ------------ | ------------- |
| January | 500 | 1000 | 300 | 300	| 800 | 200 | 100 |
| February | 600 | 500 | 200 | 0 | 400 | 300 | 150 |
| March | 300 | 600 | 0 | 0 | 500 | 400	 | 100 |
| April | 200 | 300 | 400 | 500	| 200 | 0 | 100 |
| May | 0 | 100 | 500 | 100 | 1000 | 300 | 0 |
| June | 500 | 500 | 100 | 300 | 1100 | 500 | 60 |

Up to 100 units of each product may be stored in inventory at a cost of $0.50 per unit per month. At the start of January there is no product inventory. However, by the end of June there should be 50 units of each product in inventory.

The factory produces product six days a week using two eight-hour shifts per day. It may be assumed that each month consists of 24 working days. Also, for the purposes of this model, there are no production sequencing issues that need to be taken into account.

What should the production plan look like?