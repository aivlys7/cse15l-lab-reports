# Part 1
The method I chose is `reservesInPlace`.
<p> </p>

![Image](reverseInPlace.png)

<p>A failure-inducing input would be like:</p>

```java
@Test
  public void testReverseInPlaceFailure() {
    int[] originalArray = {1, 2, 3, 4};
    ArrayExamples.reverseInPlace(originalArray);
    assertArrayEquals(new int[]{4, 3, 2, 1}, originalArray);
  }
}
```

<p>A non-failure-inducing input would be like:</p>

```java
  @Test
  public void testReverseInPlaceSingleElement() {
    int[] originalArray = {1};
    ArrayExamples.reverseInPlace(originalArray);
    // This will pass because reversing a single-element array results in the same array
    assertArrayEquals(new int[]{1}, originalArray);
  }
}
```

<p>The symptom:</p>



<p>The bug before and after the fix:</p>

```java
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length; i += 1) {
    arr[i] = arr[arr.length - i - 1];
  }
}
```

```java
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length / 2; i += 1) {
    int temp = arr[i];
    arr[i] = arr[arr.length - i - 1];
    arr[arr.length - i - 1] = temp;
  }
}
```

<p>Why the fix adress the issue:</p>
<p>The bug in the original code is that the it incorrectly assigns the value of the end of the array to the beginning.</p>
<p>The fix creates a temp array, so that it can preserve the data in the orginal array from earsing or replacing by other data.</p>


