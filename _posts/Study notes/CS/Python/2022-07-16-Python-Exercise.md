---
title: Python Basics
last_modified_at: 2022-07-16
categories:
- CS
tags: Python
---

## Python foundamentals

### Rock Paper Scissors

- Examples(Input1, Input2 --> Output):
- "scissors", "paper" --> "Player 1 won!"
- "scissors", "rock" --> "Player 2 won!"
- "paper", "paper" --> "Draw!"

>
> Answer:
>

>
> - Use dictionary to store conditions
> - One comparison is a pair
> - Tuple in list can do too
>

~~~
def rps(p1, p2):
    beats = {'rock': 'scissors', 'scissors': 'paper', 'paper': 'rock'}
    if beats[p1] == p2:
        return "Player 1 won!"
    if beats[p2] == p1:
        return "Player 2 won!"
    return "Draw!"
~~~

>
> - Also dictionary, but store int, use int for comparison
> - Use index to return results
>

~~~
def rps(p1, p2):
    hand = {'rock':0, 'paper':1, 'scissors':2}
    results = ['Draw!', 'Player 1 won!', 'Player 2 won!']
    return results[hand[p1] - hand[p2]]
~~~

>
> - Best
>

~~~
def rps(p1, p2):
    return p1 == p2 and 'Draw!' or f"Player {(p2[0] + p1[0] in 'rspr') + 1} won!"
~~~


### Calculate BMI

>
> Use Boolean value for conditions, True -> 1, Flase -> 0
>

~~~
def bmi(weight, height):
    b = weight / height ** 2
    return ['Underweight', 'Normal', 'Overweight', 'Obese'][(b > 30) + (b > 25) + (b > 18.5)]
~~~

### Return binary value of calculation

>
> Use `bin()` function
>

~~~
def add_binary(a,b):
    return bin(a+b)[2:]
~~~

>
> Use `format()` method of string
>

~~~
def add_binary(a,b):
    return '{0:b}'.format(a + b)
~~~

~~~
def add_binary(a,b):
    return f"{a + b :b}"
~~~

### Count and sum

>
> Loop sum for count function
>

~~~
def count_positives_sum_negatives(arr):
    pos = sum(1 for x in arr if x > 0)
    neg = sum(x for x in arr if x < 0)
    return [pos, neg] if len(arr) else []
~~~

### Transpose rows and cols

- Example: `matrix = [[1, 2, 3, 4],[5, 6, 7, 8],[9, 10, 11, 12]]`

>
> Nested list
>

~~~
 [[row[i] for row in matrix] for i in range(4)]
~~~

>
> `zip()` function
>

~~~
list(zip(*matrix))
~~~

### [Count the smiley faces!](https://www.codewars.com/kata/583203e6eb35d7980400002a/solutions/python)

>
> re.findall()
>

~~~
from re import findall
def count_smileys(arr):
    return len(list(findall(r"[:;][-~]?[)D]", " ".join(arr))))
~~~

>
> Enumerate
>

~~~
def count_smileys(arr):
    eyes = [":", ";"]
    noses = ["", "-", "~"]
    mouths = [")", "D"]
    count = 0
    for eye in eyes:
        for nose in noses:
            for mouth in mouths:
                face = eye + nose + mouth
                count += arr.count(face)
    return count
~~~

### [Direction Reduction](https://www.codewars.com/kata/550f22f4d758534c1100025a/solutions/python)

>
> Stack
>

~~~
opposite = {'NORTH': 'SOUTH', 'EAST': 'WEST', 'SOUTH': 'NORTH', 'WEST': 'EAST'}

def dirReduc(plan):
    new_plan = []
    for d in plan:
        if new_plan and new_plan[-1] == opposite[d]:
            new_plan.pop()
        else:
            new_plan.append(d)
    return new_plan
~~~

>
> Recursion
>

~~~
def dirReduc(arr):
    opposites = [{'NORTH', 'SOUTH'}, {'EAST', 'WEST'}]
    
    for i in range(len(arr)-1):
        if set(arr[i:i+2]) in opposites:
            del arr[i:i+2]
            return dirReduc(arr)
    
    return arr  
~~~