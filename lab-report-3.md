# Lab Report 3
**By: Wilson Zhu**

**Part 1:**

Failure-inducing input: <br>
```
@Test
  public void avgwolowest5() {
    double[] input1 = {2,2,4,4,5};
    assertEquals(3.75, ArrayExamples.averageWithoutLowest(input1),0.01);
  }
```
No Failure: <br>
```
  @Test
  public void avgwolowest4() {
    double[] input1 = {1.5,3.2,6.6,8.4,2,9,7.7};
    assertEquals(6.15, ArrayExamples.averageWithoutLowest(input1),0.01);
  }
```
JUnit output: <br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/f5542fb1-ce13-4f5c-924f-e60ef909301f)

Code before fix: <br>

```
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { 
      return 0.0; 
    }
    double lowest = arr[0];

    for(double num: arr) {
      if(num < lowest) {
         lowest = num; 
        }
    }
    double sum = 0;
    
    for(double num: arr) {
      if(num != lowest) { 
        sum += num; 
      }
    }
    return sum / (arr.length - 1);
  }
``` 

Code after fix: <br>
```
 static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { 
      return 0.0; 
    }
    double lowest = arr[0];
    int lowestInd = 0;

    for(int i = 0; i < arr.length;i++) {
      if(arr[i] < lowest) {
         lowest = arr[i];
         lowestInd = i; 
        }
    }

    double sum = 0;

    for(int i = 0; i < arr.length;i++) {
      if(i != lowestInd) { 
        sum += arr[i]; 
      }
    }
    return sum / (arr.length - 1);
  }
```
The fix addressed the issue of the code truncating all of lowest numbers rather than one instance of the lowest number. In my case, if the input was `2,2,4,4,5`, it would truncate both 2's rather than just one. The fix I've implemented would send all inputs to an array and then it will compare all elements of the array, searching for the index containing the lowest number. This way, only 1 of the lowest is truncated and the other is kept. 


read week 5
extremely sleep deprived
