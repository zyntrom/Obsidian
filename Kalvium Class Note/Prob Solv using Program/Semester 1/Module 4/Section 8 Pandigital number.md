## 🔹 Problem Restatement

We need to check if a number is **pandigital**.  
A number is pandigital if it contains **all digits from 1 to N exactly once**, where **N** is the number of digits in the number.

---

## 🔹 Step-by-Step Approach

1. **Extract digits manually**
    - Use modulo (`% 10`) to get the last digit.
    - Use integer division (`// 10`) to remove the last digit.
    - Store the digits.
2. **Count total digits (N)**
    - While extracting digits, count how many digits there are.
3. **Check conditions for pandigital**
    - All digits must be **between 1 and N**.
    - No digit should repeat.
    - The number must contain **all digits from 1 to N**.

---

## 🔹 Universal Python Code

```python
n = int(input())
cpn = n
count = 0
sum_digits = 0

while n != 0:
    count += 1
    sum_digits += n % 10
    n //= 10

n = cpn
disum = 0
for i in range(1, count + 1):
    disum += i

if sum_digits == disum:
    print("Yes")
else:
    print("No")

```

---

## C++ Program:

```cpp
#include <cstdio>
#include <iostream>
using namespace std;
int main() {
	int n;
	cin>>n;
	int cpn=n;
	int count =0;
	int sum=0;
	while(n!=0){
		count++;
		sum+=n%10;
		n/=10;
	}
	n=cpn;
	int disum=0;
	for(int i=1;i<=count;i++){
		disum+=i;
	}
	if(sum==disum){
		cout<<"Yes";
	}
	else{
		cout<<"No";
	}
	return 0;
}
```

## Java Program:

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int cpn = n;
        int count = 0;
        int sum = 0;
        while (n != 0) {
            count++;
            sum += n % 10;
            n /= 10;
        }
        n = cpn;
        int disum = 0;
        for (int i = 1; i <= count; i++) {
            disum += i;
        }
        if (sum == disum) {
            System.out.println("Yes");
        } else {
            System.out.println("No");
        }
    }
}

```
## 🔹 Example Walkthrough

### Input:

```
54321
```
### Process:

- Extract digits → [1, 2, 3, 4, 5]
- Count = 5
- Check range → all digits are between 1 and 5 ✅
- Check duplicates → none ✅
- Check if all numbers from 1 to 5 exist → yes ✅

### Output:

```
Yes
```