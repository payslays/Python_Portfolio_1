# Python_Portfolio_1
## Analyzing Patient Data
```python
import numpy
```


```python
numpy.loadtxt(fname = 'inflammation-01.csv', delimiter = ',')
              
```




    array([[0., 0., 1., ..., 3., 0., 0.],
           [0., 1., 2., ..., 1., 0., 1.],
           [0., 1., 1., ..., 2., 1., 1.],
           ...,
           [0., 1., 1., ..., 1., 1., 1.],
           [0., 0., 0., ..., 0., 2., 0.],
           [0., 0., 1., ..., 1., 1., 0.]])




```python
data = numpy.loadtxt(fname = 'inflammation-01.csv', delimiter = ',')
              
```


```python
print (data)
```

    [[0. 0. 1. ... 3. 0. 0.]
     [0. 1. 2. ... 1. 0. 1.]
     [0. 1. 1. ... 2. 1. 1.]
     ...
     [0. 1. 1. ... 1. 1. 1.]
     [0. 0. 0. ... 0. 2. 0.]
     [0. 0. 1. ... 1. 1. 0.]]



```python
print(type(data))
```

    <class 'numpy.ndarray'>



```python
print(data.shape)
```

    (60, 40)



```python
print('first value in data:', data[0,0])
```

    first value in data: 0.0



```python
print('middle value in data:', data[29,19])
```

    middle value in data: 16.0



```python
print(data[0:4, 0:10])
```

    [[0. 0. 1. 3. 1. 2. 4. 7. 8. 3.]
     [0. 1. 2. 1. 2. 1. 3. 2. 2. 6.]
     [0. 1. 1. 3. 3. 2. 6. 2. 5. 9.]
     [0. 0. 2. 0. 4. 2. 2. 1. 6. 7.]]



```python
print(data[5:10, 0:10])
```

    [[0. 0. 1. 2. 2. 4. 2. 1. 6. 4.]
     [0. 0. 2. 2. 4. 2. 2. 5. 5. 8.]
     [0. 0. 1. 2. 3. 1. 2. 3. 5. 3.]
     [0. 0. 0. 3. 1. 5. 6. 5. 5. 8.]
     [0. 1. 1. 2. 1. 3. 5. 3. 5. 8.]]



```python
small = data[:3, 36:]
```


```python
print('small is:')
```

    small is:



```python
print(numpy.mean(data))
```

    6.14875



```python
maxval, minval stdval = numpy.amax(data), numpy.amin(data), numpy.std(data)

```


```python
maxval= numpy.amax(data)
minval= numpy.amin(data)
stdval= numpy.std(data)
```


```python
print('maximum inflammation:', maxval)
print('minimum inflammation:', minval)
print('standard deviation:', stdval)
```

    maximum inflammation: 20.0
    minimum inflammation: 0.0
    standard deviation: 4.613833197118566



```python
print('maximum inflammation for paitent 2:', numpy.amax(data[2, :]))
```

    maximum inflammation for paitent 2: 19.0



```python
print(numpy.mean(data, axis = 0))
```

    [ 0.          0.45        1.11666667  1.75        2.43333333  3.15
      3.8         3.88333333  5.23333333  5.51666667  5.95        5.9
      8.35        7.73333333  8.36666667  9.5         9.58333333 10.63333333
     11.56666667 12.35       13.25       11.96666667 11.03333333 10.16666667
     10.          8.66666667  9.15        7.25        7.33333333  6.58333333
      6.06666667  5.95        5.11666667  3.6         3.3         3.56666667
      2.48333333  1.5         1.13333333  0.56666667]



```python
print(numpy.mean(data, axis =0).shape)
```

    (40,)



```python
print(numpy.mean(data, axis = 1))
```

    [5.45  5.425 6.1   5.9   5.55  6.225 5.975 6.65  6.625 6.525 6.775 5.8
     6.225 5.75  5.225 6.3   6.55  5.7   5.85  6.55  5.775 5.825 6.175 6.1
     5.8   6.425 6.05  6.025 6.175 6.55  6.175 6.35  6.725 6.125 7.075 5.725
     5.925 6.15  6.075 5.75  5.975 5.725 6.3   5.9   6.75  5.925 7.225 6.15
     5.95  6.275 5.7   6.1   6.825 5.975 6.725 5.7   6.25  6.4   7.05  5.9  ]


## Loops
odds = [1,3,5,7]

```


```python
print(odds[0])
print(odds[1])
print(odds[2])
print(odds[3])
```

    1
    3
    5
    7



```python
odds = [1, 3, 5, 7, 9, 11, 13, 15, 17, 19]

for num in odds:
    print(num)
```

    1
    3
    5
    7
    9
    11
    13
    15
    17
    19



```python
length = 0
names = ['Curie', 'Darwin', 'Turing']
for value in names:
    length = length + 1
print('There are', length, 'name in the list.')
```

    There are 3 name in the list.



```python
name = "Rosalind"
for name in ['Curie', 'Darwin', 'Turing']:
    print(name)
print('after the loop, name is', name)
```

    Curie
    Darwin
    Turing
    after the loop, name is Turing



```python
print(len([0,1,2,3]))
```

    4



```python
name = ['Curie', 'Darwin', 'Turing']

print(len(name))
```

    3
## Data Visulization
```python
import numpy
data = numpy.loadtxt(fname = 'inflammation-01.csv', delimiter = ',')
```


```python
import matplotlib.pyplot
image = matplotlib.pyplot.imshow(data)
matplotlib.pyplot.show()
```


    <Figure size 640x480 with 1 Axes>



```python
ave_inflammation =numpy.mean(data, axis =0)
ave_plot = matplotlib.pyplot.plot(ave_inflammation)
matplotlib.pyplot.show()
```


![png](output_2_0.png)



```python
max_plot = matplotlib.pyplot.plot(numpy.amax(data, axis =0))
matplotlib.pyplot.show()
```


![png](output_3_0.png)



```python
min_plot = matplotlib.pyplot.plot(numpy.amin(data, axis = 0))
matplotlib.pyplot.show()
```


![png](output_4_0.png)



```python
fig = matplotlib.pyplot.figure(figsize =(10.0, 3.0))

axes1 = fig.add_subplot(1, 3, 1)
axes2 = fig.add_subplot(1, 3, 2)
axes3 =fig.add_subplot(1, 3, 3)

axes1.set_ylabel('average')
axes1.plot(numpy.mean(data, axis = 0))

axes2.set_ylabel('max')
axes2.plot(numpy.amax(data, axis = 0))

axes3.set_ylabel('min')
axes3.plot(numpy.amin(data, axis = 0))

fig.tight_layout()

matplotlib.pyplot.savefig('inflammation.png')
matplotlib.pyplot.show()
```


![png](output_5_0.png)

## Making Choices
```python
num = 37
if num > 100:
    print('greater')
else:
    print('not greater')
print('done')
```

    not greater
    done



```python
num = 53
print('before conditional...')
if num > 100:
    print(num, 'is greater than 100')
print('...after conditional')
```

    before conditional...
    ...after conditional



```python
num = 14

if num > 0:
    print(num, 'is positive')
elif num == 0:
    print(num, 'is zero')
else:
    print(num, 'is negative')
```

    14 is positive



```python
if (1 > 0) and (-1 >= 0):
    print('both parts are true')
else:
    print('at least one part if false')
```

    at least one part if false



```python
if (1 > 0) or (-1 >= 0):
    print('both parts are true')
else: 
    print('both of these are false')
```

    both parts are true



```python
import numpy
```


```python
data = numpy.loadtxt(fname='inflammation-01.csv', delimiter=',')

```


    ---------------------------------------------------------------------------

    OSError                                   Traceback (most recent call last)

    <ipython-input-13-4e66da606a9a> in <module>
    ----> 1 data = numpy.loadtxt(fname='inflammation-01.csv', delimiter=',')
    

    ~/anaconda3/lib/python3.7/site-packages/numpy/lib/npyio.py in loadtxt(fname, dtype, comments, delimiter, converters, skiprows, usecols, unpack, ndmin, encoding, max_rows)
        966             fname = os_fspath(fname)
        967         if _is_string_like(fname):
    --> 968             fh = np.lib._datasource.open(fname, 'rt', encoding=encoding)
        969             fencoding = getattr(fh, 'encoding', 'latin1')
        970             fh = iter(fh)


    ~/anaconda3/lib/python3.7/site-packages/numpy/lib/_datasource.py in open(path, mode, destpath, encoding, newline)
        267 
        268     ds = DataSource(destpath)
    --> 269     return ds.open(path, mode, encoding=encoding, newline=newline)
        270 
        271 


    ~/anaconda3/lib/python3.7/site-packages/numpy/lib/_datasource.py in open(self, path, mode, encoding, newline)
        621                                       encoding=encoding, newline=newline)
        622         else:
    --> 623             raise IOError("%s not found." % path)
        624 
        625 


    OSError: inflammation-01.csv not found.



## Functions
```python
fahrenheit_val = 99
celsius_val = ((fahrenheit_val - 32) *(5/9))


print(celsius_val)
```

    37.22222222222222



```python
fahrenheit_val2 = 43
celsius_val2 = ((fahrenheit_val2 -32) * (5/9))

print(celsius_val2)
```

    6.111111111111112



```python
def explicit_fahr_to_celsius(temp):
    converted = ((temp - 32) *(5/9))

```


```python
def fahr_to_celsius(temp):
    return ((temp - 32) *(5/9))
```


```python
fahr_to_celsius(32)
```




    0.0




```python
explicit_fahr_to_celsius(32)
```


```python
print('Freezing point of water:', fahr_to_celsius(32), 'C')
print(' Boiling point of water:', fahr_to_celsius(212), 'C')
```

    Freezing point of water: 0.0 C
     Boiling point of water: 100.0 C



```python
def celsius_to_kelvin(temp_c):
    return temp_c + 273.15

print('freezing point of water in Kelvin:', celsius_to_kelvin(0.))
```

    freezing point of water in Kelvin: 273.15



```python
def fahr_to_kelvin(temp_f):
    temp_c = fahr_to_celsius(temp_f)
    temp_k = celsius_to_kelvin(temp_c)
    return temp_k

print('freezing point of water in Kelvin', fahr_to_kelvin(212.0))
```

    freezing point of water in Kelvin 373.15



```python
def fahr_to_kelvinZ(temp_f):
    temp_c = fahr_to_celsius(temp_f)
    temp_k = celsius_to_kelvin(temp_c)
    return temp_k

print('boiling point of water in Kelvin 373.15')
```

    boiling point of water in Kelvin 373.15



```python
temp_kelvin = fahr_to_kelvin(212.0)
print('Temperature in Kelvin was:', temp_kelving)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-15-d88438cc941c> in <module>
          1 temp_kelvin = fahr_to_kelvin(212.0)
    ----> 2 print('Temperature in Kelvin was:', temp_kelving)
    

    NameError: name 'temp_kelving' is not defined



```python
temp_kelvin
```




    373.15




```python
def print_temperatures():
    print('Temperature in Fahrenheit was:', temp_fahr)
    print('Temperature in Kelvin was:', temp_kelvin)

temp_fahr = 212.0
temp_kelvin = fahr_to_kelvin(temp_fahr)

print_temperatures()
```

    Temperature in Fahrenheit was: 212.0
    Temperature in Kelvin was: 373.15
    
## Defensive Programming
```python
numbers = [1.5, 2.3, 0.7, -0.001, 4.4]
total = 0.0
for num in numbers:
    assert num > 0.0, 'Data should only contain positive values'
    total += num
print('total is:', total)
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-1-13c7d5640ddd> in <module>
          2 total = 0.0
          3 for num in numbers:
    ----> 4     assert num > 0.0, 'Data should only contain positive values'
          5     total += num
          6 print('total is:', total)


    AssertionError: Data should only contain positive values



```python
def normalize_rectangle(rect):
    assert len(rect) == 4
    assert x0 < x1
    assert y0 < y1
    if dx > dy:
        scaled = dx / dy
        upper_x, upper_y = 1.0, scaled
    else:
        scaled = dx / dy
        upper_x, upper_y
        
    assert 0 < upper_x
    assert 0 < upper_
    
 

        
        
