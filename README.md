# Title: Logging Legends: Harnessing the Power of Logging in Python Applications

## Introduction

Logging is a critical aspect of software development that involves capturing and storing relevant information about the behavior of a program. It provides developers with a way to track and diagnose errors, monitor application performance, and understand user behavior. Logging is an essential tool for identifying and resolving issues in software applications, especially in complex systems.

## Example Code

```
import logging

logging.basicConfig(level=logging.DEBUG)

def divide(x, y):
    try:
        result = x / y
        logging.debug(f"The result of {x}/{y} is {result}")
    except ZeroDivisionError:
        logging.error("Cannot divide by zero")

if __name__ == "__main__":
    divide(10, 2)
    divide(10, 0)
```

## Instructions

**Basic Logging in Python**

- [ ] Have the students create a new Python file and name it program.py.
- [ ] They should start by importing the logging module: import logging.
- [ ] Students should then add the following code to the file:

```
logging.basicConfig(level=logging.DEBUG)

def divide(x, y):
    try:
        result = x / y
        logging.debug(f"The result of {x}/{y} is {result}")
    except ZeroDivisionError:
        logging.error("Cannot divide by zero")

if __name__ == "__main__":
    divide(10, 2)
    divide(10, 0)
```

- This code defines a function that divides two numbers and logs the result or an error if there is a division by zero.

- The basicConfig() function sets the logging level to DEBUG, which means that all the logging statements with a level of DEBUG or higher will be printed.
Configuring Loggers and Handlers

- Have the students modify their code to create a logger object and configure it to write log messages to a file:

```
logger = logging.getLogger(__name__)
logger.setLevel(logging.DEBUG)

handler = logging.FileHandler("program.log")
handler.setLevel(logging.DEBUG)

formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')
handler.setFormatter(formatter)

logger.addHandler(handler)
```

- This code creates a new logger object with the same name as the current module and sets its level to DEBUG.

- It also creates a new file handler object that writes log messages to a file named program.log.

- The formatter object defines the format of the log messages, which includes the timestamp, the logger name, the severity level, and the message.
Finally, the handler object is added to the logger object, which ensures that all the logging statements with a level of DEBUG or higher are written to the file.
