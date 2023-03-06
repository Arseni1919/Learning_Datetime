# Learning `datetime`


## Unix Time

Nearly all programming languages, including Python, incorporate the concept of Unix time. 
Python’s standard library includes a module called time that can print the number of seconds since the Unix epoch:

```python
import time
time.time()
```

## ISO 8601

To help avoid communication mistakes, the International Organization for Standardization (ISO) developed ISO 8601. 
This standard specifies that all dates should be written in order of most-to-least-significant data. 
This means the format is year, month, day, hour, minute, and second:

```
YYYY-MM-DD HH:MM:SS
```

## `time` Module

`time` is less powerful and more complicated to use than `datetime`. 
Many functions in `time` return a special `struct_time` instance. 
This object has a named tuple interface for accessing stored data, making it similar to an instance of `datetime`. 
However, 
it doesn’t support all of the features of datetime, especially the ability to perform arithmetic with time values.

## `datetime` Module 

`datetime` provides three classes that make up the high-level interface that most people will use:

- `datetime.date` is an idealized date that assumes the Gregorian calendar extends infinitely into the future and past. 
This object stores the year, month, and day as attributes.

- `datetime.time` is an idealized time that assumes there are 86,400 seconds per day with no leap seconds. 
This object stores the hour, minute, second, microsecond, and tzinfo (time zone information).

- `datetime.datetime` is a combination of a date and a time. 
It has all the attributes of both classes.

## 

```python

```

## 

```python

```

## 

```python

```

## 

```python

```

## 

```python

```

## 

```python

```

## 

```python

```

## 

```python

```

## 

```python

```

## 

```python

```

## Credits

- [real python | Using Python datetime to Work With Dates and Times](https://realpython.com/python-datetime/)
- []()