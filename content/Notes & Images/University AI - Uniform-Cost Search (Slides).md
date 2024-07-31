## Algorithm for uniform cost search:
-   Insert the root node into the priority queue
-   _Repeat while the queue is not empty:_
    Remove the element with the highest priority
    _If the removed node is the destination,_ print total cost and stop the algorithm
    _Else_, enqueue all the children of the current node to the priority queue, with their cumulative cost from the root as priority

![[Pasted image 20220821202024.png]]
