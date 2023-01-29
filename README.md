# soda-test code snippets

## Basics

| Prefix | Description |
| ------ | ----------- |
| !basicsample soda-test | The following code is a sample for a test that checks that 1+1 is 2 |

```
import { expect, describe, it, TR } from 'soda-test'

@describe('Basic Sample')
class SampleCase {

   @it('validates that 1+1 is 2')
   sampleStep(): TR {
       expect(1+1).to.equal(2)
   }
}
```
## Control Flow Methods
| Prefix | Description |
| ------ | ----------- |
| !before soda-test | this method will be executed during test-run once, before running any of the test-step methods |
| !beforeEach soda-test | this method will be executed during test-run, before running each of the test-step methods |
| !afterEach soda-test | this method will be executed during test-run, after running each of the test-step methods |
| !after soda-test | this method will be exeucted during test-run once, after runnig all of the test-step methods |



```
before(): void {
   console.log('***before')
}

```

```
beforeEach(): void {
   console.log('***beforeEach')
}

```

```
afterEach(): void {
   console.log('***afterEach')
}

```
```
after(): void {
   console.log('***after')
}

```

## Spy method

| Prefix | Description |
| ------ | ----------- |
| !spy method on object soda-test | In this example we want to call the foo method, and validate the call to console.log. Note that log is a method defined in the console object. We need to create a 'spy' on this method. In the test-step method, define an argument of type SinonSpy. To make this argument become a spy object, we need to add decorator to the argument called spy and give to the decorator 2 arguments: the object the method to spy is on it, and the name of the method to spy |

```
@it('should spy on log')
logSpy( @spy(console, 'log') console_log_spy: SinonSpy ): TR {
   foo()
   expect(console_log_spy.calledOnce).to.be.true
   expect(console_log_spy).to.have.been.calledOnce
}

```

