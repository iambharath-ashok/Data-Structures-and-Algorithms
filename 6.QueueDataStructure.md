# Queue Data Strucutures

-	Queue is a Linear Data Structure used for Storing Data 
-	Queue is FIFO Data Structure, in which elements are inserted at one end called REAR and deletion is done at another end called FRONT
-	First Element inserted will be Deleted First
-	In Queue, element are inserted at one End and Deleted at another End

## Enqueue

-	Enqueue is a insertion operation done on the Queue
	
	Code Snippet:
	
		public void enqueue(int data) {
			Node newNode = new Node(data);
			if(this.isEmpty()) {
				this.front = newNode;
			} else {
				this.rear.next = newNode;
			}
			this.rear = newNode;
		}
	

##	Dequeue	

-	Dequeue is a deletion operation done on the Queue

	Code Snippet:
	
		public int dequeue() {
			if(this.isEmpty()) {
				throw new NoSuchElementException();
			} 
			int data = front.data;
			front = front.next;
			if(front == null) {
				rear = front;
			}
			return data;
		}

## Peek

	Code Snippet:
	
		public int peek() {
			if(this.isEmpty() && this.front == null) {
				System.out.println("Queue is Empty.");
				return -1;
			}
			return this.front.data;
		}
	
##	Poll
		
	Code Snippet:
	
		public int poll() {
			if(front == null) {
				System.out.println("Queue Under Flow");
				//front = rear = null;
				return -1;
			}
			
			front = front.next;
			--this.length;
			return -1;
		}

## Offer

	Code Snippet:
		
		public int offer(int data) {
			Node newNode = new Node(data);
			if(this.isEmpty() && this.front==null) {
				this.front = this.rear =  newNode;
				return this.front.data;
			}
			this.rear.next = newNode;
			this.rear = newNode;
			this.length++;
			return this.front.data;
		}

----------------------------------------------------------------------
##	Queue Implementation with LinkedList

	Code Snippet:
	
		package queues;

		import java.util.NoSuchElementException;

		public class Queue {

			private Node front;
			private Node rear;
			private int length;

			private class Node {
				private int data;
				private Node next;

				public Node(int data) {
					this.data = data;
					this.next = null;
				}
			}

			public Queue() {
				this.front = null;
				this.rear = null;
				this.length = 0;
			}

			public boolean isEmpty() {
				return this.length == 0;
			}

			public int length() {
				return this.length;
			}
			
			
			public int peek() {
				if(this.isEmpty() && this.front == null) {
					System.out.println("Queue is Empty.");
					return -1;
				}
				return this.front.data;
			}
			
			
			public int poll() {
				if(front == null) {
					System.out.println("Queue Under Flow");
					//front = rear = null;
					return -1;
				}
				
				front = front.next;
				--this.length;
				return -1;
			}
			
			public int offer(int data) {
				Node newNode = new Node(data);
				if(this.isEmpty() && this.front==null) {
					this.front = this.rear =  newNode;
					return this.front.data;
				}
				this.rear.next = newNode;
				this.rear = newNode;
				this.length++;
				return this.front.data;
			}
			
			public void displayQueue() {
				if(this.isEmpty() && this.front==null) {
					System.out.println("Queue is Empty.");
					return;
				}
				
				Node temp = this.front;
				while(temp!=null) {
					System.out.print(temp.data+"|");
					temp = temp.next;
				}
			}
			
			public void enqueue(int data) {
				Node newNode = new Node(data);
				if(this.isEmpty()) {
					this.front = newNode;
				} else {
					this.rear.next = newNode;
				}
				this.rear = newNode;
			}
			
			public int dequeue() {
				if(this.isEmpty()) {
					throw new NoSuchElementException();
				} 
				int data = front.data;
				front = front.next;
				if(front == null) {
					rear = front;
				}
				return data;
			}
			
			public static void main(String[] args) {
				Queue queue = new Queue();
				queue.offer(10);
				queue.offer(20);
				queue.offer(30);
				queue.offer(40);
				queue.offer(50);
				queue.offer(60);
				queue.displayQueue();
				System.out.println("\nFront of Queue: "+queue.peek());
				queue.poll();
				queue.poll();
				queue.poll();
				queue.poll();
				queue.poll();
				queue.poll();
				queue.poll();
				queue.displayQueue();
				
				
			}

		}


----------------------------------------------------------------------

## 	Queue Implementation with Array

	Code Snippet:
	
		package queues;

		public class QueueArrayList {
			
			private int [] queue;
			private int front;
			private int rear;
			
			public QueueArrayList(int length) {
				this.queue = new int [length];
				this.front = -1;
				this.rear = -1;
			}
			
			public boolean isEmpty() {
				return this.queue.length == 0;
			}
			
			public int length() {
				return this.queue.length;
			}
			
			public int peek() {
				if(this.front == -1 || this.front > this.rear) {
					System.out.println("Queue Is Empty.");
					return -1;
				}
				return this.queue[this.front];
			}
			
			public int offer(int data) {
				if(this.rear >= this.queue.length -1) {
					System.out.println("Queue Overflow.");
					return -1;
				}
				if(this.front == -1) {
					this.rear = ++this.front;
					this.queue[this.rear] = data;
				} else {
					this.queue[++this.rear] = data;
				}
				return this.queue[this.front];
			}
			
			public int poll() {
				if(this.front > this.rear) {
					System.out.println("Queue UnderFlow.");
					return -1;
				}
				int data = this.queue[this.front];
				++this.front;
				return data;
			}
			
			public void displayQueue() {
				if(this.front > this.rear || this.front == -1) {
					System.out.println("Queue is Empty.");
					return;
				}
				int i = this.front, j = this.rear;
				for(;i<= j; i++) {
					System.out.print(this.queue[i]+" |");
				}
				System.out.println();
			}
			
			public static void main(String[] args) {
				QueueArrayList queue = new QueueArrayList(5);
				queue.peek();
				queue.offer(10);
				queue.offer(20);
				queue.offer(30);
				queue.offer(40);
				queue.offer(50);
				queue.offer(60);
				queue.displayQueue();
				System.out.println("Polling Queue: "+queue.poll());
				System.out.println("Polling Queue: "+queue.poll());
				System.out.println("Polling Queue: "+queue.poll());
				System.out.println("Polling Queue: "+queue.poll());
				System.out.println("Polling Queue: "+queue.poll());
				System.out.println("Polling Queue: "+queue.poll());
				queue.peek();
			}
		}

--------------------------------------------------------







































