PlannedPendingOrders (MQL4 Script)
==================================
Create limit orders depending on horziontal lines you have set in the chart
and based on an aspired risk you can change.
For an introduction with screenshots go here: https://www.mql5.com/en/code/21804

Installation
------------

Copy the script file into the Scripts folder inside your Metatrader folder.

Example:
+ Assuming your Metatrader is
installed into the folder **C:\Program Files\Metatrader**
+ Copy the script
into **C:\Program Files\Metatrader\MQL4\Scripts**

Open the script in the Metaeditor and compile it.

In Metatrader you will see the script then inside the Navigator window under
the node Scripts.

Use
---

### Creating lines

For using the script you need to create horizontal lines in the chart and
give them special names. Following are the names you need to use (number at
the end must be between 1 and 4):

+ **entry_1** (entry price for the first order and all orders where entry not
              set)
+ **sl_1**    (stoploss for the first order and all order where stoploss not
              set)
+ tp_1    (optional, if set only applies to order 1, the takeprofits of all
          other orders need to be set manually)

For example to enter two orders (one order with no takeprofit set) it is
enough to define the following lines:

+ entry_1
+ sl_1
+ tp_2

### Execute

Drag and drop the script on the chart where you have created the lines.

For the example (lines entry_1, sl_1 and tp_2 are set) the required parameters
are given and leading to order 1 has an entry and a stoploss level (no
takeprofit). For order 2 only the takeprofit is set by the user, here the
entry and the stoploss is taken over from order 1. Based on this automatic
completion the risk estimation and required margin calculation is made.

### Check data

A message box is opening with information about the order to be entered:
+ Estimated risk in account currency and percentage of account balance 
+ Risk-Reward-Ratio
+ Required margin

The estimation of risk may vary during the orders are open if the account
currency and the derivate's base currency are not same. Swap is not included
in the calculation. Also margin calculation can differ to reality if your
broker will adjust the margin requirements while orders already open.

If you are fine with the information about the trade press OK and the orders
will be opened. Press Cancel and the orders will not be opened.

### Optional

Set alerts on the takeprofit levels as a reminder to pull the stoploss
tighter. But for this to work properly the Metatrader where you set the alert
levels needs to run 24/7. Also if you do not want to spend all the time home
waiting on the alert rings, you should connect your mobile to the running
Metatrader and create message sending alerts.
