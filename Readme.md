Contributing guidelines
Before contributing
Welcome to TheAlgorithms/Python! Before sending your pull requests, make sure that you read the whole guidelines. If you have any doubt on the contributing guide, please feel free to state it clearly in an issue or ask the community in Gitter.

Contributing
Contributor
We are very happy that you consider implementing algorithms and data structures for others! This repository is referenced and used by learners from all over the globe. Being one of our contributors, you agree and confirm that:

You did your work - no plagiarism allowed
Any plagiarized work will not be merged.
Your work will be distributed under MIT License once your pull request is merged
Your submitted work fulfils or mostly fulfils our styles and standards
New implementation is welcome! For example, new solutions for a problem, different representations for a graph data structure or algorithm designs with different complexity but identical implementation of an existing implementation is not allowed. Please check whether the solution is already implemented or not before submitting your pull request.

Improving comments and writing proper tests are also highly welcome.

Contribution
We appreciate any contribution, from fixing a grammar mistake in a comment to implementing complex algorithms. Please read this section if you are contributing your work.

Your contribution will be tested by our automated testing on GitHub Actions to save time and mental energy. After you have submitted your pull request, you should see the GitHub Actions tests start to run at the bottom of your submission page. If those tests fail, then click on the details button try to read through the GitHub Actions output to understand the failure. If you do not understand, please leave a comment on your submission page and a community member will try to help.

Please help us keep our issue list small by adding fixes: #{$ISSUE_NO} to the commit message of pull requests that resolve open issues. GitHub will use this tag to auto-close the issue when the PR is merged.

What is an Algorithm?
An Algorithm is one or more functions (or classes) that:

take one or more inputs,
perform some internal calculations or data manipulations,
return one or more outputs,
have minimal side effects (Ex. print(), plot(), read(), write()).
Algorithms should be packaged in a way that would make it easy for readers to put them into larger programs.

Algorithms should:

have intuitive class and function names that make their purpose clear to readers
use Python naming conventions and intuitive variable names to ease comprehension
be flexible to take different input values
have Python type hints for their input parameters and return values
raise Python exceptions (ValueError, etc.) on erroneous input values
have docstrings with clear explanations and/or URLs to source materials
contain doctests that test both valid and erroneous input values
return all calculation results instead of printing or plotting them
Algorithms in this repo should not be how-to examples for existing Python packages. Instead, they should perform internal calculations or manipulations to convert input values into different output values. Those calculations or manipulations can use data types, classes, or functions of existing Python packages but each algorithm in this repo should add unique value.

Pre-commit plugin
Use pre-commit to automatically format your code to match our coding style:

python3 -m pip install pre-commit  # only required the first time
pre-commit install
That's it! The plugin will run every time you commit any changes. If there are any errors found during the run, fix them and commit those changes. You can even run the plugin manually on all files:

pre-commit run --all-files --show-diff-on-failure
Coding Style
We want your work to be readable by others; therefore, we encourage you to note the following:

Please write in Python 3.9+. For instance: print() is a function in Python 3 so print "Hello" will not work but print("Hello") will.

Please focus hard on the naming of functions, classes, and variables. Help your reader by using descriptive names that can help you to remove redundant comments.

Single letter variable names are old school so please avoid them unless their life only spans a few lines.
Expand acronyms because gcd() is hard to understand but greatest_common_divisor() is not.
Please follow the Python Naming Conventions so variable_names and function_names should be lower_case, CONSTANTS in UPPERCASE, ClassNames should be CamelCase, etc.
We encourage the use of Python f-strings where they make the code easier to read.

Please consider running psf/black on your Python file(s) before submitting your pull request. This is not yet a requirement but it does make your code more readable and automatically aligns it with much of PEP 8. There are other code formatters (autopep8, yapf) but the black formatter is now hosted by the Python Software Foundation. To use it,

python3 -m pip install black  # only required the first time
black .
All submissions will need to pass the test flake8 . --ignore=E203,W503 --max-line-length=88 before they will be accepted so if possible, try this test locally on your Python file(s) before submitting your pull request.

python3 -m pip install flake8  # only required the first time
flake8 . --ignore=E203,W503  --max-line-length=88 --show-source
Original code submission require docstrings or comments to describe your work.

More on docstrings and comments:

If you used a Wikipedia article or some other source material to create your algorithm, please add the URL in a docstring or comment to help your reader.

The following are considered to be bad and may be requested to be improved:

x = x + 2	# increased by 2
This is too trivial. Comments are expected to be explanatory. For comments, you can write them above, on or below a line of code, as long as you are consistent within the same piece of code.

We encourage you to put docstrings inside your functions but please pay attention to the indentation of docstrings. The following is a good example:

def sum_ab(a, b):
    """
    Return the sum of two integers a and b.
    """
    return a + b
Write tests (especially doctests) to illustrate and verify your work. We highly encourage the use of doctests on all functions.

def sum_ab(a, b):
    """
    Return the sum of two integers a and b
    >>> sum_ab(2, 2)
    4
    >>> sum_ab(-2, 3)
    1
    >>> sum_ab(4.9, 5.1)
    10.0
    """
    return a + b
These doctests will be run by pytest as part of our automated testing so please try to run your doctests locally and make sure that they are found and pass:

# python3 -m doctest -v my_submission.py
The use of the Python builtin input() function is not encouraged:

input('Enter your input:')
# Or even worse...
input = eval(input("Enter your input: "))
However, if your code uses input() then we encourage you to gracefully deal with leading and trailing whitespace in user input by adding .strip() as in:

starting_value = int(input("Please enter a starting value: ").strip())
The use of Python type hints is encouraged for function parameters and return values. Our automated testing will run mypy so run that locally before making your submission.

def sum_ab(a: int, b: int) -> int:
    return a + b
Instructions on how to install mypy can be found here. Please use the command mypy --ignore-missing-imports . to test all files or mypy --ignore-missing-imports path/to/file.py to test a specific file.

List comprehensions and generators are preferred over the use of lambda, map, filter, reduce but the important thing is to demonstrate the power of Python in code that is easy to read and maintain.

Avoid importing external libraries for basic algorithms. Only use those libraries for complicated algorithms.

If you need a third-party module that is not in the file requirements.txt, please add it to that file as part of your submission.

Other Requirements for Submissions
If you are submitting code in the project_euler/ directory, please also read the dedicated Guideline before contributing to our Project Euler library.

The file extension for code files should be .py. Jupyter Notebooks should be submitted to TheAlgorithms/Jupyter.

Strictly use snake_case (underscore_separated) in your file_name, as it will be easy to parse in future using scripts.

Please avoid creating new directories if at all possible. Try to fit your work into the existing directory structure.

If possible, follow the standard within the folder you are submitting to.

If you have modified/added code work, make sure the code compiles before submitting.

If you have modified/added documentation work, ensure your language is concise and contains no grammar errors.

Do not update the README.md or DIRECTORY.md file which will be periodically autogenerated by our GitHub Actions processes.

Add a corresponding explanation to Algorithms-Explanation (Optional but recommended).

All submissions will be tested with mypy so we encourage you to add Python type hints where it makes sense to do so.

Most importantly,

Be consistent in the use of these guidelines when submitting.
Join Gitter now!
Happy coding!