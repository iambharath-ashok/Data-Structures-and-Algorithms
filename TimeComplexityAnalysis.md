## Sorting Techniques 

1.	Quick Sort
2. 	Insertion Sort
3.	Merge Sort
4.	Bubble Sort
5.	Selection Sort
6.	Shell Sort 

## Time Complexity



## Space Complexity

## Types of Algorithms


-	Recursive
-	Iterative

-	Performance of both Recursive and Iterative will be same 
-	But analysis of Iterative will be different

## Asymptotic Notations

-	Big (Oh)O is called Asymptotic Notations
	
	-	Measurements
		-	worst case
		-	best case
		-	average case
-	Big (Oh) Ignore constants
	
	-	Certain terms Dominate Others
	
	O(1) < O(log n) < O(n) < O(n log n) < O(n^2) < O(2^n) < O(n!)

-	Statements
	-	Constant:
	
		x = x + (10 * 20) <===== O(1)
		is a constant and independent of n

	-	Linear:
	
		for i in (0, n)
			print x;
		
		n * O(1) = O(n)
	
		x = x + 10;
		for i in (0,n)
			print x
			
		total time = O(1) + O(n)
		Note : we drop lower order terms then total time complexity will be:
		
		O(n)
		
	- 	Quadratic:
		
			for i in (0,n) =====> O(n)
				for j in (0,n) ====> O(n)
					pf() ========> O(1)	
			 O(n) + O(n) + O(1) = O(n ^ 2)
			O(n) + O(n^2) = O(n^2)
	
			if 
				O(1)
			else 
				O( log n)
			else if 
				O(n^2)
				
			total time = O(n^2)
			
			
## Find Time complexity of below functions

-	function

		int i , s;
		
		while(s < n) {
		
			i++;
			s = s + i;
		}
	
	
	Ans:
	
		O (/n) 
	

-	function

		for (int i = 1;i^2 <= n; i++) {}


	Ans:
		O (/n)
	
-	function
		
		for(int i = 0; i < n; i++)
			for(int j = 0; j < i; j++)
				for(int k = 0; k < 100; k++)
					pf();
	
	Ans:
	
		100 + 2 * 100 + 3 * 100 + 4 * 100
		100(1+2+3+4 ... n)
		100(n(n+1))/2
		O(n2)
		
-	function
	
		for(int i =0; i < n; i++)
			for(int j = 0; j < i^2; j++)
				for(int k = 0; k< n/2; k++) 
					pf
					
	Ans:

		n/2(1+4+9+ 16 .... n^2)
		n/2(n(n+1(2n+1)))/6
		O(n^4)
		
-	function
		
		for(int i = 0; i <= n; i= i*2)
		
	Ans: 
		O(log n)
		
		log2 n log4 n
		
-	function

		for(i = n/2; i < n; i++)
			for(j = i; j <= n/2; j++)
				for(k =1; K <=n; k= k*2)
					pf()
					

	Ans:
		
		n/2 + n/2 + log n
		
		O(n ^ 2 (log n))
		
-	function
		
		for(i = n/2; i <=n; i++)
			for(j =1;j<=n; j= j*2)
				for(k =1;k<=n;k=k*2)
					pf()
					
	Ans:
		n/2 + log n + log n
		n/2 * (log n)^2
		
		O(n * (log n)^2)
				

-	function	

		while(n>=1)
			n = n/2;
			
	Ans:
		log n
		
-	funtion

		while( n>= 1)
			n(1+1/2+1/3+1/4....1/n)
			n(log n)
			O( n log n)
			
			



		
		