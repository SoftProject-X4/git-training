# Git Training
A Repository for git trainings to try working in collaboration with a remote Repository.

## Howto do the exercise?

1. Checkout the master branch
2. Build 3 - 4 small teams (a team can be a single person as well)
3. Each Team should do one of the exercises in a feature branch. Don't do one excercise twice.
4. Bring everything together in a release branch. Be sure that won't be easy. Talk with each other!

## Team exercises

Here are the things each team should do in their feature branch.

### Team 1

**Take care of the data**

You should check the data.xml file. There is a typo in the second row Tag, be sure everything is in small case. In the first row the zip is missing. You find the correct one in row two.

Add two new Rows with data

```xml
<row>
	<name>Baggins</name>
	<surname>Bilbo</surname>
	<address>
		<street>Bag End</street>
		<town>Hobbiton</town>
	</address>
</row>
<row>
	<name>Baggins</name>
	<surname>Frodo</surname>
	<address>
		<street>Bag End</street>
		<town>Hobbiton</town>
	</address>
</row>
```

### Team 2

**Do some Code**

Check the aSorceFile.txt. There is a nice pseudocode implementation. Let's add another one. Insert the following code **above** the existing code.

```java
public static long ackermann( long n, long m ) {
  if ( n == 0 )
    return m + 1;
  else
    if ( m == 0 )
      return ackermann( n - 1, 1 );
    else
      return ackermann( n - 1, ackermann(n, m - 1) );
}
```

Create a new file for a new implementation named "algorithm.txt" in the src folder. Add the follwoing content:

```java
public class Quicksort  {
    private int[] numbers;
    private int number;

    public void sort(int[] values) {
        // check for empty or null array
        if (values ==null || values.length==0){
            return;
        }
        this.numbers = values;
        number = values.length;
        quicksort(0, number - 1);
    }

    private void quicksort(int low, int high) {
        int i = low, j = high;
        // Get the pivot element from the middle of the list
        int pivot = numbers[low + (high-low)/2];

        // Divide into two lists
        while (i <= j) {
            // If the current value from the left list is smaller than the pivot
            // element then get the next element from the left list
            while (numbers[i] < pivot) {
                i++;
            }
            // If the current value from the right list is larger than the pivot
            // element then get the next element from the right list
            while (numbers[j] > pivot) {
                j--;
            }

            // If we have found a value in the left list which is larger than
            // the pivot element and if we have found a value in the right list
            // which is smaller than the pivot element then we exchange the
            // values.
            // As we are done we can increase i and j
            if (i <= j) {
                exchange(i, j);
                i++;
                j--;
            }
        }
        // Recursion
        if (low < j)
            quicksort(low, j);
        if (i < high)
            quicksort(i, high);
    }

    private void exchange(int i, int j) {
        int temp = numbers[i];
        numbers[i] = numbers[j];
        numbers[j] = temp;
    }
}
```

### Team 3

**The genius**

There was an error in the data.xml. Delete the second row it is worng data!

Create a new file for a new implementation named "algorithm.txt" in the src folder. Add the follwoing content:

```java
public class Quicksort  {
    private int[] numbers;
    private int number;

    public void sort(int[] values) {
        // check for empty or null array
        if (values ==null || values.length==0){
            return;
        }
        this.numbers = values;
        number = values.length;
        quicksort(0, number - 1);
    }

    private void exchange(int i, int j) {
        int temp = numbers[i];
        numbers[i] = numbers[j];
        numbers[j] = temp;
    }

    private void quicksort(int low, int high) {
        int i = low, j = high;
        // Get the pivot element from the middle of the list
        int pivot = numbers[low + (high-low)/2];

        // Divide into two lists
        while (i <= j) {
            // If the current value from the left list is smaller than the pivot
            // element then get the next element from the left list
            while (numbers[i] < pivot) {
                i++;
            }
            // If the current value from the right list is larger than the pivot
            // element then get the next element from the right list
            while (numbers[j] > pivot) {
                j--;
            }

            // If we have found a value in the left list which is larger than
            // the pivot element and if we have found a value in the right list
            // which is smaller than the pivot element then we exchange the
            // values.
            // As we are done we can increase i and j
            if (i <= j) {
                exchange(i, j);
                i++;
                j--;
            }
        }
        // Recursion
        if (low < j)
            quicksort(low, j);
        if (i < high)
            quicksort(i, high);
    }
}
```

### Team 4 (optional)
**If we are more people we should parallelize**

You should check the data.xml file. There is a typo in the second row Tag, be sure everything is in small case.

Check the aSorceFile.txt. There is a nice pseudocode implementation. Let's add another one. Insert the following code **above** the existing code.

```java
public static long ackermann( long n, long m ) {
  if ( n == 0 )
    return m + 1;
  else
    if ( m != 0 )
      return ackermann( n - 1, ackermann(n, m - 1) );
    else
      return ackermann( n - 1, 1 );
}
```
