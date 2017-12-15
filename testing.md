### Unit Testing

* Karma - is test runner
* Jasmine - is test framework

```
   $ npm install
   $ ng test
```


To test `compute.ts` create file named `compute.spec.ts`.

```
compute.ts
 export function compute(number) {
   if (number < 0) {
   return 0;
   }

   return number+1;
 }
```

```
compute.spec.ts
import { compute } from './compute'; 
describe('compute', () => {
	it('should return 0 if input negative',() =>{
		const result = compute(-1);
		expect(result).toBe(0);
	})
	it('should increment the input if it is positive',() =>{
		const result = compute(1);
		expect(result).toBe(2);
	})
})

```