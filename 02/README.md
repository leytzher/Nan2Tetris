# Implementation Notes - Chapter 2.

## De Morgan's Law

```
NOT(A+B) = NOT(A).NOT(B)   or   NOT(A OR B) = NOT(A) AND NOT(B)

NOT(A.B) = NOT(A)+NOT(B)   or   NOT(A AND B) = NOT(A) OR NOT(B)
```


## Half Adder

This circuit uses and XOR for the sum and an AND for the carry bit.

This circuit is not able to handle operations like 1+1+(carry 1). For that we need a full adder.
![Half Adder](img/img8.png)
Note that in the Half Adder the sum is given by the XOR and the carry is given by the AND.

```
|   a   |   b   |  sum  | carry |
|   0   |   0   |   0   |   0   |
|   0   |   1   |   1   |   0   |
|   1   |   0   |   1   |   0   |
|   1   |   1   |   0   |   1   |


```
## Full Adder
This circuit is built with 2 Half adders and 1 OR gate.

We use the sum output of the 1st Half Adder (XOR) and the Carry In as inputs for the 2nd Half Adder. The output of this will be the sum (XOR).

For the carry out bit, we combine the carry bit of the first Half adder with the carry bit of the 2nd half adder.


![Full Adder](img/img9.png)

```
|   a   |   b   |   c   |  sum  | carry |
|   0   |   0   |   0   |   0   |   0   |
|   0   |   0   |   1   |   1   |   0   |
|   0   |   1   |   0   |   1   |   0   |
|   0   |   1   |   1   |   0   |   1   |
|   1   |   0   |   0   |   1   |   0   |
|   1   |   0   |   1   |   0   |   1   |
|   1   |   1   |   0   |   0   |   1   |
|   1   |   1   |   1   |   1   |   1   |
```
