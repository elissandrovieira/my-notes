# Catching and treating the `argv` numbers
- Numbers can be in more than one `argv`.
- If the numbers are in only one `argv`, I need split it.

# The turk algorithm

If the number pushed to STACK A is bigger than the biggest number into STACK B, or is lower than the lowest number, it should placed above the biggest number in the STACK B. In all other cases, I need to find the place for the number manually.

## The algorithm

```C
STACK A   STACK B
  ---       ---
 | 5 |     |   |
  ---       ---
 | 2 |     |   |
  ---       ---
 | 7 |     |   |
  ---       ---
 | 1 |     |   |
  ---       ---
 | 6 |     |   |
  ---       ---
 | 3 |     |   |
  ---       ---
 | 9 |     |   |
  ---       ---
 | 4 |     |   |
  ---       ---
 | 8 |     |   |
  ---       ---
 ```

I start pushing 2 numbers to STACK B

```C
STACK A   STACK B
  ---  -->  ---
 | 7 |---  | 2 |
  ---   |   ---
 | 1 |  -->| 5 |
  ---       ---
 | 6 |     |   |
  ---       ---
 | 3 |     |   |
  ---       ---
 | 9 |     |   |
  ---       ---
 | 4 |     |   |
  ---       ---
 | 8 |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 ```

After it, I need calculate the number that take smallest number of operations. If the first number take 1 or 2 operations, it is that takes smallest number of operations.

```C
STACK A   STACK B
  ---       ---
 | 7 |     | 5 | <-
  ---       ---   |
 | 1 |     | 2 | --
  ---       ---
 | 6 |     |   |
  ---       ---
 | 3 |     |   |
  ---       ---
 | 9 |     |   |
  ---       ---
 | 4 |     |   |
  ---       ---
 | 8 |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 ```
 
```C
STACK A   STACK B
  ---       ---
 | 1 | --> | 7 |
  ---       ---
 | 6 |     | 5 |
  ---       ---
 | 3 |     | 2 |
  ---       ---
 | 9 |     |   |
  ---       ---
 | 4 |     |   |
  ---       ---
 | 8 |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 ```

```C
STACK A   STACK B
  ---       ---
 | 6 | --> | 1 |
  ---       ---
 | 3 |     | 7 |
  ---       ---
 | 9 |     | 5 |
  ---       ---
 | 4 |     | 2 |
  ---       ---
 | 8 |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 ```

```C
STACK A   STACK B
  ---       ---
 | 6 | --> | 1 |
  ---       ---
 | 3 |     | 7 |
  ---       ---
 | 9 |     | 5 |
  ---       ---
 | 4 |     | 2 |
  ---       ---
 | 8 |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 |   |     |   |
  ---       ---
 ```

Now, I need calculate.

- **6:** It should be just above the number 5. It requires two times rotation of STACK B and one push from A to B. Wich means "3" operations are required.
- **3:**  It should be just above the number “2”. It requires one rotation of A, one reverse rotation of B and and one push from A to B. This would be “3” operations. The cheapest number is the number “6” for now.