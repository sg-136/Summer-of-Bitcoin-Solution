# Summer-of-Bitcoin-Solution

### Possible soution-1:
1. Check for the validity of given parent transaction id. Time complexity= O(N) where N=number of transactions in mempool file.
2. Check all the possible combinations from valid transactions. Time complexity= 2^N where N=number of transactions in mempool file.

Conclusion: Not a good approach.

### Possible soluton-2:
1. Take difference of fee and weight.
2. Arrange them in descending order. (Use of hashmaps for values of  fee, weight and transaction id's to keep track of total fee and total weight)

Conclusion: Though the leftover of weight is minimized but fee is not maximised (in this case total fee= 4773312, total weight= 3998988, total number of
transactions in final block= 3102)

### More better solution (Approach which I have used)
1. Selection of the transactions with highest value of fee/weight using a set.
2. Check whether the transaction is valid or not (according to the constraint that the parent transaction id should be included above it) using sets.
3. If the transaction is valid, it is included and fee and weight are updated.
4. If the transaction is not valid, go to the next higher transaction.

Conclusion: This is actually a greedy based algorithm problem and this approach minimises the leftover of weight and maximises the fee value, thus a good approach.
Time complexity: O(N^2) where N= number of transactions in mempool file.

### Other Information:
* Programming Language: C++
* Program File: code.cpp
* Final Output file: block.txt
* CSV file: mempool.csv
* Problem Statement: sb_README.pdf

### Results:
* Number of transactions in the final block: 3174
* Total fee in current block: 5696031
* Total Weight: 3999936

I have explained my code in the comments too (in the file code.cpp).
