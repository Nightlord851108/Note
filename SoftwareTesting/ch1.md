# Ch1 Introduction

## Fault and Failure example
- Software Failures: The software behavior doesn't match the requirement.
- Software Error: Incorrect internal state which is manifestation of some fault. (e.g. Exception)
- Software Fault: There's a bug.


** Software do not degrade.

**Software faults were there at the beginning and do not "appear" when a part wears out.**

### Example
```
public static int numZero (int[] arr) {
  int count = 0;
  for (int i = 1; i < arr.length; i++) {
    if (arr[i] == 0) {
      count ++;
    }
  }
  return count;
}
```

***Fault***: Should start with 0 instead of 1.

**Test1**:
Test data:
```
arr = [2, 7, 0]
Expected: 1
Actual: 1
```
- Error: i is 1, not 0, on the first iteration
- Failure: None

**Test2**
```
arr = [0, 2, 7]
Expected: 1
Actual: 1
```
- Error: i is 1, not 0, on the first iteration
- Failure: count is 0 at return statement



## Validation & Verification
- Validation : Evaluating software and requirement. *Do we build the right product.*<br/>
  (Specification By Example)
- Verification: Testing. *Do we build the product right?*

**IV&V**: "Independent verification and validation"- to ask a third part department for doing verification and validation testing.

## Testing Goals Based on Test Process Maturity
- Level 0: No different between **testing and debugging**
- Level 1: Show **Correctness**
- Level 2: Show the **software doesn't work**
- Level 3: To **Reduce the risk** of using the software; not to prove specific thing.
- Level 4: It's a **mental discipline** that helps all IT professional develop high quality software.

## The goal of testing
