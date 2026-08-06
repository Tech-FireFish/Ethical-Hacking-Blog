# Python Crash Course for Ethical Hacking

A beginner-friendly, practical guide on building your first Python project. Day 5 of Ethical Hacking Journal

![EHDay5_Cover](./images/EHDay5_Cover.png)

**Question of the Day: What do you think would be the output of the following code blocks?**

```
from datetime import datetime
current_hour = datetime.now().hour
greeting = "Good morning" if current_hour < 12 else "Good evening"
print(greeting)
```

Choices :
- Good evening
- Syntax Error
- Good morning
- Good morning OR Good evening

**The answer is at the end of the article.**

>If you find yourself doing the same task repeatedly, it’s probably time to automate it.

If you did like to practice the commands, you’ll need:

- A code editor (e.g., Visual Studio Code[Download](https://code.visualstudio.com/download?))
- Python (Download [HERE](https://www.python.org/downloads//))
**Note:** You don’t have to download a code editor if you’re using Kali Linux. In your terminal, you can run `nano filename.py` to create and edit a Python file.

Let’s dive in now. 😄

**Data Types**
Suppose you manage a set of files and input new usernames into the system, Excel or spreadsheet, besides noticing the time goes slower than ever, you’ll notice that the process itself is repetitive. The act of reviewing a document is constant, while the username is the variable in this case. That is where automation comes into play, and also the core idea of developing a program language, which reduces repetitive tasks.

Before heading to the function print(), here are some data types that will enhance your understanding of the explanation.

- String is simply a text enclosed by quotation marks. (e.g. `"Hello World”` is a string data.)
- Boolean represents one of two values: `True` or `False`. In other words, a yes-or-no question. (e.g. `True` , `False` )
- Variable is a container that stores data. It cannot be these keywords: `True`, `False`, or `if`.

In practice, you can run:

```
# Create a variable and assign a value to it
[variable] = [value]
# e.g. 
# message = "hello world"
# username = "Tech-FireFish"
# username_list = ["name1", "name2"]
# username_active = True
# username_id = 1234
```

to assign a specific value to a variable.

>`type()` function returns the data type of the input data.

**Print() and Input()**

You can run string, boolean and variable inside the print() function

```
# print string “Hello World” 
print(“Hello World”) 
# OUTPUT: Hello World

# print boolean value True
print(True)
# OUTPUT: True

# print variable 'message'
message = "hello"
print(message)
# OUTPUT: hello
```

to print different text information or information stored in one or more variables.

As you might have noticed, that is just a pre-programmed result, and it’s constant. The function `input()` allows you to prompt the user for information. Inside the parentheses, you will want to input a question in string type, like this `What is the username?`. Thus, when the program is executed, the program waits for the user to enter a response before continuing.

This being said, a common practice of `input()` will be `variable_name = input("[Question]")` because you don’t want to lose the response from users, so you have to store it in a variable.

**Function**

With this knowledge, we can already construct a simple automated greeting message.

```
# Inquiries the person’s name and position role
print("Hello!")
name = input("What is your name?")
role = input("What is your new job title?")
# integrate the message together.
print("Hello " +  name + ", We are happy to have you onboard as a " + role + "!")
```

Suppose that you don’t want to write repetitively this code, you can use `def function_name():` to group the code together.

**Like this:**

```
def greeting():
  # Inquiries the users for their name and position role
  print("Hello!")
  name = input("What is your name?")
  role = input("What is your new job title?")
  # use `+` to combine the variables and strings together.
  print("Hello " +  name + ", We are happy to have you onboard as a " + role + "!")
```

Thus, you don’t have to write this code block again when you need it. By calling a function like this `greeting()` in a new line, the computer will be instructed to execute the code inside the function `greeting()`.

**Import**
Imagine your teammate already wrote a function that validates usernames. you can simply run:

```
# import function(s) from a specific file
from [filename] import [function_name]
# e.g from datetime import datetime
# This e.g. imports function datetime from file 'datetime'
```

to import functions from another Python file.

**Question ANSWER & Recap**
Back up to our question at the beginning, the answer is **CHOICE 4**.

```
from datetime import datetime
current_hour = datetime.now().hour
greeting = "Good morning" if current_hour < 12 else "Good evening"
print(greeting)
```

**Line 1:** This developer first imported a `datetime` function from the file `datetime`.

**Line 2:** Then, he stores the output of `datetime.now().hour` into the variable `current_hour`. The `.now()` is a method provided by the datetime class that returns the current date and time. The `.hour` is an attribute.

>Methods are functions that are only applicable to a specific data type. An attribute is a specific part of a value.

Meanwhile the `.now()` method captures Year -Month — Day — Hour : Minute : Second : Microsecond, `.hour` retrieves only the hour portion.

Line 3: This conversational expression of code is called “ternary operator”. Basically, you read it like this

`Variable = Value if True Condition else Value if False.`

So, here the developer wrote a condition expression that results in different greetings based on the current hour.

Line 4: He simply displays the value of variable `greeting`.

**Here is a small script that summarized today’s work:**

```
print("Hello!")
name = input("What is your name?")
role = input("What is your new job title?")
from datetime import datetime
current_hour = datetime.now().hour
greeting = "Good morning" if current_hour < 12 else "Good evening"
print(greeting + " " +  name + ", We are happy to have you onboard as a " + role + "!")
```

Congratulations. You made it all the way here. 😄

**Credits**
- Tech-FireFish, Contributor, Profile [URL](https://github.com/Tech-FireFish)

- IBM Ethical Hacking with Open Source Tools Professional Certificate instructed by IBM Skills Network Team, Dee Dee Collette, Christo Oehley on Coursera platform, 2024, [URL](https://www.coursera.org/professional-certificates/ibm-ethical-hacking-with-open-source-tools).
