# Operators

> ```ruby
> # Arithmetic Operators
> a + b           # Adition
> a - b           # Subtraction
> a * b           # Multiplication
> a / b           # Division
> a % b           # Modulus
> a**b            # Exponent
>
> # Comparison Operators
> a == b          # Checks if the value of two operands are equal
> a != b          # Checks if the value of two operands are different
> a > b           # Checks if the value of left operand is greater than the value of right operand
> a < b           # Checks if the value of left operand is less than the value of right operand
> a >= b          # Checks if the value of left operand is greater than or equal to the value of right operand
> a <= b          # Checks if the value of left operand is less than or equal to the value of right operand
> a <==> b        # Returns 0 if first operand equals second, 1 if greater and -1 if less
> (1...10) === 5  # Used to test equality within a when clause of a case statement
> a.eql?(b)       # Check if the type and value are equals
> a.equal?b       # Check if the the objects have the same id
>
> # Logical Operators - You can use these operators to help you compare two objects & make a decision based on the result
> a && b          # "and" operator (higher precedence)
> a and b         # "and" operator 
> a || b          # "or" operator (higher precedence)
> a or b          # "or" operator 
> !a              # Negation operator (higher precedence)
> not a           # Negation operator
>
> # Bitwise Operators
> a = 60          # 0011 1100 in binary format
> b = 13          # 0000 1101 in binary format
> ------------------
> a&b             # 0000 1100
> a|b             # 0011 1101
> a^b             # 0011 0001
> ~a              # 1100 0011
>
> # Parallel Assignment
> a, b, c = 10, 20, 30  # a = 10, b = 20, c = 30
> a, b = b, c           # Swapping the values
>
> # Ternary Operator
> true ? "true" : "false"   # Result is "true"
> ```

