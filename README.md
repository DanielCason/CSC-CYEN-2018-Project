# CSC-CYEN-2018-Project
A Project  For CSC/CYEN
from Tkinter import *

class Jeopardy(Frame):
    def __init__(self, parent):
        Frame.__init__(self, parent, bg="white")
        #parent.attributes("-fullscreen", True)
        self.setupGUI()

    def setupGUI(self):
        self.display = Label(self, text="", anchor=E, bg="white", height=2, width=15)
        self.display.grid(row=0, column=0, columnspan=5, sticky=E+W+N+S)

        for row in range(6):
            Grid.rowconfigure(self, row, weight=1)
        for col in range(6):
            Grid.columnconfigure(self, col, weight=1)

        # easy label
        img = PhotoImage(file="easy.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=0, column=0, columnspan=2, sticky=N+S+E+W)

        # medium label
        img = PhotoImage(file="medium.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=0, column=2, columnspan=2, sticky=N+S+E+W)

        # hard label
        img = PhotoImage(file="hard.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=0, column=4, columnspan=2, sticky=N+S+E+W)

        # $100 column
        img = PhotoImage(file="100.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=1, column=0, sticky=N+S+E+W)

        img = PhotoImage(file="100.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=2, column=0, sticky=N+S+E+W)

        img = PhotoImage(file="100.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=3, column=0, sticky=N+S+E+W)

        img = PhotoImage(file="100.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=4, column=0, sticky=N+S+E+W)

        img = PhotoImage(file="100.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=5, column=0, sticky=N+S+E+W)

        # $200 column
        img = PhotoImage(file="200.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=1, column=1, sticky=N+S+E+W)

        img = PhotoImage(file="200.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=2, column=1, sticky=N+S+E+W)

        img = PhotoImage(file="200.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=3, column=1, sticky=N+S+E+W)

        img = PhotoImage(file="200.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=4, column=1, sticky=N+S+E+W)

        img = PhotoImage(file="200.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=5, column=1, sticky=N+S+E+W)

        # $300 column
        img = PhotoImage(file="300.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=1, column=2, sticky=N+S+E+W)

        img = PhotoImage(file="300.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=2, column=2, sticky=N+S+E+W)

        img = PhotoImage(file="300.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=3, column=2, sticky=N+S+E+W)

        img = PhotoImage(file="300.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=4, column=2, sticky=N+S+E+W)

        img = PhotoImage(file="300.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=5, column=2, sticky=N+S+E+W)

        # $400 column
        img = PhotoImage(file="400.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=1, column=3, sticky=N+S+E+W)

        img = PhotoImage(file="400.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=2, column=3, sticky=N+S+E+W)

        img = PhotoImage(file="400.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=3, column=3, sticky=N+S+E+W)

        img = PhotoImage(file="400.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=4, column=3, sticky=N+S+E+W)

        img = PhotoImage(file="400.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=5, column=3, sticky=N+S+E+W)

        # $500 column
        img = PhotoImage(file="500.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=1, column=4, sticky=N+S+E+W)

        img = PhotoImage(file="500.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=2, column=4, sticky=N+S+E+W)

        img = PhotoImage(file="500.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=3, column=4, sticky=N+S+E+W)

        img = PhotoImage(file="500.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=4, column=4, sticky=N+S+E+W)

        img = PhotoImage(file="500.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=5, column=4, sticky=N+S+E+W)

        # $600 column
        img = PhotoImage(file="600.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=1, column=5, sticky=N+S+E+W)

        img = PhotoImage(file="600.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=2, column=5, sticky=N+S+E+W)

        img = PhotoImage(file="600.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=3, column=5, sticky=N+S+E+W)

        img = PhotoImage(file="600.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=4, column=5, sticky=N+S+E+W)

        img = PhotoImage(file="600.gif")
        button = Button(self, bg="white", image=img)
        button.image = img
        button.grid(row=5, column=5, sticky=N+S+E+W)

        self.pack(fill=BOTH, expand=1)


window = Tk()
window.title("Make Studying Fun Again")
j = Jeopardy(window)
window.mainloop()
