---
title: Assigning values to variables as part of a larger expression in Python 3.8
date: '2020-06-17'
tags:
  - programming
  - feature
  - operator
category:
  slug: python
  title: python
seo:
  title: Assigning values to variables as part of a larger expression in Python 3.8
  description: Python 3.8 introduces assignment expressions AKA walrus operator
  openGraph:
    images:
      - url: 'https://hallaji.com/diary/walrus-operator/walrus-operator.jpg'
        width: 1389 
        height: 758
        alt: Walrus operator in Python
---

[python-3.8]: https://docs.python.org/3/whatsnew/3.8.html
[assignment-expressions]: https://docs.python.org/3/whatsnew/3.8.html#assignment-expressions
[walrus]: /diary/walrus-operator/walrus-operator.jpg

Python [3.8][python-3.8] introduces [assignment expressions][assignment-expressions] affectionately known as “the
walrus operator”. That's because the operator looks like a walrus!

> The walrus is a large flippered marine mammal with a discontinuous distribution about the North Pole in the Arctic
Ocean and subarctic seas of the Northern Hemisphere. — Wikipedia

![Walrus operator in Python][walrus]

`:=`

---

A use case for this operator is when you want to assign a value to a variable in just one line of code if an initial
boolean expression is `True`.

```python
hasCoupon and (discount := 20)
```

In this example, a 20% discount will be applied if the user has a coupon. The assignment **must** be inside
parentheses here otherwise you will get a syntax error.

```python
discount = 0

hasCoupon = False
hasCoupon and (discount := 20)
print(discount) # output is 0

hasCoupon = True
hasCoupon and (discount := 20)
print(discount) # output is 20
```

Another motivating use case is where the operator helps to avoid calling a function twice e.g. `len`.

```python
if (n := len(a)) > 10:
    print(f"List is too long ({n} elements, expected <= 10)")
```
