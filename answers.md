# CMPS 2200 Assignment 4
## Answers

**Name:** Isaiah Kushner






- **1a.**   In a standard binary heap, the height is $log_2n$. Therefore, it makes sense that the depth ofa $d$-ary heap is $log_dn$.


- **1b.**   For insert, the work per level is constant $O(1)$, and the number of levels is $O(log_dn)$, therefore the total work is $O(log_dn)$.

For delete-min, the work per level is $O(d)$, while the number of levels is the same $O(log_dn)$, therefore the total work is $O(dlog_dn)$.


- **1c.**   $Total Work = (Cost of Delete-Min * |V|) + (Cost of Insert * |E|)$

Delete-Min term: $O(dlog_d|V|) * |V|$

Insert term: $O(log_d|V|) * |E|$

Total work: $O(|V|dlog_d|V|+|E|log_d|V|)$ or $O((d|V|+|E|)log_d|V|)$

- **1d.**   If $d = \frac{|E|}{|V|}$, we can substitute into work $O((\frac{|E|}{|V|}|V|+|E|)log_{|E|/|V|}|V|)$

$O(2|E|log_{|E|/|V|}|V|)$

$\frac{|E|}{|V|}=\frac{|V|^{1+\epsilon}}{|V|}=|V|^\epsilon$

$log_{|V|^\epsilon}|V|=\frac{1}{\epsilon}$

$Work=O(|E|)$


- **2a.**
k=0

APSP(0,0,0) = 0

APSP(0,1,0) = -2

APSP(0,2,0) = 2

APSP(1,0,0) = -2

APSP(1,1,0) = 0

APSP(1,2,0) = 0

APSP(2,0,0) = 2

APSP(2,1,0) = 0

APSP(2,2,0) = 0

k=1

APSP(0,0,1) = 0

APSP(0,1,1) = -2

APSP(0,2,1) = 1

APSP(1,0,1) = -2

APSP(1,1,1) = 0

APSP(1,2,1) = 0

APSP(2,0,1) = -1

APSP(2,1,1) = 0

APSP(2,2,1) = 0

k=2

APSP(0,0,2) = 0

APSP(0,1,2) = -2

APSP(0,2,2) = 1

APSP(1,0,2) = -2

APSP(1,1,2) = 0

APSP(1,2,2) = 0

APSP(2,0,2) = -1

APSP(2,1,2) = 0

APSP(2,2,2) = 0


- **2b.**   Yes. APSP(i,j,2)=APSP(i,j,1)

$APSP(i,j,2)=min(APSP(i,j,1), APSP(i,2,1)+APSP(2,j,1))$

- **2c.**   $APSP(i,j,k)=min(APSP(i,j,k-1),APSP(i,k,k-1)+APSP(k,j,k-1))$

- **2d.**   There are $|V| * |V| * |V|$ or $|V|^3$ subproblems. Therefore, the work is $O(|V|^3)$

- **2e.**   Johnson's algorithm has a work of $O(|V|*|E|log|V|)$. Our algorithm is preferable in dense graphs where the number of edges approaches $|V|^2$, and it is easier to implement.



- **3a.**   Yes. Let $T$ be an MST. Let $e$ be the edge with the maximum weight in $T$, with weight $w(e)$.

If $e$ is removed, the tree splits into Set $A$ and Set $B$.

Suppose there exists a different tree, $T'$, where every edge has weight less than $w(e)$.

In order for $T'$ to be valid, it must connect $A$ and $B$. Therefore, there must be an edge $e'$ that connects $A$ and $B$.

Therefore, $w(e') < w(e)$. But if this were true, the algorithm would have picked this edge in the first place. 

Therefore, no tree with a smaller maximum edge can exist.


- **3b.**   Starting with the optimal MST, iterate through every edge in the graph that is currently not part of T. For each non-tree edge, imagine adding it to T and find the maximum weight edge on that cycle (excluding the one just added). Determine how much the total weight would increase if this change was made. Select the smallest increase in total weight. This would be the second most optimal tree.


- **3c.**   $O(|E||V|)$
