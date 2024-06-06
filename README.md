PYTHON REVISION AND PRACTICE QUESTIONS
def greet(name):  # Function definition with parameter 'name'
    """This function prints a greeting message."""
    print("Hello", name + "!")
greet("SREE")  
# Output: Hello SREE!
def calculate_area(length, width):
    """This function calculates the area of a rectangle."""
    return length * width

# Calling the function with positional arguments
area = calculate_area(5, 3)  # length = 5, width = 3
print(area)  # Output: 15

def calculate_area(length, width):
    """This function calculates the area of a rectangle."""
    return length * width

def greet(name, message="Hello"):
    """This function greets someone with an optional message."""
    print(message, name + "!")

# Calling with keyword arguments (notice order is switched)
greet(message="Hi", name="SREE")  # Output: Hi SREE!

def greet(name, message="Hello"):
    """This function greets someone with an optional message."""
    print(message, name + "!")

# Using the default argument for message
greet("SREE")  # Output: Hello SREE!


# Calling the function with positional arguments
area = calculate_area(5, 3)  # length = 5, width = 3
print(area)  # Output: 15

def summarize(*args):
    """This function prints all passed arguments."""
    for arg in args:
        print(arg)

# Passing a variable number of arguments
summarize("SREE", "Python", "Functions")  
# Output:
# SREE
# Python
# Functions

def print_info(**kwargs):
    """This function prints key-value pairs of passed keyword arguments."""
    for key, value in kwargs.items():
        print(f"{key}: {value}")

# Passing a variable number of keyword arguments
print_info(name="SREE", language="Python", topic="Functions")
# Output:
# name: SREE
# language: Python
# topic: Functions
def shout(text):
    """Converts the input text to uppercase."""
    return text.upper()

def whisper(text):
    """Converts the input text to lowercase."""
    return text.lower()

def modify_text(func, text):
    """Modifies text using the passed function."""
    return func(text)

# Example usage:
input_text = "Hello, World!"

# Passing the 'shout' function as an argument
result_shout = modify_text(shout, input_text)
print(result_shout)  # Output: HELLO, WORLD!

# Passing the 'whisper' function as an argument
result_whisper = modify_text(whisper, input_text)
print(result_whisper)  # Output: hello, world!

add = lambda x, y: x + y
result = add(5, 3)
print(result)

# Global variable
global_var = 10

def example_function():
    # Local variable
    local_var = 20
    print("Inside function:", local_var, global_var)

# Accessing global variable
print("Outside function:", global_var)

# Accessing local variable - Will raise NameError
# print("Outside function:", local_var)

# Calling the function
example_function()

def is_even(num):
    """Checks if a number is even."""
    if num % 2 == 0:
        return True
    else:
        return False

# Using the return value directly in a condition
if is_even(6):
    print("6 is even.")
else:
    print("6 is odd.")

# Global variable (minimum passing grade)
MIN_GRADE = 70

def analyze_grades(names, grades):
    """This function analyzes student grades and returns average and failing students."""
    
    # Local variables
    total_grade = 0
    failing_students = []

    # Using zip to combine names and grades (works like map in this case)
    for name, grade in zip(names, grades):
        total_grade += grade

        # Local function to check if a student is failing (using lambda for brevity)
        is_failing = lambda g: g < MIN_GRADE

        if is_failing(grade):
            failing_students.append(name)

    # Calculate average grade
    average = total_grade / len(grades)

    # Returning multiple values as a tuple
    return average, failing_students

# Sample student data (can be replaced with actual data retrieval)
student_names = ["J", "Ishu", "Lakshay", "Avi"]
student_grades = [85, 60, 90, 75]

# Function call (no modification of global variable here)
average_grade, failing_list = analyze_grades(student_names, student_grades)

print("Average Grade:", average_grade)
print("Failing Students:", failing_list)

****PRACTICE QUESTIONS****

**1**

import math
def calculate_area(shape, dimensions):
    if shape == "rectangle":
        length, width = dimensions
        return length * width
    elif shape == "circle":
        radius, = dimensions
        return math.pi * radius ** 2
    else:
        raise ValueError(f"Invalid shape: {shape}")

print("Note: All dimensions entered will be displayed in centimeters (cm).")

shape = input("Enter the shape (rectangle/circle): ").strip().lower()
if shape == "rectangle":
    length = float(input("Enter the length of the rectangle in cm: "))
    width = float(input("Enter the width of the rectangle in cm: "))
    dimensions = (length, width)
elif shape == "circle":
    radius = float(input("Enter the radius of the circle in cm: "))
    dimensions = (radius,)
else:
    raise ValueError(f"Invalid shape: {shape}")

area = calculate_area(shape, dimensions)

print(f"The area of the {shape} is: {area} square cm")

**2**

def analyze_list(numbers):
    # Calculate minimum value
    min_value = min(numbers)

    max_value = max(numbers)
    
    average_value = sum(numbers) / len(numbers) if numbers else 0
    
    stats = {
        'minimum': min_value,
        'maximum': max_value,
        'average': average_value
    }
    return stats
input_list = [10, 20, 30, 40, 50]
output_stats = analyze_list(input_list)
print(f"Input list: {input_list}")
print(f"Statistics: {output_stats}")

**3**

def analyze_list(numbers):
    """Calculate statistics (minimum, maximum, average) of a list of numbers."""
    if not numbers:
        return {}  # Return an empty dictionary if the input list is empty
    
    # Calculate minimum value
    min_value = min(numbers)
    
    # Calculate maximum value
    max_value = max(numbers)
    
    # Calculate average value
    average_value = sum(numbers) / len(numbers)
    
    # Create a dictionary to store the calculated statistics
    stats = {
        'minimum': min_value,
        'maximum': max_value,
        'average': average_value
    }
    
    return stats

# Test the function
numbers = [10, 20, 30, 40, 50]
result = analyze_list(numbers)
print("Statistics:", result)

**4**

def filter_short_names(names, max_length):
    """Filter names shorter than max_length."""
    # Use filter with a lambda function to return a new list containing only names shorter than the provided max_length
    short_names = list(filter(lambda name: len(name) < max_length, names))
    return short_names

# Test the function
product_names = ["Apple", "Banana", "Orange", "Grapes", "Watermelon"]
max_length = 6
short_names = filter_short_names(product_names, max_length)
print("Short Names:", short_names)

**5**

def analyze_text(text):
    """Analyze a block of text."""
    # Count number of words
    words = text.split()
    num_words = len(words)
    
    # Count number of characters (excluding whitespaces)
    num_characters = sum(len(word) for word in words)
    
    # Create a dictionary to store word frequencies
    word_freq = {}
    for word in words:
        word = word.lower()  # Convert to lowercase for case-insensitive matching
        word_freq[word] = word_freq.get(word, 0) + 1
    
    # Find the most frequent word
    most_frequent_word = max(word_freq, key=word_freq.get)
    
    # Return a dictionary containing the counts and the most frequent word
    analysis_result = {
        'num_words': num_words,
        'num_characters': num_characters,
        'most_frequent_word': most_frequent_word
    }
    
    return analysis_result

# Test the function
text = "Python is created by Guido van Rossum ."
result = analyze_text(text)
print("Analysis Result:", result)
