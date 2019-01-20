## Java Patterns

### Character Pattern1
public class CharacterPattern1 {

	/*
	 
	 A
	 A B
	 A B C
	 A B C D
	 A B C D E
	 
	 
	*/
	
	public static void main(String[] args) {
		int steps = 5; 
		char ch = 0;
		for(int row =1; row <= steps; row++ ) {
			ch = 'A';
			for(int column =1; column<=row; column++) {
				System.out.print(ch+" ");
				ch++; 
			}
			System.out.println();
		}
	}
	
}

---------------------------
### Character Pattern2
public class CharacterPattern2 {
	
	/*
		
		A
		B C 
		D E F
		G H I J
		K L M N O
	*/
	
	public static void main(String[] args) {
		int steps = 5, alphabet = 'A';
		for (int row = 1; row <= steps; row++) {
			for (int column = 1; column <= row; column++) {
				System.out.print((char)alphabet+" ");
				alphabet++;
			}
			
			System.out.println();
		}
	}
}
-------------------------------

### Fibonacci Triangle
public class FibonacciTriangle {
	
	/*
	    1 
		1 2 
		1 2 3 
		1 2 3 5 
		1 2 3 5 8 
		1 2 3 5 8 13 
		1 2 3 5 8 13 21 
	 
	*/

	public static void main(String[] args) {

		int steps = 15;
		for (int row = 1; row <= steps; row++) {
			int n1 = 0, n2 = 1, n3 = 0;
			for (int column = 1; column <= row; column++) {

				n3 = n1 + n2;

				System.out.print(n3 + " ");
				n1 = n2;
				n2 = n3;

			}
			System.out.println();
		}

	}
	
--------------------------------------
### Floyds Triangle

package pyramids.exercise2;

public class FloydsTriangle {
	
	/*
	 
	   1 
		2 3 
		4 5 6 
		7 8 9 10 
		11 12 13 14 15 
		16 17 18 19 20 21 
		22 23 24 25 26 27 28 
		29 30 31 32 33 34 35 36 

	*/

	public static void main(String[] args) {
		int steps = 8, number = 1;
		for (int row = 1; row <= steps; row++) {
			for (int column = 1; column <= row; column++) {
				System.out.print(number+" ");
				number++;
			}
			System.out.println();

		}

	}

}
----------------------------

### Pascal Triangle


public class PascalTriangle {
	
	/*
	 * 
	 *        1 
		     1 1 
		    1 2 1 
		   1 3 3 1 
		  1 4 6 4 1 
		 1 5 10 10 5 1 
		1 6 15 20 15 6 1 

	 * 
	 * 
	 * 
	*/

	public static void main(String[] args) {

		int steps = 7;

		for (int row = 1; row <= steps; row++) {
			int temp = 1;
			for (int space = 1; space <= steps - row; space++) {
				System.out.print(" ");
			}
			for (int column = 1; column <= row; column++) {
				System.out.print(temp + " ");
				temp = temp * (row - column) / column;
			}
			System.out.println();
		}

	}

}

-------------------------------------

### Patter12
public class Patter12 {
	
	
	/*
	  1 2 3 4 5 6 5 4 3 2 1
	  1 2 3 4 5   5 4 3 2 1	
	  1 2 3 4       4 3 2 1
	  1 2 3		      3 2 1
	  1	2               2 1 
	  1			          1
	  1                   1
	  1 2			    2 1
	  1 2 3           3 2 1
	  1 2 3 4       4 3 2 1
	  1 2 3 4 5   5 4 3 2 1
	  1 2 3 4 5 6 5 4 3 2 1 
	 */
	
	public static void main(String[] args) {
		int steps =5, odd = 2, rowDecrement = 6, rowDecrementSecondHalf=5, spaceCount=1;
		for (int row = 1; row <= steps * 2 + 2; row++) {
			
			
			for(int column = 1; column <= rowDecrement; column++) {
				System.out.print(column+" ");
			}
			for(int space=spaceCount; space> 1; space--) {
				System.out.print("$$");
			}
			for(int column = rowDecrement; column >= 1; column--) {
				System.out.print(column+" ");
			} 
			System.out.println();
			odd += 2;
			rowDecrement--; 
			rowDecrementSecondHalf--;
			spaceCount+=2;
		}
	}

}
-----------------------------------------

### Pattern1

public class Pattern1 {

	/*
	 *  1 
		1 2 
		1 2 3 
		1 2 3 4 
		1 2 3 4 5 
		1 2 3 4 
		1 2 3 
		1 2 
		1 

	 * 
	 */

	public static void main(String[] args) {

		int steps = 5, colValue = 1;

		for (int row = 1; row <= steps * 2 - 1; row++) {
			for (int column = 1; column <= colValue; column++) {
				System.out.print(column + " ");
			}
			System.out.println();
			if (row < steps) {
				colValue++;
			} else {
				colValue--;
			}
		}

	}

}

--------------------------------------

### Pattern2

public class Pattern2 {
	
	/*
	 *  1 2 3 4 5 
		1 2 3 4 
		1 2 3 
		1 2 
		1 
		1 
		1 2 
		1 2 3 
		1 2 3 4 
		1 2 3 4 5 

	*/
	public static void main(String[] args) {
		
		int steps = 5, columnValue = steps;
		for(int row =1; row <= steps *  2;row ++) {
			if(row == steps + 1) {
				columnValue =1;
			}
			for(int column =1; column <= columnValue; column++) {
				
				System.out.print(column+" ");
			}
			System.out.println();
			if(row < steps) {
				columnValue--;
			} else {
				columnValue++;
			}
		}
	}

}
----------------------------------
### Pattern20

public class Pattern20 {

	
	/*
		
		*       *****************       *
		**      ********  *******      **
		***     *******    ******     ***
		****    ******      *****    ****
		*****   *****        ****   *****
		******  ****          ***  ******
		******* ***            ** *******
		**********              *********
	
	
	*/
	
	
	public static void main(String[] args) {
		
		int steps = 8;
		for(int row = 1; row<=steps; row++) {
			
			for(int column = 1; column <= row; column++) {
				System.out.print("*");
			}
			for (int space = 1; space <= steps -row; space++) {
				System.out.print(" ");
			}
			
			for(int column=9; column >= row; column--) {
				System.out.print("*");
			}
			for (int space = 1; space < row; space++) {
				System.out.print(" ");
			}
			
			for(int space = 1; space < row; space++) {
				System.out.print(" ");
			}
			for( int column = 9; column>=row; column--) {
				System.out.print("*");
			}
			
			for(int space = 8; space > row; space--) {
				System.out.print(" ");
			}
			
			for(int column =1; column <= row; column ++) {
				System.out.print("*");
			}
			
			System.out.println();
			
			
		}
		
		
		
	}
	
}
----------------------------------

### Pattern3


public class Pattern3 {
	
	/*
	 *  5 4 3 2 1 
	 *	4 3 2 1 
	 *	3 2 1 
	 *	2 1 
	 *	1 
	 *	1 
	 * 	2 1 
	 *	3 2 1 
	 *	4 3 2 1 
	 *	5 4 3 2 1 
	 * 
	 */
	public static void main(String[] args) {

		int steps = 5, columnValue = steps;
		for (int row = 1; row <= steps * 2; row++) {
			if (row == steps + 1) {
				columnValue = 1;
			}
			for (int column = columnValue; column >= 1; column--) {
				System.out.print(column + " ");
			}
			System.out.println();
			if (row < steps) {
				columnValue--;
			} else {
				columnValue++;
			}
		}

	}

}
----------------------------------

### Pattern4

public class Pattern4 {
	
	/*
	 *      1 
		   1 2 
		  1 2 3 
		 1 2 3 4 
		1 2 3 4 5 
	*/
	
	public static void main(String[] args) {
		int steps = 5;
		for (int row = 1; row <= steps; row++) {
			for (int space = 1; space <= steps - row; space++) {
				System.out.print(" ");
			}
			for (int column = 1; column <= row; column++) {
				System.out.print(column+" ");
			}
			System.out.println();
		}

	}

}
----------------------------------

### Pattern5


public class Pattern5 {
	
	/*
	 * 
	5 4 3 2 1 
	5 4 3 2 
	5 4 3 
	5 4 
	5 

	*/
	public static void main(String[] args) {
		int steps =5;
		for (int row =1; row <= steps; row++) {
			for (int column =5; column>=row; column--) {
				System.out.print(column+ " ");
			}
			System.out.println();
		}
		
	}

}
-------------------------------

### Pattern6


public class Pattern6 {
	
	/*
	 *  5 
		5 4 
		5 4 3 
		5 4 3 2 
		5 4 3 2 1 

	
*/
	public static void main(String[] args) {

		int steps = 5;
		for (int row = steps; row >= 1; row--) {
			for (int column = 5; column >= row; column--) {
				System.out.print(column+" ");
			}
			System.out.println();
		}

	}

}

-----------------------------------------
### Pattern7


public class Pattern7 {

	/*
	 *  1 
		2 3 
		4 5 6 
		7 8 9 10 
		11 12 13 14 15 

	
	*/
	
	public static void main(String[] args) {
		int steps = 5, number = 1;

		for (int row = 1; row <= steps; row++) {
			for (int column = 1; column <= row; column++) {
				System.out.print(number+" ");
				number++;
			}
			System.out.println(); 

		}

	}
}
---------------------------------------------
### Pattern8


public class Pattern8 {
	
	/*
	 *  1 
		2 7 
		3 8 13 
		4 9 14 19 
		5 10 15 20 25 

	*/

	public static void main(String[] args) {

		int steps = 5;
		for (int row = 1; row <= steps; row++) {
			int columnValue = row;
			for (int column = 1; column <= row; column++) {
				System.out.print(columnValue+" ");
				columnValue = columnValue + 5;
			}
			System.out.println();
		}

	}

}
----------------------------------------------

### Pattern9


public class Pattern9 {
	
	/*
	 * 
	          1 
		    1 2 1 
		  1 2 3 2 1 
		1 2 3 4 3 2 1 
		  1 2 3 2 1 
		    1 2 1 
		      1 
 

	*/
	
	public static void main(String[] args) {
		
		int steps = 7, odd=1, spaceCount = steps/2;
		for(int row=1; row <=steps ; row++) {
			int columnValue =1;
			
			for(int space = 1; space<=spaceCount; space++) {
				System.out.print("  ");
			}
			
			for(int column =1; column <= odd; column++) {
				System.out.print(columnValue+ " ");
				
				int middle = odd/2 +1;
				if(column < middle) {
					columnValue++;
				} else {
					columnValue--;
				}
			}
			
			if(row < steps/2 +1) {
				odd +=2;
				spaceCount--;
			} else {
				odd -=2;
				spaceCount++;
			}
			System.out.println();
		}
		
		
	}

}
------------------------------------------------------
### Square Pattern1

public class SquarePattern1 {

	/*
	 
	  
		* * * * * * 
		*         * 
		*         * 
		*         * 
		*         * 
		* * * * * * 
		
		******
		*    *
		*    *
		*    *
		*    *
		******

	
	*/
	
	
	public static void main(String[] args) {
		int steps = 6;
		for(int row =1; row <= steps; row++) {
			if(row == 1|| row== steps) {
				for(int column = 1; column<=steps; column++) {
					System.out.print("*");
				}
			} else {
				for(int column = 1; column<=steps; column++) {
					if(column ==1 || column ==steps) {
						System.out.print("*");
					} else {
						System.out.print(" "); 
					}
				}
			}
			
			System.out.println();
		}
	}
	
	
}


----------------------------------------
### Pattern 10


public class Pattern10 {
	
	/*
	 * 
	          1 
		     1 2 
		    1 2 3 
		   1 2 3 4 
		  1 2 3 4 5 
		 1 2 3 4 5 6 
		1 2 3 4 5 6 7 
		 1 2 3 4 5 6 
		  1 2 3 4 5 
		   1 2 3 4 
		    1 2 3 
		     1 2 
		      1 

	*/
	public static void main(String[] args) {
		
		int steps = 7, rowCount = 1, spaceCount=steps - 1;
		for(int row =1 ; row <= steps * 2 -1; row++) {
			
			for(int space =1; space <= spaceCount; space++) {
				System.out.print(" ");
			}
			
			for (int column =1; column <= rowCount; column++) {
				System.out.print(column+" ");
			}
			System.out.println();
			if(row < steps) {// 1,2,3,4
				rowCount++;//2,3,4,5
				spaceCount--;
			} else {
				rowCount--;
				spaceCount++;
			}
		}
		
		
	}

}

---------------------------------------
### Pattern11

public class Pattern11 {
	
	/*
		12345    
		 2345
		  345
		   45
		    5
		    5
		   45
		  345
		 2345
		12345
		
		
		
	1 2 3 4 5       
	 2 3 4 5 
	  3 4 5 
	   4 5 
	    5 
	    5 
	   4 5 
	  3 4 5 
	 2 3 4 5 
	1 2 3 4 5 
		
	*/	
	public static void main(String[] args) {
		int steps =5, columnValues=1, spaceCount= steps;
		
		for(int row =1; row<= steps *2; row++) {
			
			if(row == steps + 1) {
				columnValues = steps;
				spaceCount = 1;
			}
			for(int space = spaceCount; space < steps; space++) {
				System.out.print(" ");
			}
			
			for(int column = columnValues; column <= steps*2; column++) {
				System.out.print(column+" ");
			}
			System.out.println();
			if(row < steps ) {
				columnValues++;
				spaceCount--;
			} else {
				columnValues--;
				spaceCount++;
			}
		}
	}
}
--------------------------------
### Pattern12


public class Pattern12 {

	/*
	 	1 2 3 4 5 4 3 2 1 
		2 3 4 5 4 3 2 
		3 4 5 4 3 
		4 5 4 
		5 
	
	*/
	
	public static void main(String[] args) {
		
		int steps=5;
		for(int row = 1; row<=steps; row++) {
			for(int column = row; column <= steps; column++) {
				System.out.print(column+" ");
			}
			
			for(int column = steps -1; column >= row; column-- ) {
				System.out.print(column+" ");
			}
			System.out.println();
		}
	}
}

----------------------------------------------
Pattern13


public class Pattern13 {

	/*
	 
	    5 5 5 5 5 
		4 5 5 5 5 
		3 4 5 5 5 
		2 3 4 5 5 
		1 2 3 4 5 
	*/
	
	public static void main(String[] args) {
		
		int steps = 5,spaceCount= steps;
		for(int row =steps ; row >=1; row-- ) {
			for(int column =row; column <=steps; column++) {
				System.out.print(column+" ");
			}
			for(int space = spaceCount - 1; space >=1; space --) {
				System.out.print(steps+" ");
			}
			System.out.println();
			spaceCount--;
		}
		
	}
	
}


--------------------------------------------------
Pattern14

public class Pattern14 {
	
	/*
	    1 
		2 6 
		3 7 10 
		4 8 11 13 
		5 9 12 14 15 
	*/
	
	public static void main(String[] args) {
		int steps = 10;
		for (int row = 1; row <= steps; row++) {
			int temp = row;
			for (int column = 1; column <= row; column++) {
				System.out.print(temp+" ");
				temp = steps + temp - column;
			}
			System.out.println();
		}
	}

}


-----------------------------------------------------
Pattern15

public class Pattern15 {

	
	/*
	    1 
		2 4 
		3 6 9 
		4 8 12 16 
		5 10 15 
		6 12 
		7
	
	*/
	
	
	public static void main(String[] args) {
		int steps = 7,columnCount=1; 
		for(int row = 1; row <=7; row++) {
			int temp = row;
			for(int column=1; column<= columnCount; column++) {
				System.out.print(temp+ " ");
				temp = row * (column+1); 
			}
			if(row < steps/2 +1) {
				columnCount++;
			} else {
				columnCount--;
			}
			System.out.println();
			
		}
		
	}
}

------------------------------------------------------------
Pattern16

public class Pattern16 {
	
	/*
	 	5 5 5 5 5 
		5 4 4 4 4 
		5 4 3 3 3 
		5 4 3 2 2 
		5 4 3 2 1  
	 */	
	
	public static void main(String[] args) {

		int steps = 5;
		for (int row = steps; row >= 1; row--) {
			for (int column = steps; column >= row; column--) {
				System.out.print(column + " ");
			}
			for (int space = row - 1; space >= 1; space--) {
				System.out.print(row+" ");
			}
			System.out.println();
		}
	}

}

-------------------------------------------------------------------------
Pattern17

public class Pattern17 {

	/*
	 * 
		5 
		4 5 4 
		3 4 5 4 3 
		2 3 4 5 4 3 2 
		1 2 3 4 5 4 3 2 1 
		2 3 4 5 4 3 2 
		3 4 5 4 3 
		4 5 4 
		5
	*/
	
	public static void main(String[] args) {
		int steps = 9, odd = 1, count = 0; 
		for(int row = 1; row <= steps * 2 - 1; row++) {
			
			int rowValue = steps - count;
			
			for(int column=1; column <= odd; column++) {
				System.out.print(rowValue+" ");
				
				int middleColumn = odd / 2 + 1;
				if(column < middleColumn) {
					rowValue++;
				} else {
					rowValue--;
				}
			}
			System.out.println();
			
			if(row < steps) {
				count++;
				odd+=2;
			} else {
				count--;
				odd-=2;
			}
		}
		
		
	}
	
}


-----------------------------------------------------
Pattern18


public class Pattern18 {
	
	/*
	 * 
 	    1 
	   1 2 
	  1 2 3 
	 1 2 3 4 
	1 2 3 4 5 
	 1 2 3 4 
	  1 2 3 
	   1 2 
	    1 
	    
	    1
	   12
	  123
	 1234
	12345
	 1234
	  123
	   12
	    1
	    
	    1
		12
		123
		1234
		12345
		1234
		123
		12
		1

	    
	    
	*/

	public static void main(String[] args) {

		int steps = 9, columnCount = 1, spaceCount = steps / 2;

		for (int row = 1; row <= steps; row++) {

//			for (int space = spaceCount; space >= 1; space--) {
//				System.out.print(" ");
//			}

			for (int column = 1; column <= columnCount; column++) {
				System.out.print(column);
			}
			System.out.println();
			if (row < steps / 2 + 1) {
				columnCount++;
				spaceCount--;
			} else {
				spaceCount++;
				columnCount--;
			}
		}

	}

}


-------------------------------------
Pattern19

public class Pattern19 {
	
	/*
		    1 
	      2 1 2 
	    3 2 1 2 3 
	  4 3 2 1 2 3 4 
	5 4 3 2 1 2 3 4 5 
	  6 5 4 3 4 5 6 
	    7 6 5 6 7 
	      8 7 8 
	        9 
	
	 */	
	
	public static void main(String[] args) {

		int steps = 9, odd = 1, spaceCount = steps/2;
		for (int row = 1; row <= steps; row++) {

			int columnValue = row;

			for (int space = spaceCount; space >= 1; space--) {
				System.out.print("  ");
			}

			for (int col = 1; col <= odd; col++) {
				System.out.print(columnValue + " ");

				int middleColumn = odd / 2 + 1;

				if (col < middleColumn) {
					columnValue--;
				} else {
					columnValue++;
				}
			}
			System.out.println();
			if (row < steps / 2 + 1) {
				odd += 2;
				spaceCount--;
			} else {
				odd -= 2;
				spaceCount++;
			}
		}

	}

}
---------------------------------------------------




