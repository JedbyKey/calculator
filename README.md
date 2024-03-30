# Calculator
## Root
To make root we use tkinter:
```python
from tkinter import *
window = Tk()
window.title("Calculator")
window.geometry("500x500")

window.mainloop()
```
Then we should create button with arithmetic operations and digits:
```python
button1 = Button(frame, text=1, height=4, width=9, font=35, command=lambda: button_press(1))

button1.grid(row=0, column=0)


button2 = Button(frame, text=2, height=4, width=9, font=35, command=lambda: button_press(2))

button2.grid(row=0, column=1)


button3 = Button(frame, text=3, height=4, width=9, font=35, command=lambda: button_press(3))


button3.grid(row=0, column=2)

#keep doing other digits



plus = Button(frame, text="+", height=4, width=9, font=35, command=lambda: button_press("+"))


plus.grid(row=0, column=3)


minus = Button(frame, text="-", height=4, width=9, font=35, command=lambda: button_press("-"))

minus.grid(row=1, column=3)

#then make multiply, decimal etc.

```
Now we should make functions for buttons:
```python
def button_press(num):
    
    global equation_text 

    equation_text = equation_text + str(num)

    equation_label.set(equation_text)



def equals():
    
    global equation_text

    try:

        total = str(eval(equation_text))

        equation_label.set(total)

        equation_text = total

    except SyntaxError:

        equation_label.set("syntax error")

        equation_text = ""

    except ZeroDivisionError:

        equation_label.set("arichmetic error")

        equation_text = ""

```
We also made some errors like division on zero or some syntax errors. Now we have calculator with simple interface
### Author: Alkadarsky Ali
