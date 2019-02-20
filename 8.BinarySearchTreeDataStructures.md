# Binary Search Trees (BST)


-	Binary Tree is a type of Tree, in which data is organized in ordered manner 
-	Binary Tree Ordering helps in faster searching and insertion

-	A Tree is Binary Tree only if it follows the below 3 properties

	-	Left Subtree of Nodes should only contains values less than root node
	-	Right Subtree of Nodes should only contains values more than root node
	-	Left and Right Subtrees must also be a Binary Search Tree
	
-	With Binary Tree we will traverse only half the Tree at a Time

## Structure of Binary Search Tree


		class BinarySearchTree {
		
			private TreeNode root; 
			
			private class TreeNode {
				
				private int data;
				private TreeNode left;
				private TreeNode right;
				
				public TreeNode(int data) {
					this.data = data;
				}
			
			}
		
		}
		
		
		
##	How to insert a value into Binary Search Tree

			
			
	Code Snippet:
	
		public void insert(int data) {
			this.root = insert(this.root, data);
		}
		
		private TreeNode insert(TreeNode root, int data) {
			
			if(root == null) {
				root = new TreeNode(data);
				return root;
			}
			
			if(data < root.data) {
				root.left = insert(root.left, data);
			} else {
				root.right = insert(root.right, data);
			}
			return root;
		}
		
## How to Search for Key in Binary Search Tree

	Code snippet:	
	
		public TreeNode search(int data) {
			return search(this.root, data);
		}
		
		public TreeNode search(TreeNode root, int data) {
			if(root ==null ||root.data == data) {
				return root;
			}
			
			if(data < root.data) {
				return search(this.root.left, data);
			} else {
				return search(this.root.right, data);
			}
		}
		
## 	Binary Search Full Program


	Code Snippet:
		
		
		package trees;

		public class BinarySearchTree {
			
			private TreeNode root;
			
			private class TreeNode {
				
				private int data;
				private TreeNode left;
				private TreeNode right;
				
				public TreeNode(int data) {
					this.data = data;
					this.left = null;
					this.right = null;
				}
			}

			
			public void insert(int data) {
				this.root = insert(this.root, data);
			}
			
			private TreeNode insert(TreeNode root, int data) {
				
				if(root == null) {
					root = new TreeNode(data);
					return root;
				}
				
				if(data < root.data) {
					root.left = insert(root.left, data);
				} else {
					root.right = insert(root.right, data);
				}
				return root;
			}
			
			public void inOrderTraversal() {
				this.inOrderTraversal(this.root);
			}
			
			public void inOrderTraversal(TreeNode root) {
				
				if(root == null) {
					return;
				}
				
				inOrderTraversal(root.left);
				System.out.print(root.data+ " ");
				inOrderTraversal(root.right);
			}
			
			public TreeNode search(int data) {
				return search(this.root, data);
			}
			
			public TreeNode search(TreeNode root, int data) {
				if(root ==null ||root.data == data) {
					return root;
				}
				
				if(data < root.data) {
					return search(this.root.left, data);
				} else {
					return search(this.root.right, data);
				}
			}
			
			public static void main(String[] args) {
				
				BinarySearchTree bst = new BinarySearchTree();
				bst.insert(10);
				bst.insert(80);
				bst.insert(20);
				bst.insert(90);
				bst.insert(50);
				bst.insert(60);
				bst.inOrderTraversal();
				bst.search(80);
			}
		}

		
		
		
		
