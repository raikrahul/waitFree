# Issues with Locks 

### Deadlocks 

* One must acquire locks in order 
* Thread Set T, Lock Set L. Between the thread Set T, all the threads want the same locks L which are locked by the threads T
* _Locks are not composable_ => Cannot find Ordering of subsets in T inside S, which will make system never deadlock 




