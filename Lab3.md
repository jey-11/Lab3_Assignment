![image](https://github.com/jey-11/Lab3_Assignment/assets/137555229/ea61406c-96f5-4f0f-bc4e-51e11811a216)**Part 1**
Bug: in reverseInPlace method- the spots must be swapped but 
*A failure-inducing input for the buggy program, as a JUnit test and any associated code* <br>
  @Test <br>
  public void testArrayExamplesOG(){ <br>
    //bugs in reverse in place method <br>
    int[] arr1 = {1,2,3}; <br>
    ArrayExamples.reverseInPlaceOG(arr1); <br>
    int[] exparr1 = {3,2,1}; <br>
    assertArrayEquals(exparr1, arr1); <br>
  } <br>

*An input that doesn’t induce a failure, as a JUnit test and any associated code <br>*
	@Test <br>
	public void testReverseInPlace() { <br>
    int[] input1 = { 3 }; <br>
    ArrayExamples.reverseInPlace(input1); <br>
    assertArrayEquals(new int[]{ 3 }, input1); <br>
	} <br>

*The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)*
![Image](Lab3_Symptom.png)<br>

*The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)*
  original code <br>
  static void reverseInPlaceOG(int[] arr) { <br>
    for(int i = 0; i < arr.length; i += 1) { <br>
      arr[i] = arr[arr.length - i - 1]; <br>
    } <br>
  }<br>

*after code*
  static void reverseInPlace(int[] arr) <br>
    int temp = 0; <br>
    for(int i = 0; i < arr.length/2; i += 1) { <br>
      temp = arr[i]; <br>
      arr[i] = arr[arr.length - i - 1]; <br>
      arr[arr.length-i-1] = temp; <br>
    } <br>
  } <br>
The fix addresses the bug because a temporary variable is used to store a given value, therefore the value will not be lost. Also, since the fist half/second half are being swapped the loop only iterates to the arr.length/2

  **Part 2**
  *4 implementations of grep with two examples for each implementation* <br>
  1. -v to display the non matching files <br>
![Image](Lab3_P2_-v1.png)<br>
![Image](Lab3_P2_-v2.png)<br>
  2. -q to cause the grep to go silent (not release an output) <br>
![Image](Lab3_P2_-q1.png)<br>
![Image](Lab3_P2_-q2.png)<br>
  3. -r recursive searches through nested directories <br>
![Image](Lab3_P2_-r2.png)<br>
![Image](Lab3_P2_-r1.png)<br>
  4. -i ignores case <br>
![Image](Lab3_P2_-i1.png)<br>
![Image](Lab3_P2_-i2.png)<br>
