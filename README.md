from tkinter import *

top = Tk ()
groceryList= []

def results():
    print(groceryList)
    
def addToList():
    newItem = E1.get()
    groceryList.append(newItem)
    
#This is a Label widget
L1 = Label (top, text="    LOVING WORD   ")
L1.grid(column = 0, row = 1)

#This is a Entry Widget
E1 = Entry(top, bd = 5)
E1.grid(column = 0, row = 2)

#This is a Button widget
B1 = Button(text="    PRINT LOVE    ", bg="#e39cff", command = results)
B1.grid(column=0, row=3,)

B2 = Button(text="    ADD AFFECTION    ", bg="pink", command = addToList)
B2.grid(column=1, row=2)

top.mainloop()
