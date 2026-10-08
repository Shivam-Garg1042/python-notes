https://colab.research.google.com/drive/1DfnVcPYRGJDDrKcpYmEAuPHAR7XeTaKH?usp=sharing#scrollTo=o5waCVTx-wGt

📝 Python Functions: One-Page Quick Revision Notes
1. Function Basics & Docstrings
Definition: Reusable blocks of code defined using the def keyword.
Docstring: Optional documentation string placed inside triple quotes """ immediately under the function definition. Accessible via print(func_name.__doc__).
2. Parameters vs. Arguments
Parameters: Variables listed in the function definition.
Arguments: Values passed to the function when called (Positional, Default, or Keyword).
3. Arbitrary Arguments: *args and **kwargs 💡 (Complex Topic)
*args: Collects excess positional arguments into a Tuple.
**kwargs: Collects excess keyword arguments into a Dictionary.
# Quick Example:
def complex_demo(normal_arg, *args, **kwargs):
    print(normal_arg) # 1
    print(args)       # (2, 3)
    print(kwargs)     # {'val': 'four'}

complex_demo(1, 2, 3, val='four')
4. Memory Execution & Scope 💡 (Complex Topic)
Functions create a local frame in memory. When execution finishes, this local frame is destroyed.
Variable Scope: Local variable changes do not affect global variables unless explicitly specified with the global keyword. Nested inner functions can read outer scopes but cannot modify them in-place directly without nonlocal.
# Quick Example:
def outer_func():
    x = "local"
    def inner_func():
        nonlocal x # target variable in outer scope
        x = "modified_local"
    inner_func()
    return x
# Returns "modified_local"
5. First-Class Citizens 💡 (Complex Topic)
In Python, functions are treated as first-class citizens, meaning they behave like any other variable or object.

# Quick Example (Assign, store in a list, and execute):
def greet(name):
    return f"Hello, {name}!"

func_list = [greet, str.upper]
print(func_list[0]("Alice"))              # Output: "Hello, Alice!"
print(func_list[1](func_list[0]("Alice"))) # Output: "HELLO, ALICE!"
6. Anonymous (Lambda) Functions
Single-line anonymous helper functions: lambda arguments: expression.
7. Higher-Order Functions (HOF) & Map/Filter/Reduce 💡 (Complex Topic)
Functions that take other functions as arguments, or return them.

# Quick Example (Mapping/Filtering with Lambdas):
nums = [1, 2, 3, 4]

# Map: Transform each element
squared = list(map(lambda x: x**2, nums)) # [1, 4, 9, 16]

# Filter: Keep elements satisfying condition
evens = list(filter(lambda x: x % 2 == 0, nums)) # [2, 4]
