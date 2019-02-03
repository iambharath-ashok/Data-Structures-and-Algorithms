# Searching Algorithms

----------------------------------------------------------------
## Linear Searching


	Code Snippet:
	
	
		public int linearSearch(int [] array, int element) {
			
			for (int i =0; i<array.length; i++) {
				if(array[i]== element) {
					return i;
				}
			}
			return -1;
		}

----------------------------------------------------------------
## Binary Searching

			
	Code Snippet:
	
		public int binarySearch(int [] array, int element) {
		
			Arrays.sort(array);
			
			int low = 0;
			int high = array.length - 1;
			
			while(low <= high) {
				int mid = (low + high)/2;
				if(array[mid] == element) {
					return mid;
				} else if(array[mid] < key) {
					low = mid + 1;
				}  else {
					high = mid - 1;
				}
			}
		}
		
----------------------------------------------------------------		
		
		
		
		
		
		
		
		
