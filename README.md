# balanced-parenthesis-in-the-expression-or-not-
from collections import deque
ex = input("ENTER EXPRESSION: ")
stack = deque()
result = "EXPRESSION IS BALANCE:"
counter = 0
for i in ex :
    if (i == '(' or i == '{' or i == '['):
        stack.append(i)
        counter = counter + 1
    elif (i == ')' or i == '}' or i == ']'):
        if (len(stack) != 0):
            if (i == ')'):
                if(stack[-1] == '('):
                    counter = counter - 1
            if (i == '}'):
                if (stack[-1] == '{'):
                    counter = counter - 1
            if (i == ']'):
                if (stack[-1] == '['):
                    counter = counter - 1
            stack.pop()
        else:
            result = "EXPRESSION IS UNBALANCE!"
            
if (counter != 0):
    result = "EXPRESSION IS UNBALANCE:"
print (result)
