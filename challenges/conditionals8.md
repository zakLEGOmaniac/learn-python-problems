# Conditionals 8

### !challenge

* type: code-snippet
* language: python3.6
* id: f328e513-d275-4a7b-aa70-b3ac917ce57a
* title: convert_score_to_grade

### !question

Write a function called "convert_score_to_grade".

Given a score, "convert_score_to_grade" returns a string representing the letter grade corresponding to the given score.

Notes:
* (100 - 90) --> 'A'
* (89  - 80) --> 'B'
* (79  - 70) --> 'C'
* (69  - 60) --> 'D'
* (59  -  0) --> 'F'
* If the given score is greater than 100 or less than 0, it should return 'INVALID SCORE'.

```
output = convert_score_to_grade(91)
print(output) # --> 'A'
```

### !end-question

### !placeholder

```python




```

### !end-placeholder

### !tests

```python
import main
import unittest

class TestScript(unittest.TestCase):

    def test_0(self):
        # it should return a string
        self.assertIsInstance(main.convert_score_to_grade(95), str,
        msg = 'should return a string')


    def test_1(self):
        # it should return 'A' for scores between 90 and 100
        self.assertEqual(main.convert_score_to_grade(95), "A",
        msg = "should return 'A' for scores between 90 and 100")


    def test_2(self):
        # it should return 'B' for scores between 80 and 89
        self.assertEqual(main.convert_score_to_grade(80), "B",
        msg = "should return 'B' for scores between 80 and 89")


    def test_3(self):
        # it should return 'C' for scores between 70 and 79
        self.assertEqual(main.convert_score_to_grade(79), "C",
        msg = "should return 'C' for scores between 70 and 79")


    def test_4(self):
        # it should return 'D' for scores between 60 and 69
        self.assertEqual(main.convert_score_to_grade(60), "D",
        msg = "should return 'D' for scores between 60 and 69")


    def test_5(self):
        # it should return 'F' for 59
        self.assertEqual(main.convert_score_to_grade(59), "F",
        msg = "should return 'F' for 59")


    def test_6(self):
        # it should return 'F' for scores between 0 and 59
        self.assertEqual(main.convert_score_to_grade(50), "F",
        msg = "should return 'F' for scores between 0 and 59")


    def test_7(self):
        # it should return 'F' for 0
        self.assertEqual(main.convert_score_to_grade(0), "F",
        msg = "should return 'F' for 0")


    def test_8(self):
        # it should return 'INVALID SCORE' for scores less than 0
        self.assertEqual(main.convert_score_to_grade(-1), "INVALID SCORE",
        msg = "should return 'INVALID SCORE' for scores less than 0")


    def test_9(self):
        # it should return 'INVALID SCORE' for scores greater than 100
        self.assertEqual(main.convert_score_to_grade(101), "INVALID SCORE",
        msg = "should return 'INVALID SCORE' for scores greater than 100")

```

### !end-tests

### !explanation
```python
def convert_score_to_grade(score):
    if score > 100 or score < 0: return "INVALID SCORE"
    if score >= 90: return "A"
    if score >= 80: return "B"
    if score >= 70: return "C"
    if score >= 60: return "D"
    return "F"

```
### !end-explanation

### !end-challenge

### !challenge

* type: code-snippet
* language: python3.6
* id: d53cbbaf-dfb4-44ab-a0a9-9512018da2be
* title: convert_score_to_gradeWithPlus

### !question

Write a function called "convert_score_to_grade_plus_minus".

Given a score, "convert_score_to_grade_plus_minus" returns a string representing the letter grade corresponding to the given score.

Notes:
* (100 - 90) --> 'A'
* (89  - 80) --> 'B'
* (79  - 70) --> 'C'
* (69  - 60) --> 'D'
* (59  -  0) --> 'F'
* If the given score is greater than 100 or less than 0, it should return 'INVALID SCORE'.
* If the score is between the 0 and 2 (inclusive) of a given range, return the letter with a '-'
* If the score is be the 8 and 9 (inclusive) of a given range, return the letter with a '+'
* There are is no F+ and there is no F-.

```
output = convert_score_to_grade_plus_minus(91)
print(output) # --> 'A-'
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

class TestScript(unittest.TestCase):

    def test_0(self):
        # it should return a string
        self.assertIsInstance(main.convert_score_to_grade_plus_minus(95), str,
        msg = 'should return a string')


    def test_1(self):
        # it should return 'A+' for scores between 98 and 100
        self.assertEqual(main.convert_score_to_grade_plus_minus(100), "A+",
        msg = 'should return "A+" for scores between 98 and 100')


    def test_2(self):
        # it should return 'A-' for scores between 90 and 92
        self.assertEqual(main.convert_score_to_grade_plus_minus(90), "A-",
        msg = 'should return "A-" for scores between 90 and 92')


    def test_3(self):
        # it should return 'A' for scores between 93 and 97
        self.assertEqual(main.convert_score_to_grade_plus_minus(95), "A",
        msg = 'should return "A" for scores between 93 and 97')


    def test_4(self):
        # it should return 'B+' for scores between 88 and 89
        self.assertEqual(main.convert_score_to_grade_plus_minus(89), "B+",
        msg = 'should return "B+" for scores between 88 and 89')


    def test_5(self):
        # it should return 'B-' for scores between 80 and 82
        self.assertEqual(main.convert_score_to_grade_plus_minus(80), "B-",
        msg = 'should return "B-" for scores between 80 and 82')


    def test_6(self):
        # it should return 'B' for scores between 83 and 87
        self.assertEqual(main.convert_score_to_grade_plus_minus(84), "B",
        msg = 'should return "B" for scores between 83 and 87')


    def test_7(self):
        # it should return 'C+' for scores between 78 and 79
        self.assertEqual(main.convert_score_to_grade_plus_minus(79), "C+",
        msg = 'should return "C+" for scores between 78 and 79')


    def test_8(self):
        # it should return 'C-' for scores between 70 and 72
        self.assertEqual(main.convert_score_to_grade_plus_minus(70), "C-",
        msg = 'should return "C-" for scores between 70 and 72')


    def test_9(self):
        # it should return 'C' for scores between 73 and 77
        self.assertEqual(main.convert_score_to_grade_plus_minus(76), "C",
        msg = 'should return "C" for scores between 73 and 77')


    def test_10(self):
        # it should return 'D+' for scores between 68 and 69
        self.assertEqual(main.convert_score_to_grade_plus_minus(69), "D+",
        msg = 'should return "D+" for scores between 68 and 69')


    def test_11(self):
        # it should return 'D' for scores between 63 and 67
        self.assertEqual(main.convert_score_to_grade_plus_minus(64), "D",
        msg = 'should return "D" for scores between 63 and 67')


    def test_12(self):
        # it should return 'D-' for scores between 60 and 62
        self.assertEqual(main.convert_score_to_grade_plus_minus(60), "D-",
        msg = 'should return "D-" for scores between 60 and 62')


    def test_13(self):
        # it should return 'F' for scores between 0 and 59
        self.assertEqual(main.convert_score_to_grade_plus_minus(0), "F",
        msg = 'should return "F" for scores between 0 and 59')


    def test_14(self):
        # it should return 'INVALID SCORE' for scores less than 0
        self.assertEqual(main.convert_score_to_grade_plus_minus(-1), "INVALID SCORE",
        msg = 'should return "INVALID SCORE" for scores less than 0')


    def test_15(self):
        # it should return 'INVALID SCORE' for scores greater than 100
        self.assertEqual(main.convert_score_to_grade_plus_minus(101), "INVALID SCORE",
        msg = 'should return "INVALID SCORE" for scores greater than 100')

```

### !end-tests

### !explanation
```python
def convert_score_to_grade_plus_minus(score):
    if score > 100 or score < 0: return "INVALID SCORE"
    if score >= 98: return "A+"
    if score >= 93: return "A"
    if score >= 90: return "A-"
    if score >= 88: return "B+"
    if score >= 83: return "B"
    if score >= 80: return "B-"
    if score >= 78: return "C+"
    if score >= 73: return "C"
    if score >= 70: return "C-"
    if score >= 68: return "D+"
    if score >= 63: return "D"
    if score >= 60: return "D-"
    return "F"



```
### !end-explanation

### !end-challenge
