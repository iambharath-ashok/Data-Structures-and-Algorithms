#	Sorting Techniques

## Quick Sort Algorithm

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

----------------------------------------------------------		
		
## Shell Sort

-	





































