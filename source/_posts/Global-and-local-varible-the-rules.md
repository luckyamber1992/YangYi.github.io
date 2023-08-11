---
title: Global and local varible | the rules
date: 2023-08-11 11:26:12
tags:
  - Global variable
  - scope
  - local variable
---

# Global Variables:

- Global variables are defined at the outermost level of a Python program or within a module.
- They are accessible from any part of the program, including within functions.
- To modify a global variable from within a function, you need to use the global keyword to indicate that you're referring to the global variable, not creating a new local variable with the same name.

```
global_variable = 10
def modify_global():
    global global_variable
    global_variable += 5
modify_global()
print(global_variable)  # Output: 15
```

# Local Variables:

- Local variables are defined within a specific function's scope and are only accessible within that function unless explicitly returned.
- A local variable with the same name as a global variable will shadow (override) the global variable within the function's scope.

```
global_variable = 10

def modify_local():
    local_variable = 5
    print(local_variable)

modify_local()  # Output: 5
print(global_variable)  # Output: 10
```

- Modifying Global Variables from Local Scope:
  By default, local variables do not modify global variables directly. They can modify mutable objects (like lists or dictionaries) that are globally accessible, but they cannot reassign a global variable to refer to a new object without using the global keyword.

```
global_list = [1, 2, 3]

def modify_global_list():
    global_list.append(4)

modify_global_list()
print(global_list)  # Output: [1, 2, 3, 4]
```

To reassign a global variable from within a function, you need to use the global keyword.

```
global_variable = 10

def modify_global():
    global global_variable
    global_variable = 20

modify_global()
print(global_variable)  # Output: 20
```

- Summary
  local variables can modify global variables indirectly through mutable objects or by using the global keyword to modify or reassign global variables. However, it's generally considered better practice to avoid modifying global variables from within functions, as it can make code harder to understand and debug. Instead, it's recommended to pass values as function arguments and return modified values if necessary.
