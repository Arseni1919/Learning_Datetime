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

## Creating Python `datetime` Instances

The three classes that represent dates and times in datetime have similar initializers. 
They can be instantiated by passing keyword arguments for each of the attributes, such as year, date, or hour.

```python
>>> from datetime import date, time, datetime
>>> date(year=2020, month=1, day=31)
datetime.date(2020, 1, 31)
>>> time(hour=13, minute=14, second=31)
datetime.time(13, 14, 31)
>>> datetime(year=2020, month=1, day=31, hour=13, minute=14, second=31)
datetime.datetime(2020, 1, 31, 13, 14, 31)
```

Fortunately, `datetime` provides several other convenient ways to create datetime instances. 
These methods don’t require you to use integers to specify each attribute, 
but instead allow you to use some other information:

- `date.today()` creates a datetime.date instance with the current local date.

- `datetime.now()` creates a datetime.datetime instance with the current local date and time.

- `datetime.combine()` combines instances of datetime.date and datetime.time into a single datetime.datetime instance.

These three ways of creating datetime instances are helpful 
when you don’t know in advance what information you need to pass into the basic initializers.

```python
>>> from datetime import date, time, datetime
>>> today = date.today()
>>> today
datetime.date(2020, 1, 24)
>>> now = datetime.now()
>>> now
datetime.datetime(2020, 1, 24, 14, 4, 57, 10015)
>>> current_time = time(now.hour, now.minute, now.second)
>>> datetime.combine(today, current_time)
datetime.datetime(2020, 1, 24, 14, 4, 57)
```

## Using Strings to Create Python `datetime` Instances

Another way to create date instances is to use `.fromisoformat()`. 
To use this method, you provide a string with the date in the ISO 8601 format that you learned about earlier. 
For instance, you might provide a string with the year, month, and date specified:

```
2020-01-31
```

This string represents the date January 31, 2020, according to the ISO 8601 format. 
You can create a date instance with the following example:

```python
>>> from datetime import date
>>> date.fromisoformat("2020-01-31")
datetime.date(2020, 1, 31)
```

### `.strptime()`

But what if you have a string that represents a date and time but isn’t in the ISO 8601 format?

Fortunately, Python datetime provides a method called `.strptime()` to handle this situation. 
This method uses a special mini-language to tell Python 
which parts of the string are associated with the `datetime` attributes.

To construct a `datetime` from a string using `.strptime()`, 
you have to tell Python what each of the parts of the string represents using formatting codes from the mini-language. 
You can try this example to see how `.strptime()` works:

```
>>> date_string = "01-31-2020 14:45:37"
>>> format_string = "%m-%d-%Y %H:%M:%S"
```
On line 1, you create `date_string`, which represents the date and time January 31, 2020, at 2:45:37 PM. 
On line 2, you create `format_string`, which uses the mini-language 
to specify how the parts of `date_string` will be turned into datetime attributes.

In `format_string`, you include several formatting codes and all of the dashes (-), colons (:), 
and spaces exactly as they appear in `date_string`. 
To process the date and time in date_string, you include the following formatting codes:

![](pics/formats.png)

A complete listing of all of the options in the mini-language is outside the scope of this tutorial, 
but you can find several good references on the web, 
including in Python’s documentation and on a website called [strftime.org](strftime.org).

```python
>>> from datetime import datetime
>>> datetime.strptime(date_string, format_string)
datetime.datetime(2020, 1, 31, 14, 45, 37)
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