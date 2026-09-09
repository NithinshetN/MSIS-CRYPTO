# 3_CRYPTOLABAssignment

## Python Basics and Debugging

### 1. Debug the following programs. Identify the type of error in each case.

#### Original Code:

```python
print("Welcome to Cryptology Lab)
message = "Python Programming"
print(mesage)
num = input("Enter a number: ")
result = num + 10
print(result)
```

#### Debugged Solution:

- **Program 1 Error:** `SyntaxError` (Unterminated string literal).
- **Program 2 Error:** `NameError` (Variable `mesage` is misspelled).
- **Program 3 Error:** `TypeError` (Cannot add an integer to a string from `input()`).

```python

print("Welcome to Cryptology Lab")

msg="Python Programming"
print(msg)

n=int(input("Enter a number: "))
res=n+10
print(res)
```

---

### 2. Write Python statements to display the following exactly:

```
Welcome to Cryptology Lab
It's interesting to learn Python.
Students, "Welcome to the Cryptology Lab".
```

#### Solution:

```python
print("Welcome to Cryptology Lab")
print("It's interesting to learn Python.")
print('Students, "Welcome to the Cryptology Lab".')
```

---

### 3. Read two numbers from the user and perform:

- Addition
- Subtraction
- Multiplication
- Division
- Integer division
- Remainder
- Exponentiation

Display each result with an appropriate message.

#### Solution:

```python
a = float(input("Enter first number: "))
b = float(input("Enter second number: "))

print(f"Addition:{a} +{b} ={a + b}")
print(f"Subtraction:{a} -{b} ={a - b}")
print(f"Multiplication:{a} *{b} ={a * b}")

if b != 0:
    print(f"Division:{a} /{b} ={a / b}")
    print(f"Integer division:{a} //{b} ={a // b}")
    print(f"Remainder:{a} %{b} ={a % b}")
else:
    print("Division, integer division and remainder by zero are undefined.")

print(f"Exponentiation:{a} **{b} ={a ** b}")
```

---

### 4. Read a floating-point number and display:

- its data type;
- its absolute value;
- the value rounded to two decimal places.

#### Solution:

```python
x = float(input("Enter a floating-point number: "))
print("Data type:", type(x))
print("Absolute value:", abs(x))
print("Rounded to two decimal places:", round(x, 2))
```

---

## Part B — Data Types and Collections

### 5. Create variables containing examples of: int, float, complex, str, list, tuple, set, and dictionary. Use Python to display the value and data type of each variable.

#### Solution:

```python
a = 15
b = 10.5
c = 3 + 4j
d = "Cryptology"
e = [1, 2, 3]
f = (10, 20)
g = {1, 2, 3}
h = {"cipher": "RSA", "bits": 2048}

items = [a, b, c, d, e, f, g, h]
for i in items:
    print(f"Value:{i} | Type:{type(i)}")
```

---

### 6. Demonstrate experimentally that: Strings are immutable, whereas lists are mutable. Include the Python statements you used and explain the observed result.

#### Solution:

```python
# string immutability
s = "Python"
try:
    s[0] = "J"
except TypeError as e:
    print("Error:", e)

# list mutability
lst = [10, 20, 30]
print("Before:", lst)
lst[0] = 99
print("After:", lst)
```

- **Explanation:** Trying to change a character of the string raises a `TypeError` since strings can’t be modified once created. Lists don’t have this restriction — individual elements can be reassigned directly.

---

### 7. Create a list containing five prime numbers. Perform the following:

- display the first three elements;
- display the last element;
- append another prime number;
- extend the list with two more prime numbers;
- display the total number of elements.

#### Solution:

```python
primes = [2, 3, 5, 7, 11]
print("First three:", primes[:3])
print("Last element:", primes[-1])

primes.append(13)
print("After append:", primes)

primes.extend([17, 19])
print("After extend:", primes)

print("Total elements:", len(primes))
```

---

## Part C — String Operations

*For Questions 8–12, use:* `message = "CRYPTOLOGY USING PYTHON"`

### 8. Display: length of the string; first five characters; last six characters; characters from positions 3 to 8; string in reverse order.

#### Solution:

```python
msg = "CRYPTOLOGY USING PYTHON"
print("Length:", len(msg))
print("First 5 chars:", msg[:5])
print("Last 6 chars:", msg[-6:])
print("Positions 3-8:", msg[3:9])
print("Reversed:", msg[::-1])
```

---

### 9. Perform the following: convert to lowercase; convert back to uppercase; check whether “PYTHON” exists in the string; replace “PYTHON” with “PROGRAMMING”.

#### Solution:

```python
msg = "CRYPTOLOGY USING PYTHON"
low = msg.lower()
print("Lowercase:", low)
print("Back to upper:", low.upper())
print("'PYTHON' in string?", "PYTHON" in msg)
print("Replaced:", msg.replace("PYTHON", "PROGRAMMING"))
```

---

### 10. Remove the spaces from the string and display the resulting string.

#### Solution:

```python
msg = "CRYPTOLOGY USING PYTHON"
no_space = msg.replace(" ", "")
print("Without spaces:", no_space)
```

---

### 11. Using a loop, display every character and its corresponding Unicode/ASCII value using ord().

#### Solution:

```python
msg = "CRYPTOLOGY USING PYTHON"
for ch in msg:
    print(ch, "->", ord(ch))
```

---

### 12. Use chr() to convert the following values into characters: 65, 67, 73, 80, 72, 69, 82. Combine the resulting characters and identify the word.

#### Solution:

```python
vals = [65, 67, 73, 80, 72, 69, 82]
word = ""
for v in vals:
    word += chr(v)
print("Decoded word:", word)
```

- **Resulting Word:** **ACIPHER**

---

## Part D — Text Processing for Cryptology

### 13. Plaintext preprocessing: Read a message from the user and: remove leading/trailing spaces; convert it to uppercase; remove spaces between words.

- **Example Input:** `meet me tomorrow` -> **Output:** `MEETMETOMORROW`

#### Solution:

```python
raw = input("Enter a message: ")
out = raw.strip().upper().replace(" ", "")
print("Output:", out)
```

---

### 14. Character grouping: Read a string and divide it into blocks of five characters.

- **Example Input:** `CRYPTOLOGYLAB` -> **Output:** `CRYPT`, `OLOGY`, `LAB`

#### Solution:

```python
s = input("Enter a string: ").replace(" ", "")
for i in range(0, len(s), 5):
    print(s[i:i+5])
```

---

### 15. Padding: Modify Question 14 so that an incomplete final block is padded with X.

- **Example Input:** `CRYPTOLOGYLAB` -> **Output:** `CRYPT`, `OLOGY`, `LABXX`

#### Solution:

```python
s = input("Enter a string: ").replace(" ", "")
rem = len(s) % 5
if rem != 0:
    s += "X" * (5 - rem)

for i in range(0, len(s), 5):
    print(s[i:i+5])
```

---

### 16. Character frequency: For the text = “CRYPTOLOGYISINTERESTING”, write a program to calculate the frequency of each character. Then identify the most frequently occurring character.

#### Solution:

```python
text = "CRYPTOLOGYISINTERESTING"
freq = {}
for ch in text:
    freq[ch] = freq.get(ch, 0) + 1

print("Frequencies:", freq)
top_char = max(freq, key=freq.get)
print(f"Most frequent: '{top_char}' ->{freq[top_char]}")
```

---

### 17. Percentage frequency: Extend Question 16 to calculate Percentage Frequency = (Frequency of Character / Total Number of Characters) * 100. Display the percentage rounded to two decimal places.

#### Solution:

```python
text = "CRYPTOLOGYISINTERESTING"
n = len(text)
freq = {}
for ch in text:
    freq[ch] = freq.get(ch, 0) + 1

for ch, cnt in freq.items():
    pct = (cnt / n) * 100
    print(f"{ch}:{pct:.2f}%")
```

---

## Part E — Mathematical Foundations for Cryptology

### 18. Modular arithmetic: Use Python to evaluate: 29 mod 26, 55 mod 26, 78 mod 26, -3 mod 26, -29 mod 26. Then write a program that accepts an integer and calculates the integer modulo 26.

#### Solution:

```python
print(29 % 26)
print(55 % 26)
print(78 % 26)
print(-3 % 26)
print(-29 % 26)

n = int(input("Enter an integer: "))
print(f"{n} mod 26 ={n % 26}")
```

---

### 19. Alphabet representation: Using A=0, B=1,…, Z=25, write a program that accepts an uppercase character and displays its numerical representation. Also perform the reverse conversion.

#### Solution:

```python
c = input("Enter character: ").upper()
n = ord(c) - ord('A')
print(f"{c} ->{n}")

k = int(input("Enter number (0-25): "))
c2 = chr(k + ord('A'))
print(f"{k} ->{c2}")
```

---

### 20. Prime numbers: Write a program to: determine whether a given number is prime; display all prime numbers within a range specified by the user.

#### Solution:

```python
def is_prime(n):
    if n <= 1:
        return False
    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            return False
    return True

num = int(input("Enter number to check: "))
print(f"Is{num} prime?{is_prime(num)}")

lo = int(input("Enter lower range: "))
hi = int(input("Enter upper range: "))
result = []
for x in range(lo, hi + 1):
    if is_prime(x):
        result.append(x)
print("Primes in range:", result)
```

---

### 21. GCD and coprimes: Read two integers from the user. Find their GCD and determine whether they are coprime. Test your program with: 15 and 26; 18 and 24; 17 and 26.

#### Solution:

```python
import math

def check_coprime(a, b):
    g = math.gcd(a, b)
    print(f"({a},{b}) -> GCD ={g}, Coprime ={g == 1}")

check_coprime(15, 26)
check_coprime(18, 24)
check_coprime(17, 26)
```

---

### 22. Write a program to get the multiplicative inverse of an integer b (modulo 26).

#### Solution:

```python
def mod_inverse(b, m=26):
    orig_m = m
    x0, x1 = 0, 1
    if m == 1:
        return None
    while b > 1:
        if m == 0:
            return None
        q = b // m
        b, m = m, b % m
        x0, x1 = x1 - q * x0, x0
    if x1 < 0:
        x1 += orig_m
    return x1

b = int(input("Enter integer b: "))
inv = mod_inverse(b, 26)
if inv:
    print(f"Inverse of{b} mod 26 is{inv}")
else:
    print(f"No inverse exists for{b} mod 26.")
```

---

## Part F — Challenge / Bonus

### 23. WAP in python to implement client and server communication.

“Whether you succeed or not is irrelevant - there is no such thing. Making your known is the important thing” — Art and Letters, Georgia O’Keeffe.

#### Solution (Server Side Code):

```python
import socket

def start_server():
    srv = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    srv.bind(('127.0.0.1', 12345))
    srv.listen(1)
    print("Waiting for client...")

    conn, addr = srv.accept()
    data = conn.recv(1024).decode()
    print("Received:", data)

    conn.send("Message received by server.".encode())
    conn.close()
    srv.close()

if __name__ == "__main__":
    start_server()
```

#### Solution (Client Side Code):

```python
import socket

def start_client():
    cli = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    cli.connect(('127.0.0.1', 12345))

    msg = "Making your known is the important thing. --- Georgia O'Keeffe"
    cli.send(msg.encode())

    reply = cli.recv(1024).decode()
    print("Server reply:", reply)
    cli.close()

if __name__ == "__main__":
    start_client()
```