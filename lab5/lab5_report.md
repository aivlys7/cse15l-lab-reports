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

![Image](



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


# Part 2
`grep` command:

<p> </p>
1) `-r` or `-recursive`: it search for a pattern recursively in a directory.

```java
grep -r "functionName" ./technical
```
This command line search for the files in the technical directory with the string "functionname".

```java
grep -r "^#include" ./technical
```
This command line search for the lines in the technical directory, which are starting from "#include".

<p> </p>
2) `-i` or `--ignore-case`

```java
grep -i "Main" ./technical/main.c
```
This command line search for the string "Main" in the main.c under techincal directory, ignoring the case.

```java
grep -ir "error" ./technical/logs/
```
This command line search for the string "error" under the logs directory under technical directory, ignoring the case.

<p> </p>
3) `-l` or `--files-with-matches`

```java
grep -l "config" ./technical/configs/*
```
This command line search for the string "config" and list only the name of the files.

```java
grep -lr "TODO" ./technical/src/
```
This command line search for the string "TODO" under technical/src/ directory and list the name of the files.

<p> </p>
4) `-n` or `--line-number`

```java
grep -n "return" ./technical/module.c
```
This command line search for the word "return" under technical/module.c directory prefixes each matching line with its line number in the file.

```java
grep -rn "FIXME" ./technical/
```
This command line search for the word "FIXME" under technical directory, and print each match with its line number.


