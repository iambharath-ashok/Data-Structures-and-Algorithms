#	Arrays


-	Array is a linear Data structure
-	Data is Stored continuously in Array
-	Reading is faster in Array, using index
-	Updating or deleting element in middle of Array is Computational Task

----------------------------------------------------------

## Find Min or Max or Array

	
	Code Snippet:
	
		public int findMin(int [] array) {
			int min = array[0];
			
			for(int i = 1; i < array.length; i++) {
				if(array[i] < min) {
					min = array[i];
				}
			}
			return min;
		}
----------------------------------------------------------

## Find Sub Sequence matching to Element


	Code Snippet:
	
		public static void findSubsequence(int [] array, int element) {
		int start = 0;
		int sum = array[0];
		for(int i = 1; i<array.length; i++) {
			sum += array[i];
			while(sum > element) {
				sum -= array[start];
				start++;
			} 
			if(sum == element) {
				for(int j = start; j<=i; j++) {
					System.out.println(array[j]);
				}
			}
		}
	}
	
----------------------------------------------------------
	
## Find all the pairs in Array whose sum is equals to given number


	Code Snippet:
	
		1.	 TC: O(n log n)
			
			findThePairs(int [] array, int sumNumber) {
				
				 Arrays.sort(array);
				 
				 int i = 0;
				 
				 int j = array.length - 1;
				 
				 
				 while( i < j ) {
				 
					if (array[i] + array[j] == sumNumber) {
						System.out.println("Pairs: of Item: "+element+ " ("+arr[i]+","+arr[j]+")");
						j--;
						i++;
					} else if (array[i] + array[j] < sumNumber) {
						i++;
					} else if (array[i] + array[j] > sumNumber) {
						j--;
					}
				 }
			} 


		2. Brute Force Way: TC O(n^2)
		
			findThePairs(int [] array, int sumNumber) {
				for(int i = 0; i < array.length; i++) {
					for(int j = i + 1; j < array.length; j++) {
						if(array[i] + array[j] == sumNumber) {
							System.out.println("Pairs: of Item: "+element+ " ("+arr[i]+","+arr[j]+")");	
						}
					}
				}
			}
	
----------------------------------------------------------	

## Find all the Leaders in the Array


	Code Snippet:
	
	
		void findLeaders(int [] array) {
			int max = array[array.length - 1];
			Syso("Leaders of Array are: ");
			syso(max);
			
			for(int i = array.length - 2; i >= 0; i--) {
				if (max < array[i]) {
					syso(array[i]);
					max = array[i];
				}
			}
			
		}
----------------------------------------------------------

## Move all the Zero to End of Array


	Code Snippet of Moving Zero's to End:
	
		iint[] moveZeroToEnd(int []array) {
			int counter = 0;	
			for (int i = 0; i < array.length; i++) {
				if(array[i] != 0) {
					array[counter] = array[i];
					counter++;
				}
			}
			Arrays.fill(array, counter, array.length, 0);
			return array;
		}

----------------------------------------------------------
## Move all the Zero to Beginning of Array	
	Code Snippet of Moving Zero's to End:
	
		public static int[] moveZeroToBeginning(int array[]) {
			int counter = array.length -1;

			for(int i = array.length -1;i>=0; i--) {
				if(array[i]!=0) {
					array[counter] = array[i];
					counter--;
				}
			}

			while(counter >= 0) {
				array[counter] = 0;
				counter--;
			}
			return array;
		}
----------------------------------------------------------

## 	Reverse an Array

	Code Snippet:
	
		public static int[] reverseArray(int [] array) {
			int i = 0;
			int j = array.length - 1;
			
			while (i < (i + j) / 2) {
				array[i] = array[i] + array[j];
				array[j] = array[i] - array[j];
				array[i] = array[i] - array[j];
				i++;
				j--;
			}
			return array;
		}
----------------------------------------------------------		
