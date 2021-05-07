from tkinter import *

top = Tk ()
groceryList= []

def results():
    print(groceryList)
    
def addToList():
    newItem = E1.get()
    groceryList.append(newItem)
    E1.delete(0, END)

def exportList():
    with open('test.txt', ' w') as f:
        for item in groceryList:
            f.write("%s\n" % item)

def clearWindow():
    for widgets in top.winfo_children():
        widgets.destroy()

def mainMenu():
    clearWindow()
    Lmain = Label(top, text= "BLOCK 5 GUI PROJECT")
    Lmain.grid(column = 2, row =1)

    B1Main = Button(text= " WEEK 1 ", bg="pink", command = week1)
    B1Main.grid(column = 2, row=2)

    B2Main = Button(text= " WEEK 2 ", bg= "pink",)
    B2.grid(column = 2, row=3)

    B3Main = Button(text= " WEEK 1 ", bg="pink",)
    B1Main.grid(column = 2, row=4)


def week1 ():
    #This is a Label widget
    L1 = Label (top, text="    THING MAKER   ")
    L1.grid(column = 0, row = 1)

    #This is a Entry Widget
    E1 = Entry(top, bd = 5)
    E1.grid(column = 0, row = 2)

    #This is a Button widget
    B1 = Button(text="    PRINT THING  ", bg="pink", command = results)
    B1.grid(column=0, row=3,)

    B2 = Button(text="    ADD THING    ", bg="pink", command = addToList)
    B2.grid(column=1, row=2)

    B3 = Button(text="   PUT IT IN FILE   ", bg= "pink", command = exportList)
    B3.grid(column = 3, row = 2)

if __name__=="__main__":
    mainMenu
top.mainloop()
