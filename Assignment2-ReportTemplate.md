**SENG 637 - Dependability and Reliability of Software Systems**

**Lab. Report \#2 – Requirements-Based Test Generation**

| Group \#:      |     |
| -------------- | --- |
| Student Names: |     |
| Graydon Hall   | 30142310 |
|                |     |
|                |     |

# 1 Introduction

Text…

# 2 Detailed description of unit test strategy
### DataUtilities class methods
Method: `createNumberArray()`
* The purpose of this method: It constructs an array of Number objects from an array of double primitives.
* This class was tested by creating various types of double arrays to be used as inputs, and then
comparing them with the corresponding output to ensure the Number[] array was created properly. 
* The following cases were identified:
  * test basic valid input
  * checking for rounding errors 
  * empty arrays
  * extremely large value

### Range class methods
Method: `CombineIgnoringNaN()`
* The purpose of this method: It returns a new range that spans both range1 and range2. 
This method has a special handling to ignore Double.NaN values.
* For each range, we have an upper and lower bound, either of which can be Double.NaN for this function
* We will execute 5 tests
  * one with no Double.NaN values
  * every other test will have one Double.NaN value, (ex. upper bound of range 1)
  * For each test, we will test with a valid value in the newly created range.
* This is an example of weak combinatorial testing
  * there are 4 factors that can either be a number, or Not a Number
  * To test all cases exhaustively would be 2^4=16  tests 
  * Instead we take a weak approach, and test each affect independently 

Method: `expandToInclude()`
* The purpose of this method: It returns a range that includes all the values in the 
specified range AND the specified value 
* To test this, we start with a valid range between -1 and 1
* We test 2 cases: expanding the range up and down
* For each of these cases, we define partitions, and apply boundary value testing as follows<br>
![](images/expandToIncludeRangeImage.png)<br>

# 3 Test cases developed

### Classes for testing methods of DataUtilities class
Class: `createNumberArrayTest`
* This class corresponds to the `createNumberArray()` method
* methods:
  * `testIdenticalArrays()`: ensure a basic double array gets converted to a Number array properly
  * `testNonIdenticalArrays()`: checks that no rounding errors occur when creating the new array
  * `testEmptyArraysSameLength()`: ensures empty array of correct length is created
  * `testEmptyArraysDifferentLength()`: ensures empty array created does not have the wrong length
  * `testLargeValues()`: ensures correct behavior when extremely large values are used

### Classes for testing methods of Range class
Class: `CombineIgnoringNaNTest`
* This class corresponds to the `CombineIgnoringNaN()` method
* methods: 
  * `testNoNaNs()`: test combined range with no NaNs present
  * `testR1LbNaN()`: test combined range with range 1 lower bound NaN
  * `testR1UbNaN()`: test combined range with range 1 upper bound NaN
  * `testR2LbNaN()`: test combined range with range 2 lower bound NaN
  * `testR2UbNaN()`: test combined range with range 2 u bound NaN

Class: `ExpandToIncludeTest`
* This class corresponds to the `expandToInclude()` method
* Methods: 
  * `expandUpNominal()`: expand range up, test nominal value
  * `expandUpBUB()`: expand range up, test below upper bound
  * `expandUpUB()`: expand range up, test Upper Bound
  * `expandUpAUB()`: expand range up, test above upper bound
  * `expandDownNominal()`: expand range down, test nominal value
  * `expandDownALB()`: expand range down, test Above lower bound
  * `expandDownLB()`: expand range down, test lower bound
  * `expandDownBLB()`: expand range down, test below lower bound

# 4 How the team work/effort was divided and managed

Text…

# 5 Difficulties encountered, challenges overcome, and lessons learned

Text…

# 6 Comments/feedback on the lab itself

Text…
