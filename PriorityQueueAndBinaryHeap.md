
# Priority Queue

-	Priority Queue is a Data Structure that allows to store the data
-	Priority Queue allows to find minimum and maximum element among collection of elements in a constant time
-	Priority Queue allows following Operations

	-	insert(key) : Insert a key in to Priority Queue
	-	deleteMin/ deleteMax: Return and delete Largest or Smallest Key
	-	getMax/ getMin: Return Max or Min element 
	
	
## Binary Heap

-	Binary Heap is a Data Structure that helps to implement Priority Queue Operations Efficiently
-	A Binary Heap is Complete Binary Tree 
	-	In which each parent node value is either greater or less than child nodes

- 	There are two types of Binary Tree
	
	-	Min Heap
		-	In Min Heap, Child Nodes will have values greater than Parent Node
		
	-	Max Heap
		-	In Max Heap, Parent Node will have values greater than Child Nodes

		
##	Complete Binary Tree

-	A Complete Binary Tree is Binary Tree, where all the levels are completely filled except for last levels
-	Last level can have nodes in such a way that left side can never be empty


## Representation of Binary Heap

-	Binary Heap is implemented with Arrays 
-	First entry of Array will be taken as empty 
-	Arrays size will be #nodes + 1
-	Binary Heaps are Complete Binary Tree:
	-	In which values are stored in array by traversing level by level from left to right
	
-	Binary Heap does not allow null or empty values 


## Finding a Child Nodes in Tree

-	Given a Node, we can find the child nodes in Binary Tree uisng:

		left:   2 * index
		right: (2 * index) + 1 

		Children of 1st Index 2 and 3
		Children of 2nd Index 4 and 5
		Children of 3rd Index 6 and 7


##	Finding Parent of Kth index

		Parent of 7th Index is 3
		Parent of 6th Index is 3
		Parent of 5th Index is 2
		Parent of 4th Index is 2
		
		Parent of Kth index = k/2 
		


## How to implement Max Binary Heap

-	Max Binary Heap is Complete Binary Tree in which each parent node has value greater than its child node
-	Highest element will be at top which is root of whole Complete Binary Tree
-	For its array representation it will be at first element of array array[1]				


## Java Representation of MaxHeapPriorityQueue
	
	Code Snippet:
	
		package heaps;

		/**
		 * @author iambh
		 *
		 **/
		public class MaxPriorityQueue {
			
			private Integer[] queue;
			private int size;
			
			public MaxPriorityQueue(int size) {
				this.queue = new Integer[size + 1];
				this.size = 0;
			}

			
			public boolean isEmpty() {
				return this.size == 0;
			}
			
			public int size() {
				return this.size;
			}
			
			public static void main(String[] args) {
				MaxPriorityQueue queue = new MaxPriorityQueue(3);

			}
		}

























		