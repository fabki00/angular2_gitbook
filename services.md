### Services 

[Article explaining Reactive Programming](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754): explains what Observables are.

**Reactive Programming** (RP) - using Observables to structure data architecture. RP allows to work with asynchronous data streams. 

**Observables** - main data structure to implement RP.

**Promises** - asynchronous technique for returning data without waiting for the server response. Promise will call back when the results are ready. 
- ask asynchronous service to do work and give it callback function. The service does the work and calls the function returning results or an error. 

- arrow function - sipmpler syntax than function expression; best suited for non-method functions; cannont be used as constructors. Arrow functions work as lambdas in Python. 

Simpler syntax:
instead of classic function:
``` 
function( inputVar) {
	return outputVar;
}
```
we can write:
```
inputVar => outputVar;
```