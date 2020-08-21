#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a)  Linear 
    O(n)
    n^3 / n ^2 == n 
    Resulting in n operations being ran no matter how big n is.
   <!-- still unsure about answer, might be O(n^3).. I think of O(N^2) also being O(n^3), O(n^4) and so on. O(N^2) is always bound under O(n^3), therefore O(n^2) is indeed O(n^3) or O(n). -->

b)  Log-logarithmic 
(Amortized time per operation using a bounded priority que, The motivation for amortized analysis is that looking at the worst-case run time per operation, rather than per algorithm, can be too pessimistic.)

   O(n log n) 
 but if O(n^2), then it's jsut O(n) due to it being tight upper bound and that is what we should use in time complexity derivation of algorithims. If we use ^2 or ^3 we are misusing the Big-O notation however i'm pretty sure it's O(n log n) and this is only because there are nested loops. The outer for loop will run n times and the inner while loop will run log(n) times. The inner loop  has a log(n) time complexity because of the value of j doubles(power of 2) with each cycle so j will increase quadradically & only take log(n) iterations to reach the value of n.
 If something is inside of our forloop, we just multiply
    So we have:
    O(n) * O(1) *O( log n) * O(1) ~ O(n) * O(log n) = O(n log n)
    ```python
    sum = 0  # O(1) - space
    for i in range(n): #O(n) - time 
      j = 1 # O(1) - space 
      while j < n: # O(log n) J increases exponentially so it gets to its target faster. - time 
        j *= 2 - time
        sum += 1 # O(1) - space
    ```


c)  Linear
    O(n) 
(although the return of recursive function confuses me slightly) it just seems to add 2 to the return value each time. Since adding 2 to another is a constant time operation, and it's done 'n' times the final run time complexity is O(n)

## Exercise II

UPER

Understand - They want us to use a search algorithim to determine when the egg will break when it reaches f floor while using the minimal amount of eggs (dropped + break)
since we don't know n-stories or f floors, we can't assume the size so for all we know n and f can be very high or low values. 
For effeciency sake, and assuming we have a high number of f and n to work with, the binary search or O(log n) algorithim would be most effecient here.

if we used O(n) or a linear approach, we would drop one egg per floor until we reached the one floor that broke the egg, resulting in 1 broken egg but potentially a mass amount of dropped eggs. Since the goal is to minimize both dropped and broken eggs, it's safe to say despite size, O(log n) is a more effecient solution for this type of problem.

In this problem, we assume the floors are sorted in acending format as is typically the case.

Plan - we want to drop the egg from the middle, and determine its left or right values. It should take no more than 9 guesses on average if we use the binary search approach eliminating whole left/right sides until we reach our desired floor, in which case we can return -1 to return the floor prior once the algorithim completes.

Execute -
    (word answer so no code needed)

Reflect - O(n) or linear was the first thought, however since they specified they want us to minimize the number of eggs dropped as well as broken, binary would be optimal in this regard. Else, a linear approach would be more optmial if we only cared about minmizing broken eggs. So the optimal solution would be a run time complexity of O(log(n)) or binary search from middle - left >< right/collapse.


