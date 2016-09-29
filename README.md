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
| Vertical drilling | Content column 2 | Content column 1 | Content column 2 | Content column 1 | Content column 2 | Content column 1 | Content column 2 |
| Horizontal drilling | Content column 2 | Content column 1 | Content column 2 | Content column 1 | Content column 2 | Content column 1 | Content column 2 |
| Boring | Content column 2 | Content column 1 | Content column 2 | Content column 1 | Content column 2 | Content column 1 | Content column 2 |
| Planing | Content column 2 | Content column 1 | Content column 2 | Content column 1 | Content column 2 | Content column 1 | Content column 2 |

In each of the six months covered by this model, one or more of the machines is scheduled to be down for maintenance and as a result will not be available to use for production that month. The maintenance schedule is as follows:

There limitations to how many of each product can be sold in a given month. These limits are shown below:

Up to 100 units of each product may be stored in inventory at a cost of $0.50 per unit per month. At the start of January there is no product inventory. However, by the end of June there should be 50 units of each product in inventory.

The factory produces product six days a week using two eight-hour shifts per day. It may be assumed that each month consists of 24 working days. Also, for the purposes of this model, there are no production sequencing issues that need to be taken into account.

What should the production plan look like? Also, recommend any price increases and identify the value of acquiring any new machines.

This problem is based on a larger model built for the Cornish engineering company of Holman Brothers.