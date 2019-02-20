# Matrix Problem

##	Given a row and column wise Sorted Matrix of n x n. Write a program to search key  in a given Matrix.


	Code Snippet:
	
	
		public static void search(int[][] matrix, int n, int element) {

			int row = 0;
			int column = n - 1;

			while (row <= n - 1 && column >= 0) {
				if (matrix[row][column] == element) {
					System.out.println("Element found at Postion: " + row + ": " + column);
					return;
				}
				if (matrix[row][column] > element) {
					column--;
				} else {
					row++;
				}
			}
			System.out.println("Elememt: "+ element+" Not Found.");
		}

## Full Program:

	Code Snippet:
	
	
		package matrix;

		public class MatrixSearch {

			public static void search(int[][] matrix, int n, int element) {

				int row = 0;
				int column = n - 1;

				while (row <= n - 1 && column >= 0) {
					if (matrix[row][column] == element) {
						System.out.println("Element found at Postion: " + row + ": " + column);
						return;
					}
					if (matrix[row][column] > element) {
						column--;
					} else {
						row++;
					}
				}
				System.out.println("Elememt: "+ element+" Not Found.");
			}
			
			public static void main(String[] args) {
				
				int n = 4;
				int [][] matrix =  {
						 {10, 20, 30, 40},
						 {15, 25, 35, 45},
						 {27, 29, 37, 48},
						 {32, 33, 39, 51}
								 };
				
				search(matrix, n, 32);
			}

		}
