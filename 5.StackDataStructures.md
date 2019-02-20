# Stack Data Structure

-	Stack is Linear Data Structure
-	Stack is an Ordered List in which elements are added and removed from same end called TOP
-	Stack follows LIFO order , hence is a LIFO list
-	Stack has a special Pointer called TOP which always points to TOP of Stack

-------------------------------------------------

## Stack Representation

	Code Snippet:
	
		class Stack{
		
			private Node top;
			private int length;
			
			private class Node {
				
				private int data;
				private Node next;
				
				public Node(int data) {
					this.data = data;
					this.next = null;
				}
			
			}
			
			public Stack() {
				this.top = null;
				this.length = 0;d
			}
		
		}
----------------------------------------------------

##	Reverse String using Stack

	Code Snippet:
	
		public String reverseString(String string) {
			Stack<Character> stack = new Stack<>();
			char[] charArray = string.toCharArray();
			
			for(char ch: charArray) {
				stack.push(ch);
			}
			
			for(int i = 0; i<charArray.length;i++) {
				charArray[i] = stack.pop();
			}
			return new String(charArray);
		}
	
----------------------------------------------------	
	
##	Stack Push, Pop, Peek Operations

	Code Snippet:
	
		package stack;

		import java.util.EmptyStackException;

		public class Stack<T> {
			
			private Node<T> top;
			private  int length;
			
			private class Node<T> {
				
				private T data;
				private Node<T> next;
				
				public Node(T data) {
					this.data = data;
					this.next = null;
				}
			}
			
			public Stack() {
				this.top = null;
				this.length = 0;
			}
			
			public boolean isEmpty() {
				return this.length ==0;
			}
			
			public int length() {
				return this.length;
			}
			
			public Node<T> push(T data) {
				Node<T> temp = new Node<>(data);
				temp.next = this.top;
				this.top = temp;
				this.length++;
				return this.top;
			}
			
			public T pop() {
				if(this.isEmpty()) {
					throw new EmptyStackException();
				}
				T data = this.top.data;
				this.top = this.top.next;
				this.length--;
				return data;
			}
			
			public T peek() {
				if(this.isEmpty()) {
					throw new EmptyStackException();
				}
				return this.top.data;
			}
			
			public String reverseString(String string) {
				Stack<Character> stack = new Stack<>();
				char[] charArray = string.toCharArray();
				
				for(char ch: charArray) {
					stack.push(ch);
				}
				
				for(int i = 0; i<charArray.length;i++) {
					charArray[i] = stack.pop();
				}
				return new String(charArray);
			}
			
			public static void main(String[] args) {
				Stack<Integer> stack = new Stack<>();
				stack.push(30);
				stack.push(10);
				stack.push(40);
				stack.push(20);
				stack.push(50);
				System.out.println(stack.peek());;
				
				System.out.println(stack.reverseString("Bharath"));
				
			}
		}

-----------------------------------------
