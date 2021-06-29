# Building Python Packages
## What is Python Package and benefits
### Structure

- step 1 ` create an app folder`
- step 2 inside app folder ` __init__.py` empty - to initiate our package
- step 3 inside app folder `fizzbuzz.py` to add our functionality
- step 4 create `program.py` on dir level - to use as our 
- `setup.py` on a dir level - to describe our module details such as versioon, author and contact details

```python
building_python_package
--app
--- __init__.py
--- fizzbuzz.py
program.py
setup.py
```
- Let's build our package starting with setup.py
```python
from setuptools import setup

# Let's add some information about your package
setup(name = "app")
version = "1.0"
description = "Python app"
author = "Prathima at Sparta Global"
author_email = "ramagiri.prathima@gmail.com"
url = "https://spartaglobal.com"
```
- code for fizzbuzz.py
```python
class Fizzbuzz:

    def __init__(self, start_of_range, end_of_range):
        self.fizzrange = range(start_of_range, end_of_range)
        self.fizzbuzz_list = []
        self._fizzbuzz_iterator()

    def _divisible_by(self, num1, num2):
        if num1 % num2 == 0:
            return True
        else:
            return False

    def _fizzbuzz_iterator(self):

        for num in self.fizzrange:
            if self._divisible_by(num, 15):
                self.fizzbuzz_list.append("fizzbuzz")
            elif self._divisible_by(num, 5):
                self.fizzbuzz_list.append("buzz")
            elif self._divisible_by(num, 3):
                self.fizzbuzz_list.append("fizz")
            else:
                self.fizzbuzz_list.append(num)

```
- code for program.py
```python
from app.fizzbuzz import Fizzbuzz

one_to_100 = Fizzbuzz(1, 100)

print(one_to_100.fizbuzz_list)
```

- pip install . to install our package using pip package manager
