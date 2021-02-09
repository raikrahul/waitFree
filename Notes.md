# Issues with Locks 
_Your enemy is data sharing, not the locks!_

### Deadlocks 

* One must acquire locks in order [ IT SLOWS DOWN THE FAST THREADS ] 
https://en.wikipedia.org/wiki/Lock_convoy

* Thread Set T, Lock Set L. Between the thread Set T, all the threads want the same locks L which are locked by the threads T
* _Locks are not composable_ => Cannot find Ordering of subsets in T inside S, which will make system never deadlock 

### Livelock 
* How does one have live lock without the livelocks? 
  
  
### Priority Inversion 
* Low priority thread never gets the lock 

### Signal Handling & Shared Memory 
* `malloc` inside signal handler will always deadlock 
* Shared Memory - Spinlock or Mutex? 
* Process N+1 will wait forever if the Process N died, and non Process from 1...N, makes process 


### Partially Lock Free Data Structures + Thread Safe 

* Thraed Safe Classes - _multiple threads may call on the shared objects_
* Basic Base Thread Assurance - Have `const` function call, only that assures 
* Weak Assurance - Another object of that type in another thread - Design for use for only one thread 
* Multiple type of the derived at the same time in other threads 

_Why internal locking is rarely assured?_

* STL Will give basic thread assurance - Multiple threads can call `const` functions 
* *READ ONLY != CONST* 
* *Per object locks != per type locks*
  
  
  --------------------------------------------------------------------------------------------------------------------------------------------------------
  --------------------------------------------------------------------------------------------------------------------------------------------------------
  
  * Internal Locking - Transcation are wrong in the API
  * Not just useful to be thread safe 


```template <typename T>
T CAS(T& value, T expected, T newVal)
{

 T temp = value; 
 if ( temp == expected ) value = newVal; 
 return temp;
 }
 
 ```
 
