# CSC-CYEN-2018-Project
A Project  For CSC/CYEN
import abc

class Notecard(object):
    def __init__(self, number):
        self.number = number

    @property
    def number(self):
        return self._number

    @number.setter
    def number(self, value):
        self._number = value

    @abc.abstractmethod   
    def makeNotecard(self, number):
        """ make notecard """
        

class Easy(Notecard):
    def __init__(self, number):
        self.number = number
        Notecard.__init__(self, number)

    def makeNotecard(self, number):
        easy = {}
        for i in range(self.number):
            question = input("Enter a question: ")
            answer = input("Enter an answer: ")
            easy[question] = answer

class Medium(Notecard):
    def __init__(self, number):
        self.number = number
        Notecard.__init__(self, number)

    def makeNotecard(self, number):
        medium = {}
        for i in range(self.number):
            question = input("Enter a question: ")
            answer = input("Enter an answer: ")
            medium[question] = answer

class Hard(Notecard):
    def __init__(self, number):
        self.number = number
        Notecard.__init__(self, number)

    def makeNotecard(self, number):
        hard = {}
        for i in range(self.number):
            question = input("Enter a question: ")
            answer = input("Enter an answer: ")
            hard[question] = answer



e = input("How many easy level questions do you wish to enter? ")
easy = Easy(e)
easy.makeNotecard(e)
m = input("How many medium level questions do you wish to enter? ")
medium = Medium(m)
medium.makeNotecard(m)
h = input("How many hard level questions do you wish to enter? ")
hard = Hard(h)
hard.makeNotecard(h)
