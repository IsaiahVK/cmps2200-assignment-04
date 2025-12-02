# CMPS 2200 Assignment 4
## Answers

**Name:** Isaiah Kushner






- **1a.**   In a standard binary heap, the height is $log_2n$. Therefore, it makes sense that the depth ofa $d$-ary heap is $log_dn$.


- **1b.**   For insert, the work per level is constant $O(1)$, and the number of levels is $O(log_dn)$, therefore the total work is $O(log_dn)$.

For delete-min, the work per level is $O(d)$, while the number of levels is the same $O(log_dn)$, therefore the total work is $O(dlog_dn)$.


- **1c.**   $Total Work = (Cost of Delete-Min * |V|) + (Cost of Decrease-Key * |E|)$

Delete-Min term: $O(dlog_d|V|) * |V|$

Decrease-Key term: $O(log_d|V|) * |E|$

Total work: $O(|V|dlog_d|V|+|E|log_d|V|)$ or $O((d|V|+|E|)log_d|V|)$

- **1d.**


- **2a.**


- **2b.**


- **2c.**

- **2d.**

- **2e.**



- **3a.**


- **3b.**


- **3c.**
