Fibonacci Series: Write a simple Java program which will print Fibonacci series e.g. 1 1 2 3 5 8 13 ... . up to a given number. Be prepare for cross questions like using iteration over recursion and how to optimize the solution using caching and memoization.

	Code Snippet:
	
		public static int fibonacciRecursion(int number) {
			if(number <= 1) {
				return number;
			}
			
			return fibonacciRecursion(number -1) + fibonacciRecursion(number - 2);
		}
		
		public static void fibonacci(int number) {
			int num1 = 0, num2 = 1, sum = 1;
			System.out.print(num1+" ");
			for(; sum < number; ) {
				System.out.print(sum+" ");
				sum = num1 + num2;
				num1 = num2;
				num2 = sum;
			}
		}
		
		static Map<Integer, Integer> cache = new HashMap<>();
		static int impCount;
		public static int improvedFibonacci(int number) {
			impCount++;
			if (number <= 1) {
				return number;
			}

			if (cache.get(number) != null) {
				return cache.get(number);
			}
			int fibValue = improvedFibonacci(number - 1) + improvedFibonacci(number - 2);
			cache.put(number, fibValue);
			return fibValue;
		}
		
		public static void main(String[] args) {
			fibonacci(100);

			for (int i = 0; i <= 10; i++) {
				System.out.print(fibonacciRecursion(i) + " ");
			}
		}
		
		static Map<Integer, Integer> cache = new HashMap<>();
		static int impCount;
		public static int improvedFibonacci(int number) {
			impCount++;
			if (number <= 1) {
				return number;
			}

			if (cache.get(number) != null) {
				return cache.get(number);
			}
			int fibValue = improvedFibonacci(number - 1) + improvedFibonacci(number - 2);
			cache.put(number, fibValue);
			return fibValue;
		}
-----------------------------------------------------------------
Prime number:  Write a Java program to check if a given number is prime or not. Remember, a prime number is a number which is not divisible by any other number e.g. 3, 5, 7, 11, 13, 17 etc. Be prepared for cross e.g. checking till the square root of a number etc.
	
	Code Snippet:
	
		public static boolean isPrime(int number) {
			for (int i = 2; i < number; i++) {
				if (number % i == 0) {
					return false;
				}
			}
			return true;
		}
		
		public static void main(String[] args) {
			int number = 101;
			for(int i = 2; i <=number; i++) {
				if(isPrime(i)) {
					System.out.println(i);
				}
			}
		}
		
-----------------------------------------------------------------
Integer Palindrome: This is generally asked as follow-up or alternative of the previous program. This time you need to check if given Integer is palindrome or not. An integer is called palindrome if its equal to its reverse e.g. 1001 is a palindrome but 1234 is not because the reverse of 1234 is 4321 which is not equal to 1234. You can use divide by 10 to reduce the number and modulus 10 to get the last digit. This trick is used to solve this problem.


	Code Snippet:
	
		public static int reverse(int number) {
			int reverse = 0;
			while(number!= 0) {
				reverse = reverse * 10 + number% 10;
				number  = number / 10;
			}
			return reverse;
		}
		
		public static boolean isPalindrome(int number) {
			return number == reverse(number);
		}
		
		public static void main(String[] args) {
			for (int i = 1; i <100000; i++) {
				if(isPalindrome(i)) {
					System.out.println(i);
				}
			}
		}

-----------------------------------------------------------------
Armstrong number: A number is called an Armstrong number if it is equal to the cube of its each digit. for example, 153 is an Armstrong number because 153= 1+ 125+27 which is equal to 1^3+5^3+3^3. You need to write a program to check if given number is Armstrong number or not.
	Code Snippet:
	
		public static boolean isAmstrong(int number) {
			int copyOfInput = number;
			int result = 0;

			while (copyOfInput != 0) {
				int lastDigit = copyOfInput % 10;
				result = result + (lastDigit * lastDigit * lastDigit);
				copyOfInput = copyOfInput / 10;

			}
			return result == number;
		}
		
		public static void main(String[] args) {
			
			for(int i = 1; i< 100000000; i++) {
				if (isAmstrong(i)) {
					System.out.println(i);
				}
			}
			
		}
------------------------------------------------------------------------
GCD: GCD of two numbers


	Code Snippet:
	
		public static int gcd(int a, int b) {
			if (b == 0) {
				return a;
			}

			int gcd = gcd(b, a % 10);
			return gcd;
		}

		public static int gcd2(int num1, int num2) {
			int gcd = 1;
			for (int i = 1; i < num1 && i < num2; i++) {

				if (num1 % 1 == 0 && num2 % i == 0) {
					gcd = i;
				}
			}
			return gcd;
		}

		public static int lcm(int num1, int num2) {
			return (num1 * num2) / gcd(num1, num2);
		}

		
