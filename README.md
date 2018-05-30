# amazon_food_reviews

# issue 1 -  str.maketrans('','',string.punctuation)
```python
string.punctuation
=> '!"#$%&\'()*+,-./:;<=>?@[\\]^_`{|}~'
```

```python
import string
# This uses the 3-argument version of str.maketrans with arguments (x, y, z) where 'x' and 'y'
# must be equal-length strings and characters in 'x' are replaced by characters in 'y'. 
# 'z' is a string(string.punctuation here) where each character in the string is mapped to None
translator = str.maketrans('', '', string.punctuation)
s = 'string with "punctuation" inside of it! Does this work? I hope so.'
print(s.translate(translator))
=> 'string with punctuation inside of it Does this work I hope so'
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

# issue 2 -  ImportError: No module named 'sklearn.model_selection'（windows）

anaconda中通过命令行查看sklearn的版本为 0.17.1，而sklearn.model_selection 是 sklearn 版本 0.18.1 以上.

**Answer**
```
$ conda update scikit-learn
Fetching package metadata .............
Solving package specifications: .

Package plan for installation in environment E:\Program Files\Anaconda3:

The following NEW packages will be INSTALLED:

    icc_rt:       2017.0.4-h97af966_0
    intel-openmp: 2018.0.0-8

The following packages will be UPDATED:

    conda:        4.3.30-py35hec795fb_0 --> 4.5.4-py35_0
    conda-env:    2.6.0-0               --> 2.6.0-h36134e3_1
    mkl:          11.3.3-1              --> 2018.0.2-1
    numexpr:      2.6.1-np111py35_0     --> 2.6.5-py35hcd2f87e_0
    numpy:        1.11.1-py35_1         --> 1.11.3-py35h4a99626_4
    pycosat:      0.6.1-py35_1          --> 0.6.3-py35h456c199_0
    scikit-learn: 0.17.1-np111py35_1    --> 0.19.1-py35h2037775_0
    scipy:        0.18.1-np111py35_0    --> 1.1.0-py35h672f292_0

Proceed ([y]/n)? y

conda-env-2.6. 100% |###############################| Time: 0:00:00 898.26 kB/s
icc_rt-2017.0. 100% |###############################| Time: 0:00:02   3.42 MB/s
intel-openmp-2 100% |###############################| Time: 0:00:00   3.81 MB/s
mkl-2018.0.2-1 100% |###############################| Time: 0:00:51   3.62 MB/s
numpy-1.11.3-p 100% |###############################| Time: 0:00:00   4.29 MB/s
pycosat-0.6.3- 100% |###############################| Time: 0:00:00   1.58 MB/s
numexpr-2.6.5- 100% |###############################| Time: 0:00:00   4.36 MB/s
scipy-1.1.0-py 100% |###############################| Time: 0:00:03   4.04 MB/s
scikit-learn-0  90% |############################   | Time: 0:00:01   2.72 MB/s

```

reference: [报错 ImportError: No module named model_selection 的解决办法](https://blog.csdn.net/jinlong_xu/article/details/72862047)
