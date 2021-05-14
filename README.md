\from tkinter import *
import random
top = Tk ()
groceryList= []
myRolls = []
rollTimes = 0
dieType = 0

def results():
    print(groceryList)
    
def addToList():
    newItem = E1.get()
    groceryList.append(newItem)
    E1.delete(0, END)

def exportList():
    with open('test.txt', 'w') as f:
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

    B2Main = Button(text= " WEEK 2 ", bg= "pink", command = week2)
    B2Main.grid(column = 2, row=3)

    B3Main = Button(text= " WEEK 1 ", bg="pink",)
    B1Main.grid(column = 2, row=4)


def week1 ():

        
    def addToList():
        newItem = E1.get()
        groceryList.append(newItem)
        E1.delete(0, END)

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

    Bclear = Button(text="MAIN MENU", bg= "pink", command = exportList)
    Bclear.grid(column = 5, row = 2)


def week2():
    def rollDice():

        dieType = E1W2.get()

        rollTimes = E2W2.get()

        clearWindow()
        for x in range (0, int(rollTimes)):
            myRolls.append(random.randint(1,int(dieType)))

        L4W2 = Label(top,text=" LIST OF ROLLS")
        L4W2.grid(column = 0, row = 1)

        L5W2 = Label(top,text="{}".format(myRolls))
        L5W2.grid(column = 0, row = 2)

        B2W2 = Button(text=" EXIT ", bg= "pink", command = mainMenu)
        B2W2.grid(column = 0, row = 3)        

        
    clearWindow()

    B1W2 = Button(text="ROLL DICE", bg= "pink", command = rollDice)
    B1W2.grid(column= 2, row = 4)
    
    L1W2 = Label(top, text="DICE ROLLER PROGRAM")
    L1W2.grid(column = 2, row=1)

    L2W2 = Label(top,text="HOW MANY SIDES")
    L2W2.grid(column = 0, row =2)

    L3W2 = Label(top, text="HOW MANY ROLLS")
    L3W2.grid(column = 2, row =2)

    E1W2 = Entry(top,bd=5)
    E1W2.grid(column=0, row = 3)

    E2W2 = Entry(top,bd=5)
    E2W2.grid(column= 2, row= 3)

if __name__=="__main__":
    mainMenu()
    top.mainloop()
