# Tries

-	Trie is a data structure actually came from word retrieval
-	Trie data structure is used for fast retrieval purposes
-	Retrieve stored information very fast
-	In Trie root node will be and it will connected to trie of Strings

## Real Life Applications

-	Google Auto-completion
-	Search Contacts in Mobile Phone Index
-	Auto-Spell checking in document

## How to represent a Tries Data Structure in Java

-	Each node in Trie represents a single alphabet of a word called Trie Node
-	In order to insert a string "Dog", three trie nodes are used, one for each alphabet


## Java Representation of Tries

	Code Snippet:
	
		public class Trie {
	
			private TrieNode root;
			
			public Trie() {
			root = new TrieNode(); // root is empty 
			}
			
			private class TrieNode {
			private TrieNode[] children;
			private boolean isWord;
				
			public TrieNode() {
				this.children = new TrieNode[26]; // storing english words - a -> z    	    this.isWord = false;
			}
			}
			
			public void insert(String word) {
			if(word == null || word.isEmpty()) {
				throw new IllegalArgumentException("Invalid input");
			}
				
			word = word.toLowerCase();
				
			TrieNode current = root;
			for(int i = 0; i < word.length(); i++) {
				char c = word.charAt(i);
				int index = c - 'a';
				if(current.children[index] == null) {
				TrieNode node = new TrieNode();
				current.children[index] = node;
				current = node;
				} else {
				current = current.children[index];
				}
			}
			current.isWord = true;
				
			}
			
			public boolean search(String word) {
			return false;
			}
		 
			public static void main(String[] args) {
			Trie trie = new Trie();
			trie.insert("cat");
			trie.insert("cab");
			trie.insert("son");
			trie.insert("so");
			System.out.println("Values inserted successfully !!!");
			}
		}