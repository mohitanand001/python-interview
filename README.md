1. what are decorators?
2. what design patterns are already available in python
     - builder pattern: it helps us in passing different number of arguments to a function (args for positional args, kwargs for keyword args)
     - decorator pattern: we already have the @decorator_name in python, which helps us in 
3. what are fixtures in pytest (they are like setup/arrange and teardown/cleanup in unittest)
4. pytest best practices: https://pytest-with-eric.com/pytest-best-practices/pytest-benchmark/
5. performance issues in testing: when the number of tests increase beyond a certain limit we saw that testing starts taking a lot of time
   when we investigated, we found that there were some tests which took 1/2 seconds and were increasing the overall runtime by 20s or so.
   so we mocked the time.sleep
6. pytest -s is used to print the "print" statements to the console.
7. multithreading (time sliced tasks), useful in IO operations, database calls, http requests
8. multiprocessing (large number crunching, calculation)
9. what is async (https://www.youtube.com/watch?v=K56nNuBEd0c)
10. diff bw unittest and pytest,
      - unittest is a builtin, pytest is 3rd party.
      -  we have fixtures in pytest, while we have setup/teardow in unittest
      -  pytest has parameterized testing
```python
from datetime import datetime, timedelta

import pytest

testdata = [
    (datetime(2001, 12, 12), datetime(2001, 12, 11), timedelta(1)),
    (datetime(2001, 12, 11), datetime(2001, 12, 12), timedelta(-1)),
]


@pytest.mark.parametrize("a,b,expected", testdata)
def test_timedistance_v0(a, b, expected):
    diff = a - b
    assert diff == expected


@pytest.mark.parametrize("a,b,expected", testdata, ids=["forward", "backward"])
def test_timedistance_v1(a, b, expected):
    diff = a - b
    assert diff == expected
```
unittest doesn't seem to have a formal approach to it.
11. how to teardown in pytest (https://pytest-with-eric.com/pytest-best-practices/pytest-setup-teardown/)










1. diff bw list and tuple: list is mutable data type, while tuple is immutable. since tuple is immutable, it can be used as a key to a dict.
2. when have you used tuple over a list: when passing around a data which I don't want a function to accidentally change, I use a tuple over a list.
3. what is multiprocessing in python(implements parallelism): multiprocessing means invoking multiple instances of the same program, and making it run on different processors.
4. what is multithreading in python (implements concurrency): In multithreading or multiprocessing any kind of context switching is done by Operating System.
5. problems with multiprocessing: added overhead,complexity, difficult to debug (because of interleaved logs)
6. when to use multithreading vs multiprocessing:
    multithreading: io bound process (sending requests to multiple
      database servers and waiting for a response from them),
    multiprocessing: cpu bound process (number crunching, real parallellism)
7. iterators are objects that can be iterated upon by loops (https://realpython.com/python-iterators-iterables/)
    Iterator Protocol 
    A set of rules that must be followed to define an iterator in Python.
8. https://www.geeksforgeeks.org/multiple-inheritance-in-python/ (method resolution order)
9. garbage collection (https://stackify.com/python-garbage-collection/) 2 methods of gc, one is reference counting. In case of cycling reference geenrattional gc is used
   which identifies unreacaable objects and
10. context managers
11. exception handling (custom exceptions)
