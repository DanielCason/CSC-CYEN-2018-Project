# CSC-CYEN-2018-Project
A Project  For CSC/CYEN


### Aside from minor bugs, should work ###

### Can store, receive, delete, and create questions and sections ###
### Stored in the format {"section"{"number of questions{"answers":"questions"}}} ###

### Cannot have multiple sections of the same name, or questions in the same
### Section with the same Answers###

### You should not need these files ahead of time, they will be created when nessecary
### The Files : number, answers, questions, subject###



### Does nothing ###
def play(n):
    pass
### Retrieves stored data ###
def receive():
    MyLength = []
    MySection = []
    MyAnswers = []
    MyQuestions = []
    MyDict1 = {}
    MyDict3= {}
    MyDict2 = {}
    r = open("number.txt","r")
    for line in r:
        MyLength.append(line[0:(len(line)-1)])
    r.close()
    r = open("answers.txt","r")
    for line in r:
        MyAnswers.append(line[0:(len(line)-1)])
    r.close()
    r = open("questions.txt","r")
    for line in r:
        MyQuestions.append(line[0:(len(line)-1)])
    r.close()
    r = open("subject.txt","r")
    for line in r:
        MySection.append(line[0:(len(line)-1)])
    r.close()
    print MyLength
    print MyAnswers
    print MyQuestions
    print MySection
    for i in range(0,(len(MySection))):
        s = int(MyLength[i])
        for j in range(0,s):
            MyDict3[MyAnswers[j]]=MyQuestions[j]
        MyAnswers = MyAnswers[s:]
        MyQuestions = MyQuestions[s:]
        for l in range(0,1):
            MyDict2[MyLength[l]]=MyDict3
        print MyDict2
        MyDict1[MySection[i]]=MyDict2
        print MyDict1
        MyDict3={}
        MyDict2={}
    return MyDict1
### stores all current data into txt files ###
### cannot update with individual data, throws everything out of order ###
### WARNING : WILL ERASE DATA FROM THOSE FILES FIRST###
def store(n):
    r = open("answers.txt","w")
    r.close
    r = open("questions.txt","w")
    r.close()
    r = open("number.txt","w")
    r.close()
    r = open("subject.txt","w")
    v = n.keys()
    o = len(v)
    for i in range(0,o):
        r.write(v[i] + "\n")
    r.close()
    for i in range(0,o):
        z = n[v[i]]
        z1 = z.keys()
        a = z[z1[0]]
        r = open("answers.txt","a")
        b = a.keys()
        q = len(b)
        for k in range(0,q):
            c = b[k]
            s = len(c)
            for m in range(0,s):
                d = c[m]
                r.write(d)
            r.write("\n")
        r.close()
        r = open("questions.txt","a")
        for p in range(0,q):
            e = a[b[p]]
            for ee in range(0,(len(e))):
                r.write(e[ee])
        r.write("\n")
        r.close()
        r = open("number.txt","a")
        a1 = len(a)
        r.write(str(a1))
        r.write("\n")
        r.close()
#### Just used to control currenty ###
def options(n):
    action = raw_input("Create or Delete?")
    action.lower()
    if (action == "create"):
        action = raw_input("New: all, section, question")
        if (action == "all"):
            n = createall()
        elif(action == "section"):
            n = creates(n)
        elif(action == "question"):
            n = createq(n)
    elif(action == "delete"):
        action = raw_input("Remove: all, section, question")
        if (action == "question"):
            n = deleteq(n)
        elif(action == "section"):
            n = deletes(n)
        elif(action == "all"):
            n = deleteall(n)
    return n

### Does as the name says, creates many sections and questions ###
def createall():
    MyAnswers = []
    MyQuestions = []
    MyRating = []
    MyLength = []
    MyDict1 = {}
    MyDict2 = {}
    MyDict3 = {}
    num = input("How many sections would you like?")
    for i in range (0,num):
        section = raw_input("What is the name for this section?")
        num1 = input("How many questions would you like?")
        MyLength.append(num1)
        for j in range (0,(num1)):
            q = raw_input("Question {}:".format(j+1))
            a = raw_input("Answer {}:".format(j+1))
            MyAnswers.append(a)
            MyQuestions.append(q)
        for k in range(0,num1):
            MyDict3[MyAnswers[k]]=MyQuestions[k]
        print MyDict3
        MyAnswers = []
        MyQuestions = []
        for l in range(0,1):
            MyDict2[MyLength[i]]=MyDict3
        print MyDict2
        MyDict1[section]=MyDict2
        print MyDict1
        MyDict3={}
        MyDict2={}
    return MyDict1
### Creates an individual section ###
def creates(o):
    section = raw_input("What is the name of the section you would like to add?")
    num = input("How man questions for this section?")
    MyLength = [num]
    MyAnswers = []
    MyQuestions = []
    MyDict3 = {}
    MyDict2 = {}
    for i in range (0,num):
        q = raw_input("Question {}:".format(i+1))
        a = raw_input("Answer {}:".format(i+1))
        MyAnswers.append(a)
        MyQuestions.append(q)
    for k in range(0,num):
        MyDict3[MyAnswers[k]]=MyQuestions[k]
    print MyDict3
    MyAnswers = []
    MyQuestions = []
    for l in range(0,1):
        MyDict2[num]=MyDict3
    print MyDict2
    o[section]=MyDict2
    print o
    return o
### Creates an indivdual question ###
def createq(o):
    MyAnswers = []
    MyQuestions = []
    MyDict3 = {}
    add = raw_input("Which section do you wish to add to? {}".format(o.keys()))
    p = o[add]
    r = p.keys()
    v = r[0]
    add1 = input("How many questions will you add?")
    s = p[v]
    for i in range (0,add1):
        q = raw_input("Question {}:".format(i+1))
        a = raw_input("Answer {}:".format(i+1))
        MyAnswers.append(a)
        MyQuestions.append(q)
    for j in range (0,add1):
        s[MyAnswers[j]] = MyQuestions[j]
    total = add1+v
    p[total] = s
    del p[v]
    print p
    o[add] = p
    return o

### Deletes individual questions ###    
def deleteq(o):
    remove = raw_input("From Which section do you wish to remove from? {}".format(o.keys()))
    p = o[remove]
    print p
    r = p.keys()
    print r
    v= r[0]
    gone = raw_input("Which question number would you like gone? Number of question: {}, Questions: {}".format(r,p[v]))
    s = p[v]
    print s
    del s[gone]
    print s
    p[v] = s
    o[remove]=p
    return o
### deletes everything : including saved if requested ###
def deleteall(u):
    action = raw_input("Delete everything from this session? Yes or No ")
    action.lower()
    if (action == "yes"):
        u = {}
    action = raw_input("Delete everything from the saved storage? Yes or No?")
    if (action == "yes"):
        w = open("answers.txt","w")
        w.close()
        w = open("number.txt","w")
        w.close()
        w = open("questions.txt","w")
        w.close()
        w = open("subject.txt","w")
        w.close()
    return u
### deletes indivdual sections ###
def deletes(o):
    remove = raw_input("Which section do you wish to remove? {}".format(o.keys()))
    del o[remove]
    print o
    return o

################################################################
n = {}
action = raw_input("import saved? yes or no")
if (action == "yes"):
    n = receive()
while (True):
    
    action = raw_input("What do you want to do? Play, Edit, Quit, Send")
    action.lower()
    if (action == "play"):
        play(n)
    elif(action == "edit"):
        n = options(n)
    elif(action == "quit"):
        pass
    elif(action == "send"):
        store(n)
    else:
        print "Invalid response, try again"
    print n
