Computational physics
-----

###Two minor **mistakes** the teacher made:

 - The  name of the famous package for first-principle calculations is *Vienna Ab-initio Simulation Package* (VASP), but the teacher took it as **WASP**. I noticed it and secretly  corrected it in the short break between lessons by wiping out the front "V" of the strike of "W" he put on the blackboard.  Of course,  he didn't find it.
 
 - The teacher mistook the name of *Phys.Rev.Lett* as "Physics Review Letter", but actually it should be **Physical Review Letters**. If it was not his slip of the tongue, I don't think the teacher have read [*LIGO*'s paper on Gravitational Waves](http://journals.aps.org/prl/abstract/10.1103/PhysRevLett.116.061102).
 - The standard pronunciation of LaTeX is ['leitek] but not ['leiteks].

### My **complaint** about the assessment rule

Though keep training may improve one's skill in programming, I still want to give this uncanny assessment rule, which high lights the **length** in stead of the **quality** of your homework, an inequality: $ln( x-1)>0.$ I think most of the rule-taker share the same opinion of mine.

### Code demo

I wrote a program to count how many digits and what they are in number $2^{100000}$
```python
a = 2 ** 100000
digit = {0: 0, 1: 0, 2: 0, 3: 0, 4: 0, 5: 0, 6: 0, 7: 0, 8: 0, 9: 0}


def count_digit(num):
    while num > 0:
        d = num % 10
        num //= 10
        digit[d] += 1
    return digit

count_digit(a)
summation = 0
for i in range(0, 9):
    summation += digit[i]

print digit
print summation
```
>```python
>{0: 2991, 1: 2969, 2: 3068, 3: 3075, 4: 3040, 5: 3015, 6: 2952, 7: 3052, 8: 2932, 9: 3009}
>27094
>```
What a **large** number! There are totally 27094 digits with 2991 0's, 2969 1's and so on. Hopefully, my Mac can cope with it in several seconds, ahahhhhh~~

I wrote the following program to explore the nuance between pass-by-**refernce** and pass-by-**value**
```python
def apd(alist):
    alist.append('suffix')
    return


def plus(alist):
    alist = alist + ['suffix']
    return


list = [1,2,3]
plus(list)
print 'result of "+":', list
apd(list)
print 'result of "list.append()":', list

```
>```python
> result of "+": [1, 2, 3]
> result of "list.append()": [1, 2, 3, 'suffix']
>```
