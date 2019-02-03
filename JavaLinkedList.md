# Java LinkedList


--------------------------------------------------------------------------
## How to Represent LinkedList


	class ListNode<T>{
		
		T data;
		ListNode<T> next;
	}
	
	class ListNode<Integer> {
		
		Integer data;
		ListNode<Integer> next;
		
	}
	
	
	Code Snippet:
	
		public class LinkedList {
		
			private Node<T> head;

			private static class Node<T> {

				private T data;
				Node<T> next;

				Node(T data) {
					this.data = data;
					this.next = null;
				}
			}
		}
--------------------------------------------------------------------------
## How to create a LinkedList in Java

	Code Snippet:
	
		public static void main(String[] args) {
		
			Node head = new Node(10);
			Node second = new Node(11);
			Node third = new Node(1);
			Node fourth = new Node(18);
			
			head.next = second;
			second.next = third;
			third.next = fourth;
			fourth.next = null;
			
			System.out.println(head.next);
		}
--------------------------------------------------------------------------		
## Print All the Elements

	Code Snippet:
	
		// Given a Head of LL, display all its elemets
		public static void display(Node head) {
			if(head==null) {
				System.out.println("Empty Linked List");
				return;
			}
			Node current = head;
			while(current!=null) {
				System.out.print(current.data +"--->");
				current = current.next;
			}
			System.out.print(current);
		}
	
	Output:
	
		10--->11--->1--->18--->null
--------------------------------------------------------------------------
		
## Length of LinkedList

	Code Snippet:
	
		// Given a head of LL, find the length of LL
		public static int getLength(Node head) {
			if(head == null) {
				System.out.println("List is empty");
				return 0;
			}
			Node current = head;
			int count= 0;
			
			while(current!=null) {
				count ++;
				current = current.next;
			}
			return count;
		}
	
	Output:
	
		10--->11--->1--->18--->null
		Length of LL: 4
	
--------------------------------------------------------------------------		
## 	Insert at Beginning 

	Code Snippet:
	
		//Given the head of LL and data, insert at beginning
		public static Node insertAtBegginning(Node head, int data) {
			Node newNode = new Node(data);
			if(head == null) {
				return newNode;
			}
			newNode.next= head;
			return head = newNode;
		}
		
	Output:
	
		10--->11--->1--->18--->null
		25--->10--->11--->1--->18--->null // insertAtBegginning
--------------------------------------------------------------------------		
## 	Insert at End

	Code Snippet:
		
		//Given Head Of LL and data, Insert at End
		public Node insertAtEnd(Node head, int data) {
			Node newNode = new Node(data);
			if(head == null) {
				return newNode;
			}
			Node current = head;
			while(current.next!=null) {
				current = current.next;
			}
			current.next = newNode;
			return head;
		}
		
		
	Output:
	
		25--->10--->11--->1--->18--->null
		25--->10--->11--->1--->18--->7--->null // insertAtEnd
--------------------------------------------------------------------------		
##	Insert After Particular Element

	Code Snippet:

		// Given a Node, Insert After that particular Node
		public static void insertAfter(Node previous, int data) {
			if(previous == null) {
				System.out.println("Previous cant be empty");
				return;
			} 
			Node newNode = new Node(data);
			newNode.next = previous.next;
			previous.next = newNode;
		}
	
	Output:

		25--->10--->11--->1--->18--->7--->null
		25--->10--->11--->1--->45--->18--->7--->null // insertAfter 3 element 1 and 45

--------------------------------------------------------------------------		
		
## 	Insert at particular position

	Code Snippet:
		
		//Given a head, data and position, insert at the particular position
		public static Node insertAtPosition(Node head, int data, int position) {
			
			if(position < 1 && position > getLength(head) + 1) {
				System.out.println("Invalid Postion.");
				return null;
			}
			Node newNode = new Node(data);
			if(position == 1) {
				return newNode;
			} 
			
			Node previous = head;
			int count = 1;
			while(count < position -1) {
				count++;
				previous = previous.next;
			}
			newNode.next = previous.next;
			previous.next = newNode;
			return head;
		}
			
			
	Output:
	
		25--->10--->11--->1--->45--->18--->7--->null
		25--->10--->35--->11--->1--->45--->18--->7--->null // After insertAtPosition 3
		
--------------------------------------------------------------------------		
		
## Delete at Beginning 


	Code Snippet:
	
		// Given the Head of LL, Delete the FirstElement of LL
		public static Node deleteAtBeginning(Node head) {
			if(head == null) {
				System.out.println("List is Empty");
				return head;
			} 
			
			Node temp = head;
			head = head.next;
			temp.next= null;
			return temp;
		}
		
	Output:

		25--->10--->35--->11--->1--->45--->18--->7--->null
		10--->35--->11--->1--->45--->18--->7--->null // After deleteAtBeginning

--------------------------------------------------------------------------
		
## Delete at Last

	Code Snippet:

		// Given the Head of LL, delete tha last element of LL
		public static Node deleteLast(Node head) {
			if(head == null) {
				System.out.println("List is Empty");
				return head;
			}
			Node last = head;
			Node previousToLast = null;
			while(last.next!= null) {
				previousToLast = last;
				last = last.next;
			}
			previousToLast.next = null;
			return last;
		}			
		
	Output:

		25--->10--->35--->11--->1--->45--->18--->7--->null
		25--->10--->35--->11--->1--->45--->18--->null

--------------------------------------------------------------------------		
		
##	Delete at Particular Position


	Code Snippet:

		// Given the Head of the Node and Position, Delete the at Particular Node
		public static Node deleteAtPosition(Node head, int position) {
			Node nodeDelete = head;
			Node previousToDelete = null;
			int count = 1;
			
			if(position < 1 || position > getLength(head) + 1) {
				System.out.println("Invalid Position");
				return head;
			}
			
			
			if(position == 1) {
				Node temp = head;
				head = head.next;
				return temp;
			}
			
			while(count < position) {
				count++;
				previousToDelete = nodeDelete;
				nodeDelete = nodeDelete.next;
			}
			previousToDelete.next = nodeDelete.next;
			nodeDelete.next = null;
			return nodeDelete;
		}
	
	
	Output:
		
		25--->10--->35--->11--->1--->45--->18--->null
		25--->10--->11--->1--->45--->18--->null // After Deleting at Particular Position
		
--------------------------------------------------------------------------		
		
##	Search for Particular Element
	
	
	
	Code Snippet:
	
		public static boolean searchForElement(Node head, int data) {
			boolean isFound = false;
			
			if(head == null) {
				System.out.println("List is Empty.");
				return isFound;
			}
			Node currentNode = head;
			while(currentNode!= null) {
				if(currentNode.data == data) {
					isFound = true;
					break;
				}
				currentNode = currentNode.next;
			}
			return isFound;
		}
		
		
		
--------------------------------------------------------------------------		
## Reverse a List 

	Code Snippet:
	
		// Give Head of List, reverse a List 
		public static Node reverseLinkedList(Node head) {
			if(head == null) {
				System.out.println("List is Empty.");
				return head;
			}
			Node current = head;
			Node next = null;
			Node previous = null;
			while(current != null) {
				next = current.next;
				current.next = previous;
				previous = current;
				current = next;
			}
			return previous;
		}
	
	
	Output:
	
		25--->10--->11--->1--->45--->18--->null
		18--->45--->1--->11--->10--->25--->null
		
--------------------------------------------------------------------------		
## 	Find a Middle Node of Linked List


	Code Snippet:
	
		// Given Head of List, find middle of List
		public static Node middleOfList(Node head) {
			if(head == null) {
				System.out.println("List is Empty.");
				return head;
			}
			Node fastPointer = head;
			Node slowPointer = head;

			while (fastPointer != null && slowPointer.next != null) {
				slowPointer = slowPointer.next;
				fastPointer = fastPointer.next.next;
			}
			return slowPointer;
		}
		
	Output:
		
		18--->45--->1--->11--->10--->25--->null
		middle of List: 11
		
--------------------------------------------------------------------------		
		
## 	Find Nth Element from Beginning

	
	Code Snippet:
		// Given the head of LL, find the Nth element from Beginning
		public static Node getNthElement(Node head, int position) {
			if(head == null) {
				System.out.println("List is Empty.");
				return head;
			}
			if(position < 1 && position > getLength(head)) {
				System.out.println("Invalid Postion.");
				return head;
			}
			int count = 1;
			Node current = head;
			while (count< position) {
				count++;
				current = current.next;
			}
			return current;
		}
--------------------------------------------------------------------------		
		
## 	Find the Nth Element from End of LL


	Code Snippet:
	
		// Given Head of LL, find Nth element from End
		public static Node findNthElementFromEnd(Node head, int position) {
			if(head == null) {
				System.out.println("List is Empty.");
				return head;
			}

			if( position < 1 && position > getLength(head)) {
				System.out.println("Invalid Postion");
				return head;
			}

			Node refPointer = head;
			Node mainPointer = head;
			int count = 1;
			while(count<= position) {
				if(refPointer == null) {
					throw new IllegalArgumentException();
				}
				refPointer = refPointer.next;
				count++;
			}
			while(refPointer!=null) {
				mainPointer = mainPointer.next;
				refPointer = refPointer.next;
			}
			return mainPointer;
		}
--------------------------------------------------------------------------				

## 	Remove Duplicates from LinkedList
			
	Code Snippet:
	
		// Given Head of LL, remove all Duplicates
		public static Node removeDuplicates(Node head) {
			Node current = head;
			Node previous = null;
			Set<Integer> set = new HashSet<>();
			while(current!=null) {
				if(set.contains(current.data)) {
					previous.next = current.next;
				} else {
					set.add(current.data);
					previous = current;
				}
				current = current.next;
			}
			return head;
		}
			
--------------------------------------------------------------------------		
## Insert a Node at Sorted LinkedList	

	Code Snippet:
		
		// Given Head of LL, Sort a LL and insert at appropriate position
		public static Node sortLinkdedList(Node head) {
			Node current = head;
			
			List<Integer> dataList = new ArrayList<>();
			while(current != null) {
				dataList.add(current.data);
				current = current.next;
			}
			List<Node> collect = dataList.stream().sorted(Comparator.naturalOrder()).map(Node::new).collect(Collectors.toList());
				
			return head;
		}
	
		
	
		
--------------------------------------------------------------------------	
## Insert a Node in Sorted List

	Code Snippet:
	
		// Give a Sorted List and Head, Insert a Data at Appropriate Place
		public static Node insertNodeInSortedList(Node head, int data) {
			
			Node current = head;
			Node previous = null;
					
			while(current!= null && current.data < data) {
				previous = current;
				current = current.next;
			}
			Node newNode = new Node(data);
			previous.next = newNode;
			newNode.next = current;
			return head;					
		}		
		
--------------------------------------------------------------------------
##	Remove a given Key from Singly Linked List


	Code Snippet:
		
		// Given Head of LL and Key, Remove from LinkedList
		public static Node removeGivenKeyFromList(Node head, int data) {
			Node current = head;
			Node previous = null;
			
			while(current!= null && data!=current.data) {
				previous = current;
				current = current.next;
			}
			previous.next = current.next;
			return head;
		}
		
		
	Output:
		
		11--->45--->25--->10--->1--->18--->null
		11--->45--->25--->1--->18--->null
		
--------------------------------------------------------------------------
## 	Detect a Loop in Singly Linked List


	Code Snippet:
	
		// Given a LinkedList, detect a Loop
		public static boolean containsLoop(Node head) {
			Node fastPtr = head;
			Node slwPtr = head;
			
			while(fastPtr!=null && fastPtr.next!=null) {
				fastPtr = fastPtr.next.next;
				slwPtr = slwPtr.next;
				if(slwPtr == fastPtr) {
					return true;
				}
			}
			return false;
		}
		

		
--------------------------------------------------------------------------		

	
		
		
		
		
		
		
		
		
		
		
		
		
		
	
