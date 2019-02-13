#	Sorting Techniques

-----------------------------------------------
## Quick Sort Algorithm

### What is Heap sort algorithm?

-	Heap sort is a comparison-based sorting algorithm
-	Heap sort can be thought of as an improved selection sort
-	It divides its input into a sorted and an unsorted region,
-	And it iteratively shrinks the unsorted region by extracting the largest element and moving that to the sorted region

The improvement consists of the use of a heap data structure rather than a linear-time search to find the maximum

## What are properties of Heap sort?

-	Not stable
-	O(1) extra space
-	O(n·lg(n)) time
-	Not really adaptive

## What is performance of Heap sort?

-	Worst-case performance	O(nlog n)
-	Best-case performance	O(nlog n)
-	Average performance	O(nlog n)
-	Worst-case space complexity	O(1) auxiliary

### Pivot

-	Pivot is an item that we are going to compare with every other item
-	Elements lesser than Pivot are moved to left of Pivot and greater than are moved to right of Pivot
-	Quick Sort is Recursive 
-	Quick sort uses Divide and Conquer Algorithm
-	Very efficient for large data sets
-	Worst Case of Quick Sort is O(n^2)
-	Average Case of Quick Sort is O(n log n)
-	Performance of Quick Sort Highly depends on Selection of Pivot


	Code Snippet:
		
		package sorting;

		import java.util.Arrays;

		public class QuickSortDemo {

			public class QuickSort {
				private int[] array;
				private int length;

				public int[] sort(int array[]) {
					if (array != null && array.length < 1) {
						return array;
					}

					this.array = array;
					this.length = array.length;

					quicksort(0, length - 1);
					return this.array;
				}

				private void quicksort(int low, int high) {
					if (low < high) {
						int splitPoint = partion(low, high);
						quicksort(low, splitPoint - 1);
						quicksort(splitPoint + 1, high);
					}
				}

				private int partion(int low, int high) {
					int pivot = this.array[low];
					int leftmark = low + 1;
					int rightmark = high;

					boolean isDone = true;
					while (isDone) {

						while (array[leftmark] <= pivot && leftmark <= rightmark) {
							leftmark++;
						}

						while (array[rightmark] >= pivot && rightmark >= leftmark) {
							rightmark--;
						}

						if (rightmark < leftmark) {
							isDone = false;
						} else {
							swap(leftmark, rightmark);
						}
					}

					swap(low, rightmark);
					return rightmark;
				}

				private void swap(int i, int j) {
					int temp = this.array[i];
					this.array[i] = this.array[j];
					this.array[j] = temp;
				}

			}

			public static void main(String[] args) {
				QuickSort qs = new QuickSortDemo().new QuickSort();
				int array[] = { 54, 26, 93, 999,17, 77, 31, 44, 55, 20,10,89,7,1,66,1000,8988,888 };
		//		 12, 16, 333, 50, 1000, 5, 897, 1, 3, 66, 13
				System.out.println("Input Array: " + Arrays.toString(array));
				array = qs.sort(array);
				System.out.println(Arrays.toString(array));
			}
		}

		

		package sorting;

		import java.util.Arrays;

		public class QuickSortRighMostPivot {

				
			/*	
			
			1.	Choose Pivot with either start, end, or middle
			2. 	Partition the array with Split Point
				1.	if array[j] < pivot 
				2.	Increment leftmarker++
				3.	swap
				4.	swap right most with leftmarker + 1
				5.	return leftmarker + 1
			3.	Repeat for left and right subarrays
				
			*/	
			
			private class QuickSort {

				private int[] array;
				private int length;

				public int[] sort(int[] array) {
					this.array = array;
					this.length = array.length;
					quickSort(0, length - 1);
					return this.array;
				}

				private void quickSort(int low, int high) {
					if (low < high) {
						int splitPoint = partition(low, high);
						quickSort(low, splitPoint - 1);
						quickSort(splitPoint + 1, high);
					}
				}

				private int partition(int low, int high) {
					int pivot = this.array[high];
					int leftmarker = low - 1;

					for (int i = low; i < high; i++) {
						if (this.array[i] < pivot) {
							leftmarker++;
							swap(leftmarker, i);
						}
					}
					swap(leftmarker + 1, high);

					return leftmarker + 1;
				}

				private void swap(int i, int j) {
					int temp = this.array[i];
					this.array[i] = this.array[j];
					this.array[j] = temp;
				}
			}

			public static void main(String[] args) {
				QuickSort qs = new QuickSortRighMostPivot().new QuickSort();
				int[] array = {  12, 16, 333, 50, 1000, 5, 897, 1, 3, 66, 13};
				array = qs.sort(array);
				System.out.println(Arrays.toString(array));
			}

		}

----------------------------------------------------------

## Merge Sort:

-	Merge Sort is O(n log n ) in worst case and O(n) in average case
-	Insertion Sort, Selection Sort, Bubble Sort is O( n^2) in average case
-	Merge sort uses divide and conquer method to sort the array
-	Merge sort has two phases:
	
	-	Divide: In this phase,we will divide the elements into two halves
	-	Conquer: In this phase, we sort and merge the divided arrays 
	
## What is merge sort?

-	Merge sort is a sorting technique based on divide and conquer rule
-	With worst-case time complexity being Ο(n log n), it is one of the most respected algorithms
-	Merge sort first divides the array into equal halves and then combines them in a sorted manner

## What are properties of merge sort?

-	Stable
-	Θ(n) extra space for arrays
-	Θ(lg(n)) extra space for linked lists
-	Θ(n·lg(n)) time
-	Not adaptive
-	Does not require random access to data

## What is performance of merge sort?

-	Worst-case performance	O(n log n)
-	Best-case performance	O(n log n) typical, O(n) natural variant
-	Average performance	O(n log n)
-	Worst-case space complexity	О(n) total, O(n) auxiliary


	
	Code Snippet:
	
		package sorting;

		import java.util.Arrays;

		public class MergeSortDemo {

			private class MergeSort {

				private int[] array;
				private int length;

				public int[] sort(int[] array) {
					this.array = array;
					this.length = array.length;
					mergeSort(array);
					return this.array;
				}

				private void mergeSort(int[] array) {
					if (array.length < 2) {
						return;
					}

					int mid = array.length / 2;

					int[] left = new int[mid];
					int[] right = new int[array.length - mid];

					for (int i = 0; i < left.length; i++) {
						left[i] = array[i];
					}

					for (int i = 0; i < right.length; i++) {
						right[i] = array[mid + i];
					}

					mergeSort(left);
					mergeSort(right);

					merge(left, right, array);
				}

				private void merge(int[] left, int[] right, int[] result) {
					int leftmarker, rightmarker, resultmarker;
					leftmarker = rightmarker = resultmarker = 0;

					while (leftmarker < left.length && rightmarker < right.length) {
						result[resultmarker++] = left[leftmarker] < right[rightmarker] ? left[leftmarker++]
								: right[rightmarker++];
					}
					while (leftmarker < left.length) {
						result[resultmarker++] = left[leftmarker++];
					}
					while (rightmarker < right.length) {
						result[resultmarker++] = right[rightmarker++];
					}
				}
			}

			public static void main(String[] args) {
				MergeSort ms = new MergeSortDemo().new MergeSort();
				int[] array = {  12, 16, 333, 50, 1000, 5, 897, 1, 3, 66, 13 };
				array = ms.sort(array);
				System.out.println(Arrays.toString(array));
			}
		}

	
----------------------------------------------------------

## Insertion Sort

-	Insertion is not efficient sorting technique
-	Insertion sort is not fast, since it uses nested for loops to swift elements into place
-	Insertion sort is useful only for smaller data sets
-	Time Complexity of Insertion sort is O(n!) or O(n^2)
-	In Insertion sort each element will be picked up and inserted into correct location
-	Average case of Insertion sort is O(n^2)
-	Insertion Sort is better than Bubble sort and Selection Sort


## Properties of Insertion sort?
-	Stable
-	O(1) extra space
-	O(n2) comparisons and swaps
-	Adaptive: O(n) time when nearly sorted
-	Very low overhead



## What is Performance of insertion sort?

-	Worst-case performance	О(n2) comparisons, swaps
-	Best-case performance	O(n) comparisons, O(1) swaps
-	Average performance	О(n2) comparisons, swaps
-	Worst-case space complexity	О(n) total, O(1) auxiliary


	Code Snippet:
	
		package sorting;

		import java.util.Arrays;

		public class InsertionSortDemo {

			private class InsertionSort {

				private int[] array;

				public int[] sort(int array[]) {
					this.array = array;
					insertionSort(this.array, this.array.length);
					return array;
				}

				private void insertionSort(int[] array, int length) {
					for (int i = 1; i < length; i++) {
						int key = array[i];
						int j = i;
						while (j > 0) {
							if (key < array[j - 1]) {
								swap(j, j - 1);
							}	
							j--;
						}
					}
				}

				private void swap(int i, int j) {
					int temp = this.array[i];
					this.array[i] = this.array[j];
					this.array[j] = temp;
				}
			}

			public static void main(String[] args) {
				InsertionSort is = new InsertionSortDemo().new InsertionSort();
				int[] array = { 5, 4, 3, 2, 1 };
				array = is.sort(array);
				System.out.println(Arrays.toString(array));
			}
		}

----------------------------------------------------------
## Selection Sort

-	Simplest Algorithm
-	Selection Sort involves both Searching and Sorting 
-	Selection Sort is not fast, because it uses nested for loops
-	Selection Sort is applicable for smaller data sets
-	Selection runs in O(n^2)
-	Space Complexity of Selection Sort is O(1)

## Properties of Selection sort algorithm

-  Not stable
-  O(1) extra space
-  Θ(n2) comparisons
-  Θ(n) swaps
-  Not adaptive		
	
## When to use Selection sort?

-	Selection sort should never be used
-	It does not adapt to the data in any way , so its runtime is always quadratic
-	Selection sort has the property of minimizing the number of swaps
-	In applications where the cost of swapping items is high, selection sort very well may be the algorithm of choice

## What is performance of selection sort in Big'O?

-   Worst-case performance	О(n2)
-   Best-case performance	О(n2)
-   Average performance	О(n2)
-   Worst-case space Complexity	О(n) total, O(1) auxiliary
	
## Advantages Selection sort?

-	It is very simple
-	It is very efficient for small data sets
-	It is stable; i.e., it does not change the relative order of elements with equal keys
-	In-place; i.e., only requires a constant amount O(1) of additional memory space


	Code Snippet:

		package sorting;

		import java.util.Arrays;

		public class SelectionSortDemo {

			private class SelectionSort {
				private int[] array;

				public int[] sort(int[] array) {
					this.array = array;
					selectionSort(this.array);
					return this.array;
				}

				public void selectionSort(int[] array) {

					for (int i = 0; i < array.length - 1; i++) {
						int min = i;
						for (int j = i + 1; j < array.length; j++) {
							if (array[j] < array[min]) {
								min = j;
							}
						}
						swap(min, i);
					}
				}

				private void swap(int i, int j) {
					int temp = this.array[i];
					this.array[i] = this.array[j];
					this.array[j] = temp;
				}
			}

			public static void main(String[] args) {
				int[] array = { 80, 90, 40, 10, 20, 30, 50 };

				array = new SelectionSortDemo().new SelectionSort().sort(array);
				System.out.println(Arrays.toString(array));
			}

		}


----------------------------------------------------------
## Bubble Sort

-	Bubble sort  is simple sorting technique
-	Bubble sort can be used for smaller data sets
-	Bubble sort is slower and time consuming algorithm
-	Order of Algorithm of Bubble Sort is Time Complexity O(n) and Space Complexity is O(1)

### What are Properties of Bubble Sort?

-	Stable
-	O(1) extra space
-	O(n2) comparisons and swaps
-	Adaptive: O(n) when nearly sorted


## What is Performance of Bubble Sort?

-	Worst-case performance	O(n^{2})
-	Best-case performance	O(n)
-	Average performance	 O(n^{2})
-	Worst-case space complexity	O(1) auxiliary

	Code Snippet:
		
		package sorting;

		import java.util.Arrays;

		public class BubbleSortDemo {
			
			private class BubbleSort {
				
				private int [] array;
				
				public int [] sort(int [] array) {
					if(array!= null && array.length < 1) {
						return array;
					}
					this.array = array;
					bubbleSort(this.array, this.array.length);
					return array;
				}
				
				private void bubbleSort(int [] array, int length) {
					for(int i = 0; i < length - 1; i++) {
						for(int j = 0; j < length - i - 1; j++) {
							if(array[j] > array[j + 1]) {
								swap(j, j + 1);
							}
						}
					}
				}
				
				private void swap(int i, int j) {
					int temp = this.array[i];
					this.array[i] = this.array[j];
					this.array[j] = temp;
				}
			}
						
			public static void main(String[] args) {
				BubbleSort bs = new BubbleSortDemo().new BubbleSort();
				int array[] = {5,3,4,2,1,5,4};
				array  = bs.sort(array);
				System.out.println(Arrays.toString(array));
			}
		}
		
	Order of Algorithm:

		Time Complexity: O(n)
		Space Complexity: O (1)

----------------------------------------------------------		
		
## Shell Sort

-	Shell Sort is a generalized version of insertion sort. It is an in–place comparison sort
-	Shell Sort is also known as diminishing increment sort
-	This algorithm uses insertion sort on the large interval of elements to sort
-	Then the interval of sorting keeps on decreasing in a sequence until the interval reaches 1
-	These intervals are known as gap sequence.
-	Shell Sort overcomes the drawbacks of insertion sort by comparing elements separated by a gap of several positions
-	In general, Shell sort performs the following steps

	-	Step 1: Arrange the elements in the tabular form and sort the columns by using insertion sort
	-	Step 2: Repeat Step 1; each time with smaller number of longer columns in such a way that at the end, there is only one column of data to be sorted
	
-	This algorithm works quite efficiently for small and medium size array as its average time complexity is near to O(n)


### key points of shell sort algorithm –

-	Shell Sort is a comparison based sorting
-	Time complexity of Shell Sort depends on gap sequence 
-	Its best case time complexity is O(n* logn) and worst case is O(n* log2n)
-	Time complexity of Shell sort is generally assumed to be near to O(n) and less than O(n2) as determining its time complexity is still an open problem.
-	The best case in shell sort is when the array is already sorted. The number of comparisons is less
-	It is an in-place sorting algorithm as it requires no additional scratch space
-	Shell Sort is unstable sort as relative order of elements with equal values may change
-	It is been observed that shell sort is 5 times faster than bubble sort and twice faster than insertion sort its closest competitor
-	There are various increment sequences or gap sequences in shell sort which produce various complexity between O(n) and O(n2)

	Code Snippet:
	
		public class ShellSortEx {

			public static int shellSort(int[] array) {

				int n = array.length;

				for (int gap = n / 2; gap > 0; gap /= 2) {
					for (int i = gap; i < n; i++) {
						int temp = array[i];
						int j;
						for (j = i; j >= gap && array[j - gap] > temp; j -= gap) {
							array[j] = array[j - gap];
						}
						array[j] = temp;	
					}
				}
				System.out.println(Arrays.toString(array));
				return 0;
			}

			public static void main(String[] args) {
				int [] array = {4,9,8,1,3,5,2};
				shellSort(array);
			}
		}















