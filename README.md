# Harshadnumber# Harshad Number — Assignment Submission

---

## Student Information

           

 **Name:**     Ridhikanta Sarkar Sumit <br>
 **ID:**       IT24045               
     

---

## What is a Harshad Number?

A **Harshad Number** (also called a Niven Number) is a positive integer that is **divisible by the sum of its digits**.

**Formula:**
```
digitSum = sum of all digits of n
if (n % digitSum == 0)  →  Harshad Number ✓
else                    →  NOT a Harshad Number ✗
```

**Example:**
```
n = 18
digitSum = 1 + 8 = 9
18 % 9 = 0  →  18 IS a Harshad Number ✓

n = 23
digitSum = 2 + 3 = 5
23 % 5 = 3  →  23 is NOT a Harshad Number ✗
```

---

## Task 1 — Check if a Number is Harshad (CMD Based)

### File: `HarshadCheck.java`

```java
// File: HarshadCheck.java
// Harshad Number: divisible by sum of its digits

public class HarshadCheck {

    // *** STEP 1: Calculate digit sum ***
    static int digitSum(int n) {
        int sum = 0;
        while (n > 0) {
            sum += n % 10;  // *** Extract last digit ***
            n /= 10;
        }
        return sum;
    }

    // *** STEP 2: Check Harshad condition ***
    static boolean isHarshad(int n) {
        int sum = digitSum(n);
        return n % sum == 0;  // *** Divisible = Harshad ***
    }

    public static void main(String[] args) {

        // *** CMD Input Check ***
        if (args.length == 0) {
            System.out.println("Usage: java HarshadCheck <number>");
            System.out.println("Example: java HarshadCheck 18");
            return;
        }

        // *** Parse & Validate Input ***
        int n = Integer.parseInt(args[0]);
        if (n <= 0) {
            System.out.println("Error: Enter a positive integer!");
            return;
        }

        int sum = digitSum(n);
        boolean result = isHarshad(n);

        // *** Display Result ***
        System.out.println("=================================");
        System.out.println("  Input Number : " + n);
        System.out.println("  Digit Sum    : " + sum);
        System.out.println("  " + n + " % " + sum + " = " + (n % sum));
        System.out.println("---------------------------------");
        if (result)
            System.out.println("  Result: " + n + " IS a Harshad Number ✓");  // *** Harshad ***
        else
            System.out.println("  Result: " + n + " is NOT a Harshad Number ✗");  // *** Not Harshad ***
        System.out.println("=================================");
    }
}
```

### How to Run (CMD)

```cmd
javac HarshadCheck.java
java HarshadCheck 18
java HarshadCheck 23
java HarshadCheck 720
```

### Sample Output

```
C:\> java HarshadCheck 18
=================================
  Input Number : 18
  Digit Sum    : 9
  18 % 9 = 0
---------------------------------
  Result: 18 IS a Harshad Number ✓
=================================

C:\> java HarshadCheck 23
=================================
  Input Number : 23
  Digit Sum    : 5
  23 % 5 = 3
---------------------------------
  Result: 23 is NOT a Harshad Number ✗
=================================
```

---

## Task 2 — LeetCode: Sum of Digits of Harshad Number

**Problem Link:** https://leetcode.com/problems/harshad-number/

**Problem Statement:**  
Given an integer `x`, return the **sum of its digits** if `x` is a Harshad number, otherwise return `-1`




 
 
      class Solution {
  
    public int sumOfTheDigitsOfHarshadNumber(int x) {
       
        int sum = 0;
      
        
        int temp = x;

        // *** STEP 1: Calculate digit sum ***
         while (temp > 0) {
            sum += temp % 10;  // *** Extract last digit and add ***
            temp /= 10;        // Remove last digit
        }

        // *** STEP 2: Return sum if Harshad, else -1 ***
        return (x % sum == 0) ? sum : -1;  // *** Core Harshad check ***
    }
}

### Sample Output

```
C:\> java HarshadNumber 18
=================================
  Input Number : 18
  Digit Sum    : 9
---------------------------------
  Harshad? YES  →  Output: 9
=================================

C:\> java HarshadNumber 23
=================================
  Input Number : 23
  Digit Sum    : 5
---------------------------------
  Harshad? NO   →  Output: -1
=================================
```

---

## Test Cases

| Input | Digit Sum | n % sum | Harshad? | Output |
|-------|-----------|---------|----------|--------|
| 1     | 1         | 0       | YES ✓    | 1      |
| 18    | 9         | 0       | YES ✓    | 9      |
| 23    | 5         | 3       | NO  ✗    | -1     |
| 720   | 9         | 0       | YES ✓    | 9      |
| 100   | 1         | 0       | YES ✓    | 1      |
| 19    | 10        | 9       | NO  ✗    | -1     |

---

## Key Logic Summary

```
digitSum(n)  →  sum of all digits
n % digitSum == 0  →  Harshad Number ✓
n % digitSum != 0  →  NOT a Harshad Number ✗
```

---

*Submitted by: Ridhikanta Sarkar Sumit | ID: IT24045*
