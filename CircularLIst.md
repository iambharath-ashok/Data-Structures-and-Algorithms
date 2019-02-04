# Circular List

-	Similar to LinkedList 
-	Only Difference is that Last node points to First Node instead of null
-	Keep track of Last Node instead of Head Node like in Singly LinkedList
-	When Circular List has only one Node, then Node.next points to itself


------------------------------------------------------------------------------

##	How to Represent a Circular List


	Code Snippet:
	
	
		public class CircularList<T> {
			private Node<Integer> last;
			private int length;

			private class Node<T> {

				private T data;
				private Node<T> next;

				public Node(T data) {
					this.data = data;
					this.next = null;
				}
			}

			public CircularList() {
				this.last = null;
				this.length = 0;
			}

			public int length() {
				return this.length;
			}

			public boolean isEmpty() {
				return this.length == 0;
			}
		}
		
		
------------------------------------------------------------------------------
		
##	Create a Circular List


	Code Snippet:
		
		private void createCircularList() {
			Node<Integer> first = new Node<>(70);
			Node<Integer> second = new Node<>(10);
			Node<Integer> third = new Node<>(60);
			Node<Integer> fourth = new Node<>(20);
			
			first.next = second;
			second.next  = third;
			third.next = fourth;
			fourth.next = first;
			this.last = fourth;
			this.length = 4;
		}
		
------------------------------------------------------------------------------		
##	Traverse Circular List		

	
	Code Snippet:
	
		public void displayCircularList() {
			if(this.isEmpty()) {
				System.out.println("List is Empty.");
				return;
			}
			if(this.last == null) {
				System.out.println("List is Empty.");
				return;
			}
			Node<Integer> first = last.next;
			while(first!=null && first!= last) {
				System.out.print(first.data+"------->");
				first = first.next;
			}
			System.out.print(first.data+"---->"+first.next.data);
		}
		
	Output:

		70------->10------->60------->20---->70
		
------------------------------------------------------------------------------		
##  Display Circular List

	
	Code Snippet:
	
		public void displayCircularList() {
	
			if(this.isEmpty()) {
				System.out.println("List is Empty.");
				return;
			}
			if(this.last == null) {
				System.out.println("List is Empty.");
				return;
			}
			Node<Integer> first = last.next;
			while(first!=null && first!= last) {
				System.out.print(first.data+"------->");
				first = first.next;
			}
			System.out.print(first.data+"---->"+first.next.data);
			System.out.println();
		}
		
------------------------------------------------------------------------------
## 	Insert At Beginning Of CircularList

	Code Snippet:
		
		public void insertAtBeginningOfCircularList(int data) {
			Node<Integer> newNode  = new Node<>(data);
			if(last == null) {
				last = newNode;
			} else {
				newNode.next = last.next;
			}
			last.next = newNode;
			this.length();
		}
		
------------------------------------------------------------------------------
## 	Insert At Beginning Of CircularList		
	
	Code Snippet:
		
		public void insertAtEndOfCircularList(int data) {
			Node<Integer> newNode = new Node<>(data);
			
			if(last == null) {
				last = newNode;
				last.next = last;
			} else {
				newNode.next = last.next;
				last.next = newNode;
				last = newNode;
			}
			
			this.length++;
			
		}
		
------------------------------------------------------------------------------	
##	Remove First From Circular List

	Code Snippet:
		
		public void removeFirstElementFromCircularList() {
			if(this.isEmpty() || this.last == null) {
				System.out.println("List is Empty.");
				return;
			}
			Node<Integer> deleteNode  = last.next;
			last.next = deleteNode.next;
			deleteNode = deleteNode.next = null;
		}
		
------------------------------------------------------------------------------
## 	Remove Last Element From CircularList

	Code Snippet:
		
		public void removeLastElementFromCircularList() {
			if(this.isEmpty() || this.last == null) {
				System.out.println("List is Empty.");
				return;
			}
			
			if(this.last.next == this.last) {
				this.last = null;
				return;
			}
			Node<Integer> deleteNode = last.next;
			Node<Integer> temp = null;
			
			while(deleteNode!=last) {
				temp = deleteNode;
				deleteNode = deleteNode.next;
			}
			
			temp.next = deleteNode.next;
			this.last = temp;
			deleteNode = deleteNode.next = null;
			this.length--;
		}
		
		
		
------------------------------------------------------------------------------		
## Full Program of Circular Linked List


	Code Snippet		
		
		package circularlist;

		public class CircularList<T> {

			private Node<Integer> last;
			private int length;

			private class Node<T> {

				private T data;
				private Node<T> next;

				public Node(T data) {
					this.data = data;
					this.next = null;
				}
			}

			public CircularList() {
				this.last = null;
				this.length = 0;
			}

			public int length() {
				return this.length;
			}

			public boolean isEmpty() {
				return this.length == 0;
			}
			
			
			public static void main(String[] args) {
				CircularList<Integer> cl = new CircularList<>();
				cl.createCircularList();
				cl.displayCircularList();
				cl.insertAtBeginningOfCircularList(30);
				cl.displayCircularList();
				cl.insertAtEndOfCircularList(100);
				cl.displayCircularList();
				cl.removeFirstElementFromCircularList();
				cl.displayCircularList();
				cl.removeLastElementFromCircularList();
				cl.displayCircularList();
			}

			private void createCircularList() {
				Node<Integer> first = new Node<>(70);
				Node<Integer> second = new Node<>(10);
				Node<Integer> third = new Node<>(60);
				Node<Integer> fourth = new Node<>(20);
				
				first.next = second;
				second.next  = third;
				third.next = fourth;
				fourth.next = first;
				this.last = fourth;
				this.length = 4;
			}
			
			public void displayCircularList() {
				
				if(this.isEmpty()) {
					System.out.println("List is Empty.");
					return;
				}
				if(this.last == null) {
					System.out.println("List is Empty.");
					return;
				}
				Node<Integer> first = last.next;
				while(first!=null && first!= last) {
					System.out.print(first.data+"------->");
					first = first.next;
				}
				System.out.print(first.data+"---->"+first.next.data);
				System.out.println();
			}
			
			public void insertAtBeginningOfCircularList(int data) {
				Node<Integer> newNode  = new Node<>(data);
				if(last == null) {
					last = newNode;
				} else {
					newNode.next = last.next;
				}
				last.next = newNode;
				this.length();
			}
			
			public void insertAtEndOfCircularList(int data) {
				Node<Integer> newNode = new Node<>(data);
				
				if(last == null) {
					last = newNode;
					last.next = last;
				} else {
					newNode.next = last.next;
					last.next = newNode;
					last = newNode;
				}
				
				this.length++;
				
			}
			
			
			public void removeFirstElementFromCircularList() {
				if(this.isEmpty() || this.last == null) {
					System.out.println("List is Empty.");
					return;
				}
				Node<Integer> deleteNode  = last.next;
				last.next = deleteNode.next;
				deleteNode = deleteNode.next = null;
			}
			
			public void removeLastElementFromCircularList() {
				if(this.isEmpty() || this.last == null) {
					System.out.println("List is Empty.");
					return;
				}
				
				if(this.last.next == this.last) {
					this.last = null;
					return;
				}
				Node<Integer> deleteNode = last.next;
				Node<Integer> temp = null;
				
				while(deleteNode!=last) {
					temp = deleteNode;
					deleteNode = deleteNode.next;
				}
				
				temp.next = deleteNode.next;
				this.last = temp;
				deleteNode = deleteNode.next = null;
				this.length--;
			}

		}

---------------------------------------------------------
