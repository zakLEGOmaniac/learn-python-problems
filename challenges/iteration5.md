# Iteration 5

### !challenge

* type: code-snippet
* language: python3.6
* id: 39be5abf-26c2-4d8c-be67-116467662bed
* title: multiply

### !question

Write a function called "multiply".

Given 2 numbers, "multiply" returns their product.

Notes:
* It should not use the multiply operator '*' anywhere in the code

```
output = multiply(4, 7)
print(output) # --> 28

output2 = multiply(-4, 70)
print(output2) # --> -280

output2 = multiply(4, -70)
print(output2) # --> -280

output2 = multiply(-4, -7)
print(output2) # --> 28

```

### !end-question

### !placeholder

```python
# your code here


```

### !end-placeholder

### !tests

```python
import main
import unittest
import inspect, re

class TestScript(unittest.TestCase):

    def test_0(self):
        # it should return a number
        self.assertIsInstance(main.multiply(5, 6), int,
        msg = 'should return a number')


    def test_1(self):
        # it should not use the multiply operator
        pattern = re.compile(r'\*')
        source = inspect.getsource(main.multiply)
        self.assertIsNone(pattern.search(source),
        msg = 'should not have the multiply operator in the function body')


    def test_2(self):
        # it should multiply two numbers
        self.assertEqual(main.multiply(6, 8), 48,
        msg = 'should multiply two numbers')


    def test_3_1(self):
        # it should multiply negative numbers
        self.assertEqual(main.multiply(6, -8), -48,
        msg = 'should multiply negative numbers')


    def test_3_2(self):
        # it should multiply negative numbers
        self.assertEqual(main.multiply(-6, 8), -48,
        msg = 'should multiply negative numbers')

    def test_3_2(self):
        # it should multiply negative numbers
        self.assertEqual(main.multiply(-6, -8), 48,
        msg = 'should multiply negative numbers')

    def test_4(self):
        # it should multiply with the second number as 0
        self.assertEqual(main.multiply(0, 10), 0,
        msg = 'should multiply with the second number as 0')


    def test_5(self):
        # it should multiply with the first number as 0
        self.assertEqual(main.multiply(0, -3), 0,
        msg = 'should multiply with the first number as 0')

```

### !end-tests

### !explanation
```python
def multiply(num1, num2):
    acc = 0
    for i in range(abs(num2)):
        acc += num1
    if (num1 < 0 and num2 > 0) or (num1 > 0 and num2 < 0):
        return -abs(acc)
    else:
        return abs(acc)


```
### !end-explanation

### !end-challenge
