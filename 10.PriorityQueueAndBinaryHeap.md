
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

-------------------------------------------------------------------

## Bottom-up reheapif (swim) in Max Heap

- 	A max heap is a complete binary tree in which each node is having a value greater than its child
-	After inserting an value into heap, heap may lose its max heap property
-	Thus, we need to perform bottom-up reheapif technique
	-	In which we need to adjust location of elements to satisfy Max Heap Property
	
	
	Code Snippet of Bottom up ReheapIf:
	
		public void insert(int data) {
			if(this.size == this.heap.length - 1) {
				resize(this.heap.length */* 2);
			} 
			
			size++;
			heap[size] = data;
			swim(size);
			
		}
		
		public void swim(int k) {
			
			while (k >1 && heap[k/2] < heap[k]) {
				int temp = heap[k/2];
				heap[k/2] = heap[k];
				heap[k] = temp;
				k /= 2; // we need to shifting up till new value is inserted at correct postion
			}
		}
		
		private void resize(int size) {
			Integer [] temp = new Integer[size];
			
			for(int i = 0; i < this.heap.length; i++) {
				temp[i] = heap[i];
			}
			this.heap = temp;
		}

-------------------------------------------------------------------------

## Max Heap Full Implementation


	Code Snippet:
	
		/**
		 * 
		 **/
		package heaps;

		import java.util.Arrays;

		public class MaxPriorityQueue {

			private Integer[] heap;
			private int size;
			
			public MaxPriorityQueue(int size) {
				this.heap = new Integer[size];
			}

			public int size() {
				return this.size;
			}

			public boolean isEmpty() {
				return this.size == 0;
			}
			
			
			public void insert(int data) {
				if(this.size == this.heap.length - 1) {
					resize(this.heap.length */* 2);
				} 
				
				size++;
				heap[size] = data;
				swim(size);
				
			}
			
			public void swim(int k) {
				
				while (k >1 && heap[k/2] < heap[k]) {
					int temp = heap[k/2];
					heap[k/2] = heap[k];
					heap[k] = temp;
					k /= 2; // we need to shifting up till new value is inserted at correct postion
				}
			}
			
			private void resize(int size) {
				Integer [] temp = new Integer[size];
				
				for(int i = 0; i < this.heap.length; i++) {
					temp[i] = heap[i];
				}
				this.heap = temp;
			}
			
			
			private void displayQueue() {
				System.out.println(Arrays.toString(this.heap));
			}
			
			private Integer getMax() {
				if(this.heap != null && this.heap.length < 1) {
					throw new RuntimeException("Queue is Empty.");
				}
				return this.heap[1];
			}
			
			public static void main(String [] args) {
				MaxPriorityQueue  pq  = new MaxPriorityQueue(4);
				pq.insert(10);
				pq.insert(100);
				pq.insert(40);
				pq.insert(90);
				pq.insert(30);
				pq.insert(50);
				pq.insert(10);
				pq.insert(60);
				pq.insert(70);
				pq.insert(80);
				pq.displayQueue();
				System.out.println(pq.getMax());
			}

		}

------------------------------------------------------
## MinHeap Full Implementation

	Code Snippet:
	
		package heaps;

		import java.util.Arrays;

		public class MinPriorityQueue {


			private Integer[] heap;
			private int size;
			
			public MinPriorityQueue(int size) {
				this.heap = new Integer[size];
			}

			public int size() {
				return this.size;
			}

			public boolean isEmpty() {
				return this.size == 0;
			}
			
			
			public void insert(int data) {
				if(this.size == this.heap.length - 1) {
					resize(this.heap.length * 2);
				} 
				
				size++;
				heap[size] = data;
				swim(size);
				
			}
			
			public void swim(int k) {
				
				while (k >1 && heap[k/2] > heap[k]) {
					int temp = heap[k/2];
					heap[k/2] = heap[k];
					heap[k] = temp;
					k /= 2; // we need to shifting up till new value is inserted at correct postion
				}
			}
			
			private void resize(int size) {
				Integer [] temp = new Integer[size];
				
				for(int i = 0; i < this.heap.length; i++) {
					temp[i] = heap[i];
				}
				this.heap = temp;
			}
			
			
			private void displayQueue() {
				System.out.println(Arrays.toString(this.heap));
			}
			
			private Integer getMax() {
				if(this.heap != null && this.heap.length < 1) {
					throw new RuntimeException("Queue is Empty.");
				}
				return this.heap[1];
			}
			
			public static void main(String [] args) {
				MinPriorityQueue  pq  = new MinPriorityQueue(4);
				pq.insert(10);
				pq.insert(100);
				pq.insert(40);
				pq.insert(90);
				pq.insert(30);
				pq.insert(50);
				pq.insert(10);
				pq.insert(60);
				pq.insert(70);
				pq.insert(80);
				pq.displayQueue();
				System.out.println(pq.getMax());
			}


		}























		
