# Graphs

-	A Graph is a Non-Linear Data Structure used for storing the data
-	A Graph is a set of vertices and collection of edges that connects pairs of vertices

## Application of Graphs 

-	Social N/w
	-	Graph is used in Social N/w sites like Twitter, Facebook etc
	-	Its called as Social N/w Graph
	-	Names represent Vertices and Edges represent relationship b/w them

-	Applications - Web Content ovet the Internet

	-	Graphs helps to organize web content over the internet
	-	Webpages such as google.com, udemy.com, youtube.com, twitter.com represents vertices
	-	Link b/w two webpages represented as an Edge of Graph
	
	
##	Adjacency Matrix Representation (Undirected Graph)

### Undirected Graph

-	Undirected Graph is a Graph with no for edges b/w vertices
-	Ex: Social N/w Graph is an Undirected Graph

### Adjacency Matrix Representation of Undirected Graph

	
	Graph:
	
		0--------------------1
		|					 |	
		|                    |
		|                    |
		|                    |
		|                    |
		3--------------------2
		
	
	Adjacency Matrix[][]:
	
		
			0	1	2 	3
		
		0	0	1	0	1
		
		1	1	0	1	0	
		
		2	0	1	0	1
		
		3	1	0	1	0
		
## Representation of Undirected  Graph in Java using Array


	Code Snippet:
	
		public class Graph {
	
			private int[][] adjacencyMatrix;
			private int edges;
			private int vertices;
			
			public Graph(int nodes) {
				this.edges = 0;
				this.vertices = nodes;
				this.adjacencyMatrix = new int[vertices][vertices];
			}
			
			public void addEdge(int row, int column) {
				this.adjacencyMatrix[row][column] = 1;
				this.adjacencyMatrix[column][row] = 1;
				this.edges++;
			}
			
			
			public static void main(String[] args) {
				Graph g = new Graph(4);
				g.addEdge(0, 1);
				g.addEdge(1, 2);
				g.addEdge(0, 3);
				g.addEdge(3, 2);
				g.displayAdjacencyMatrix();
				
			}
			
			public void displayAdjacencyMatrix() {
				for(int row = 0; row < this.vertices; row ++) {
					System.out.print(row + ": ");
					for(int column = 0; column < this.vertices; column++) {
						System.out.print(this.adjacencyMatrix[row][column]+" ");
					}
					System.out.println();
				}
			}
		}



##	Representation of Undirected Graph in Java using List

	
	Code Snippet:
	
		public class GraphWithList {
	
			private List<Integer>[] adj;
			private int vertices;
			private int edges;
			
			private GraphWithList(int vertices) {
				this.vertices = vertices;
				this.edges = 0;
				this.adj = new List[this.vertices];
				for(int i = 0; i < this.vertices; i++) {
					adj[i] = new LinkedList<>();
				}
			}
			
			private void addEdge(int u, int v) {
				this.adj[u].add(v);
				this.adj[v].add(u);
				this.edges++;
			}
			
			public void display() {
				for(int v = 0; v < this.vertices; v++) {
					System.out.print(v +" :");
					for(int e : this.adj[v] ) {
						System.out.print(e+" ");
					}
					System.out.println();
				}
			}
			
			public static void main(String[] args) {
				GraphWithList g = new GraphWithList(4);
				g.addEdge(0, 1);
				g.addEdge(1, 2);
				g.addEdge(2, 3);
				g.addEdge(3, 0);
				g.display();
			}
			
		}

	Output:
		0 :1 3 
		1 :0 2 
		2 :1 3 4 
		3 :2 0 
		4 :2 
----------------------------------------------------------


## Breadth First Search (BFS)

-	BFS is traversing technique used to traverse the Graph
-	BFS is also know as Level Order Traversal
-	Vertices will be visited in level by level order

	Code Snippet:
	
		public void bfs(int vertice) {
			boolean[] visited = new boolean[this.vertices];
			Queue<Integer> buffer = new LinkedList<>();
			visited[vertice] = true;
			buffer.offer(vertice);

			while (!buffer.isEmpty()) {
				int u = buffer.poll();
				System.out.print(u+" ");
				for (int v : adj[u]) {
					if (!visited[v]) {
						visited[v] = true;
						buffer.offer(v);
					}
				}
			}
		}
		
		Output:
			 BFS: 0 1 3 2 4 
 

## Depth First Search(DFS)


	Code Snippet:
	
		public void dfs(int s) {
			boolean[] visited = new boolean[this.vertices];
			Stack<Integer> stack = new Stack<>();
			stack.push(s);
			System.out.println("\n");
			
			while(!stack.isEmpty()) {
				int u = stack.pop();
				if(!visited[u]) {
					visited[u] = true;
					System.out.print(u + " ");
					
					for(int v : adj[u]) {
						if(!visited[v]) {
							stack.push(v);
						}
					}
				}
			}
		}


	Output:
	
		DFS: 0 3 2 4 1 



## 	Graph implentation in Java with DFS and BFS

	
	Code Snippet:
	
		package graphs;

		import java.util.LinkedList;
		import java.util.List;
		import java.util.Queue;
		import java.util.Stack;

		public class GraphWithList {

			private List<Integer>[] adj;
			private int vertices;
			private int edges;

			private GraphWithList(int vertices) {
				this.vertices = vertices;
				this.edges = 0;
				this.adj = new List[this.vertices];
				for (int i = 0; i < this.vertices; i++) {
					adj[i] = new LinkedList<>();
				}
			}

			private void addEdge(int u, int v) {
				this.adj[u].add(v);
				this.adj[v].add(u);
				this.edges++;
			}

			public void display() {
				for (int v = 0; v < this.vertices; v++) {
					System.out.print(v + " :");
					for (int e : this.adj[v]) {
						System.out.print(e + " ");
					}
					System.out.println();
				}
			}

			public void bfs(int node) {
				boolean[] visited = new boolean[this.vertices];
				Queue<Integer> buffer = new LinkedList<>();
				visited[node] = true;
				buffer.offer(node);
				System.out.print("\n BFS: ");
				while (!buffer.isEmpty()) {
					int u = buffer.poll();
					System.out.print(u+" ");
					for (int v : adj[u]) {
						if (!visited[v]) {
							visited[v] = true;
							buffer.offer(v);
						}
					}
				}
			}
			
			
			
			public void dfs(int s) {
				boolean[] visited = new boolean[this.vertices];
				Stack<Integer> stack = new Stack<>();
				stack.push(s);
				System.out.print("\n DFS: ");
				
				while(!stack.isEmpty()) {
					int u = stack.pop();
					if(!visited[u]) {
						visited[u] = true;
						System.out.print(u + " ");
						
						for(int v : adj[u]) {
							if(!visited[v]) {
								stack.push(v);
							}
						}
					}
				}
			}

			
			public static void main(String[] args) {
				GraphWithList g = new GraphWithList(5);
				g.addEdge(0, 1);
				g.addEdge(1, 2);
				g.addEdge(2, 3);
				g.addEdge(3, 0);
				g.addEdge(2, 4);
				
				g.display();
				g.bfs(0);;
				g.dfs(0);
			}

		}























	
