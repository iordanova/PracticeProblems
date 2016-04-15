
## Write a Python function that accepts a string and calculate the number of upper case letters and lower case letters.

Sample String : 'Hello Mr. Rogers, how are you this fine Tuesday?'
Expected Output : 
No. of Upper case characters : 4
No. of Lower case Characters : 33




```python
import string

def up_low(s):
    out_dict = {'Upper':0, 'Lower':0}
    s_split = s.split()
    for word in s_split:
        for letter in word:
            if letter.isupper() == True:
                out_dict['Upper']+=1
            elif letter.isalpha() == True:
                out_dict['Lower']+=1
    return out_dict

s = 'Hello Mr. Rogers, how are you this fine Tuesday?'
result= up_low(s)
print 'No. of Upper cases: {0}'.format(result['Upper'])
print 'No. of Lower cases: {0}'.format(result['Lower'])    
```

    No. of Upper cases: 4
    No. of Lower cases: 33



```python
type(up_low(s))
```




    dict




```python
#Write a Python function that takes a list and returns a new list with unique elements of the first list
```


```python
def unique_list(l):
    return set(l)

l1 = [1,1,1,1,2,2,3,3,3,3,4,5]
unique_list(l1)
```




    {1, 2, 3, 4, 5}




```python
#Write a Python function to multiply all the numbers in a list.
```


```python
def multiply(numbers):
    res = numbers[0]
    for num in numbers[1:]:
        res*=num
    
    return res

l1 =[1, 2, 3, -4]
multiply(l1)
```




    -24




```python
#Write a Python function that checks whether a passed string is palindrome or not.

#Note: A palindrome is word, phrase, or sequence that reads the same backward as forward, e.g., madam or nurses run.
```


```python
def palindrome(s):
    s_rev = s[::-1]
    for letter in range(len(s)/2 +1):
        if s[letter]==s_rev[letter]:
            continue
        else:
            return False
    return True

palindrome('pottop')
```




    True
   
    Or just use      return s==s[::-1] 


```python
#Write a Python function to check whether a string is pangram or not.

#Note : Pangrams are words or sentences containing every letter of the alphabet at least once.
#For example : "The quick brown fox jumps over the lazy dog"
```


```python
import string

def ispangram(str1, alphabet=string.ascii_lowercase): 
    str1 = str1.lower()
    dic1={}
    for letter in str1:
        if letter.isalpha()==True:
            dic1[letter]=1
    
    str1_letters = sorted(dic1.keys())
    for ind in range(len(str1_letters)):
        if alphabet[ind] == str1_letters[ind]:
            continue
        else:
            return False
    return True

ex ="The quick brown fox jumps over the lazy dog"
ex1 = "I am not happy for Burnie"
ispangram(ex1)
```




    False


