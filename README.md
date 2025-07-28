#  Take Home Assignment: EP & BVA – Student Score Classification

##  Context

You are tasked with testing a function that determines the classification of students based on their scores. The function accepts an **integer score between 0 and 100 (inclusive)** and returns a string classification as follows:

- `"Fail"` for scores **0–49**
- `"Pass"` for scores **50–69**
- `"Merit"` for scores **70–89**
- `"Distinction"` for scores **90–100**

##  Objective

Design test cases using:
- **Equivalence Partitioning (EP)**
- **Boundary Value Analysis (BVA)**

---

##  1. Equivalence Classes

###  Valid Equivalence Classes
| Class | Input Range | Expected Output    |
|-------|-------------|--------------------|
| EC1   | 0–49        | "Fail"             |
| EC2   | 50–69       | "Pass"             |
| EC3   | 70–89       | "Merit"            |
| EC4   | 90–100      | "Distinction"      |

###  Invalid Equivalence Classes
| Class | Input Example | Reason            |
|-------|---------------|-------------------|
| EC5   | -1, -10       | Below 0           |
| EC6   | 101, 150      | Above 100         |
| EC7   | 50.5, "eighty"| Non-integer input |

---

##  2. Boundary Value Analysis (BVA)

Using **two-value BVA** (just below and above the boundaries):

| Range        | Boundary Values to Test       |
|--------------|-------------------------------|
| 0–49         | -1, 0, 1, 48, 49, 50          |
| 50–69        | 49, 50, 51, 68, 69, 70        |
| 70–89        | 69, 70, 71, 88, 89, 90        |
| 90–100       | 89, 90, 91, 99, 100, 101      |

---

##  3. Designed Test Cases

| **Test Case** | **Test Type**     | **Input** | **Expected Output**     | **Comment**                       |
|---------------|-------------------|-----------|--------------------------|------------------------------------|
| TC1           | EP Valid          | 25        | "Fail"                   | Typical value from EC1             |
| TC2           | EP Valid          | 55        | "Pass"                   | Typical value from EC2             |
| TC3           | EP Valid          | 75        | "Merit"                  | Typical value from EC3             |
| TC4           | EP Valid          | 95        | "Distinction"            | Typical value from EC4             |
| TC5           | EP Invalid        | -10       | Error / Invalid input    | From EC5                           |
| TC6           | EP Invalid        | 150       | Error / Invalid input    | From EC6                           |
| TC7           | EP Invalid        | 50.5      | Error / Invalid input    | From EC7 (non-integer)             |
| TC8           | BVA               | -1        | Error / Invalid input    | Just below lower boundary          |
| TC9           | BVA               | 0         | "Fail"                   | Lower boundary of Fail             |
| TC10          | BVA               | 1         | "Fail"                   | Just above lower boundary          |
| TC11          | BVA               | 49        | "Fail"                   | Upper boundary of Fail             |
| TC12          | BVA               | 50        | "Pass"                   | Lower boundary of Pass             |
| TC13          | BVA               | 69        | "Pass"                   | Upper boundary of Pass             |
| TC14          | BVA               | 70        | "Merit"                  | Lower boundary of Merit            |
| TC15          | BVA               | 89        | "Merit"                  | Upper boundary of Merit            |
| TC16          | BVA               | 90        | "Distinction"            | Lower boundary of Distinction      |
| TC17          | BVA               | 100       | "Distinction"            | Upper boundary of valid input      |
| TC18          | BVA               | 101       | Error / Invalid input    | Just above upper boundary          |

---

##  Total Test Cases: 18
- **EP-based:** 7 test cases  
- **BVA-based:** 11 test cases
