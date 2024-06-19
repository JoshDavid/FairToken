Experimental fooling around with fair mutexes... more of a playground than actual library at the moment

These TGETs are Fair and FIFO -- first thread that requested the token gets it. 

`Tests.RunStarvation ''` to see Starvation with vanilla ⎕TGET in action

`Tests.RunFairTest ''` to see how Fair Tokens are used to ensure FIFO on requests.

What to watch in both of these tests: How we have 1 thread waiting for a token at the end, and we create a new thread that waits for the same token. In the first test, the thread that was created last gets the token (conducive to starvation). In the second test, the earliest thread waiting for the token receives it first. 

N.B. TGET on multiple tokens at a time has not been implemented, let alone thought about in this library. But I don't think it will be extremely difficult. 

Priorities can probably easily be baked into this as well. 
