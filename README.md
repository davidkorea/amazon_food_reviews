# amazon_food_reviews

# issue 1 -  str.maketrans('','',string.punctuation)
```python
import string
# This uses the 3-argument version of str.maketrans with arguments (x, y, z) where 'x' and 'y'
# must be equal-length strings and characters in 'x' are replaced by characters in 'y'. 
# 'z' is a string(string.punctuation here) where each character in the string is mapped to None
translator = str.maketrans('', '', string.punctuation)
s = 'string with "punctuation" inside of it! Does this work? I hope so.'
print(s.translate(translator))
=> string with punctuation inside of it Does this work I hope so
```

**Explaination**

```python
str.maketrans('abc', 'xyz', 'hij')

# This is the same as the two argument version, except that the characters from the third string are removed, 
# as if they were mapped to None. 
# So your table is saying "Don't replace anything, but remove the characters that show up in this string".
```
**Don't replace anything, but remove the characters that show up in this string**

reference: [How to explain the str.maketrans function in Python 3.6?](https://stackoverflow.com/questions/41535571/how-to-explain-the-str-maketrans-function-in-python-3-6#41536036)
