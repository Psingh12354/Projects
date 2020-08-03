<h1 align=center><b>Project Python</b></h1>

<p align=center><b><i>My Projects</i></b></p>

<p> Check below to get the codes</p>

### Quiz : 

```
from tkinter import *
from Question import Question
root=Tk()
class Question:
    def __init__(self, prompt, answer):
        self.prompt = prompt
        self.answer = answer
root.geometry("600x600")
question_prompts = [
     "What color are apples?\n(a) Red/Green\n(b) Orange\n(c) Yellow\n",
     "What color are bananas?\n(a) Red/Green\n(b) Yellow\n(c) None of these\n",
    "What is the capital of India?\n(a) Mumbai\n(b) Delhi\n(c) Calcuta\n",
     "Who i am?\n(a) Human\n(b) Animal\n(c) Both a and b\n",
     "Where do we leave?\n(a) Mars\n(b) Earth\n(c) Jupiter\n",
     "Is plant has cell?\n(a) Yes\n(b) No\n(c) Don't know what is plant\n",
     "What is computer?\n(a) A electronic device\n(b) A mosquito\n(c) None of these\n",
     "Who give food?\n(a) Mother\n(b) Farmer\n(c) You don't need food\n",
     "Which of them rotate?\n(a) Fan\n(b) Van\n(c) You\n",
     "What comes after 10?\n(a) 12\n(b) 9\n(c) 11\n",
]

questions = [
     Question(question_prompts[0], "a"),
     Question(question_prompts[1], "b"),
    Question(question_prompts[2], "b"),
     Question(question_prompts[3],"c"),
     Question(question_prompts[4], "b"),
     Question(question_prompts[5], "a"),
     Question(question_prompts[6], "a"),
     Question(question_prompts[7], "b"),
     Question(question_prompts[8], "a"),
     Question(question_prompts[9], "c"),

]

def run_quiz(questions):
     score = 0
     for question in questions:
          answer = input(question.prompt)
          if answer == question.answer:
               score += 1
     print("you got", score, "out of", len(questions))
run_quiz(questions)
mainloop()
```

### Calculator : 

```
from tkinter import *
def btnClick(numbers):
    global operator
    operator=operator+str(numbers)
    text_Input.set(operator)
def btnClearDisplay():
    global operator
    operator=""
    text_Input.set("")
def btnEqualsInput():
    global operator
    sumup=str(eval(operator))
    text_Input.set(sumup)
    operator=""

root=Tk()
root.title("Calculator")
operator=""
text_Input = StringVar()
txtDislay=Entry(root,font=('arial',20,'bold'), textvariable=text_Input,bd=30,insertwidth=4,
                bg="burlywood1",justify='right',).grid(columnspan=4)
btn7=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="7",command=lambda : btnClick(7),bg="gray").grid(row=1,column=0)
btn8=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="8",command=lambda : btnClick(8),bg="gray").grid(row=1,column=1)
btn9=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="9",command=lambda : btnClick(9),bg="gray").grid(row=1,column=2)
Addition=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="+",command=lambda : btnClick("+"),bg="gray").grid(row=1,column=3)

btn4=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="6",command=lambda : btnClick(4),bg="gray").grid(row=2,column=0)
btn5=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="6",command=lambda : btnClick(5),bg="gray").grid(row=2,column=1)
btn6=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="6",command=lambda : btnClick(6),bg="gray").grid(row=2,column=2)
Subtraction=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="-",command=lambda : btnClick("-"),bg="gray").grid(row=2,column=3)


btn3=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="3",bg="gray",command=lambda : btnClick(3)).grid(row=3,column=0)
btn2=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="2",command=lambda : btnClick(2),bg="gray").grid(row=3,column=1)
btn1=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="1",command=lambda : btnClick(1),bg="gray").grid(row=3,column=2)
Multiplication=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="x",command=lambda : btnClick("*"),bg="gray").grid(row=3,column=3)

btn0=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="0",bg="gray",command=lambda : btnClick(0)).grid(row=4,column=0)
btnClear=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="C",bg="gray",command=btnClearDisplay).grid(row=4,column=1)
btnEquals=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="=",bg="gray",command=btnEqualsInput).grid(row=4,column=2)
Division=Button(root,padx=16,pady=16,bd=8,fg="black",font=('arial',20,'bold'),
            text="/",command=lambda : btnClick("/"),bg="gray").grid(row=4,column=3)
root.mainloop()
```

### Registration Form : 

```
from tkinter import *
root=Tk()
root.geometry("600x600")
root.title("Registration Form")
menu = Menu(root)
root.config(menu=menu)
filemenu = Menu(menu)
menu.add_cascade(label='File', menu=filemenu)
filemenu.add_command(label='New')
filemenu.add_command(label='Open...')
filemenu.add_separator()
filemenu.add_command(label='Exit', command=root.quit)
helpmenu = Menu(menu)
menu.add_cascade(label='Help', menu=helpmenu)
helpmenu.add_command(label='About')
def openNewWindow():
    newWindow=Toplevel(root)
    newWindow.title("New Window")
    newWindow.geometry("600x400")
    Label(newWindow,text="This is new Window").pack()
def getvals():
    print("Submitting form")
    print(f"{fname.get(),lname.get(),email.get(),var.get(),c.get(),var1.get(),var2.get(),var3.get()} ")

    with open("records.txt","a") as f: # use a for append and if write use w only
        f.write(f"{fname.get(),lname.get(),email.get(),var.get(),c.get(),var1.get(),var2.get(),var3.get()} \n")

lab1=Label(root,text="Registration Form",width=24,font=('bold',20)).place(x=95,y=55)
lab2=Label(root,text="First Name : ",width=24,font=('bold', 10)).place(x=85,y=140)
fname=StringVar()
entry1=Entry(root,textvariable=fname,width=30).place(x=245,y=140)
lab3=Label(root,text="Last Name : ",width=24,font=('bold' ,10)).place(x=85,y=180)
lname=StringVar()
entry2=Entry(root,textvariable=lname,width=30).place(x=245,y=180)
lab4=Label(root,text="Email : ",width=24,font=('bold',10)).place(x=70,y=220)
email=StringVar()
entry2=Entry(root,textvariable=email,width=30).place(x=245,y=220)
lab5=Label(root,text="Gender : " ,width=24,font=('bold',10)).place(x=72,y=260)
var=IntVar()
Radiobutton(root,text="Male",padx=7,variable=var,value=1,).place(x=235,y=260)
Radiobutton(root,text="Female",padx=7,variable=var,value=2,).place(x=300,y=260)
lab6=Label(root,text="Country : ",width=24,font=('bold', 10)).place(x=70,y=300)
list1=[    ('US', 'United States'),
    ('AF', 'Afghanistan'),
    ('AL', 'Albania'),
    ('DZ', 'Algeria'),
    ('AS', 'American Samoa'),
    ('AD', 'Andorra'),
    ('AO', 'Angola'),
    ('AI', 'Anguilla'),
    ('AQ', 'Antarctica'),
    ('AG', 'Antigua And Barbuda'),
    ('AR', 'Argentina'),
    ('AM', 'Armenia'),
    ('AW', 'Aruba'),
    ('AU', 'Australia'),
    ('AT', 'Austria'),
    ('AZ', 'Azerbaijan'),
    ('BS', 'Bahamas'),
    ('BH', 'Bahrain'),
    ('BD', 'Bangladesh'),
    ('BB', 'Barbados'),
    ('BY', 'Belarus'),
    ('BE', 'Belgium'),
    ('BZ', 'Belize'),
    ('BJ', 'Benin'),
    ('BM', 'Bermuda'),
    ('BT', 'Bhutan'),
    ('BO', 'Bolivia'),
    ('BA', 'Bosnia And Herzegowina'),
    ('BW', 'Botswana'),
    ('BV', 'Bouvet Island'),
    ('BR', 'Brazil'),
    ('BN', 'Brunei Darussalam'),
    ('BG', 'Bulgaria'),
    ('BF', 'Burkina Faso'),
    ('BI', 'Burundi'),
    ('KH', 'Cambodia'),
    ('CM', 'Cameroon'),
    ('CA', 'Canada'),
    ('CV', 'Cape Verde'),
    ('KY', 'Cayman Islands'),
    ('CF', 'Central African Rep'),
    ('TD', 'Chad'),
    ('CL', 'Chile'),
    ('CN', 'China'),
    ('CX', 'Christmas Island'),
    ('CC', 'Cocos Islands'),
    ('CO', 'Colombia'),
    ('KM', 'Comoros'),
    ('CG', 'Congo'),
    ('CK', 'Cook Islands'),
    ('CR', 'Costa Rica'),
    ('CI', 'Cote D`ivoire'),
    ('HR', 'Croatia'),
    ('CU', 'Cuba'),
    ('CY', 'Cyprus'),
    ('CZ', 'Czech Republic'),
    ('DK', 'Denmark'),
    ('DJ', 'Djibouti'),
    ('DM', 'Dominica'),
    ('DO', 'Dominican Republic'),
    ('TP', 'East Timor'),
    ('EC', 'Ecuador'),
    ('EG', 'Egypt'),
    ('SV', 'El Salvador'),
    ('GQ', 'Equatorial Guinea'),
    ('ER', 'Eritrea'),
    ('EE', 'Estonia'),
    ('ET', 'Ethiopia'),
    ('FK', 'Falkland Islands (Malvinas)'),
    ('FO', 'Faroe Islands'),
    ('FJ', 'Fiji'),
    ('FI', 'Finland'),
    ('FR', 'France'),
    ('GF', 'French Guiana'),
    ('PF', 'French Polynesia'),
    ('TF', 'French S. Territories'),
    ('GA', 'Gabon'),
    ('GM', 'Gambia'),
    ('GE', 'Georgia'),
    ('DE', 'Germany'),
    ('GH', 'Ghana'),
    ('GI', 'Gibraltar'),
    ('GR', 'Greece'),
    ('GL', 'Greenland'),
    ('GD', 'Grenada'),
    ('GP', 'Guadeloupe'),
    ('GU', 'Guam'),
    ('GT', 'Guatemala'),
    ('GN', 'Guinea'),
    ('GW', 'Guinea-bissau'),
    ('GY', 'Guyana'),
    ('HT', 'Haiti'),
    ('HN', 'Honduras'),
    ('HK', 'Hong Kong'),
    ('HU', 'Hungary'),
    ('IS', 'Iceland'),
    ('IN', 'India'),
    ('ID', 'Indonesia'),
    ('IR', 'Iran'),
    ('IQ', 'Iraq'),
    ('IE', 'Ireland'),
    ('IL', 'Israel'),
    ('IT', 'Italy'),
    ('JM', 'Jamaica'),
    ('JP', 'Japan'),
    ('JO', 'Jordan'),
    ('KZ', 'Kazakhstan'),
    ('KE', 'Kenya'),
    ('KI', 'Kiribati'),
    ('KP', 'Korea (North)'),
    ('KR', 'Korea (South)'),
    ('KW', 'Kuwait'),
    ('KG', 'Kyrgyzstan'),
    ('LA', 'Laos'),
    ('LV', 'Latvia'),
    ('LB', 'Lebanon'),
    ('LS', 'Lesotho'),
    ('LR', 'Liberia'),
    ('LY', 'Libya'),
    ('LI', 'Liechtenstein'),
    ('LT', 'Lithuania'),
    ('LU', 'Luxembourg'),
    ('MO', 'Macau'),
    ('MK', 'Macedonia'),
    ('MG', 'Madagascar'),
    ('MW', 'Malawi'),
    ('MY', 'Malaysia'),
    ('MV', 'Maldives'),
    ('ML', 'Mali'),
    ('MT', 'Malta'),
    ('MH', 'Marshall Islands'),
    ('MQ', 'Martinique'),
    ('MR', 'Mauritania'),
    ('MU', 'Mauritius'),
    ('YT', 'Mayotte'),
    ('MX', 'Mexico'),
    ('FM', 'Micronesia'),
    ('MD', 'Moldova'),
    ('MC', 'Monaco'),
    ('MN', 'Mongolia'),
    ('MS', 'Montserrat'),
    ('MA', 'Morocco'),
    ('MZ', 'Mozambique'),
    ('MM', 'Myanmar'),
    ('NA', 'Namibia'),
    ('NR', 'Nauru'),
    ('NP', 'Nepal'),
    ('NL', 'Netherlands'),
    ('AN', 'Netherlands Antilles'),
    ('NC', 'New Caledonia'),
    ('NZ', 'New Zealand'),
    ('NI', 'Nicaragua'),
    ('NE', 'Niger'),
    ('NG', 'Nigeria'),
    ('NU', 'Niue'),
    ('NF', 'Norfolk Island'),
    ('MP', 'Northern Mariana Islands'),
    ('NO', 'Norway'),
    ('OM', 'Oman'),
    ('PK', 'Pakistan'),
    ('PW', 'Palau'),
    ('PA', 'Panama'),
    ('PG', 'Papua New Guinea'),
    ('PY', 'Paraguay'),
    ('PE', 'Peru'),
    ('PH', 'Philippines'),
    ('PN', 'Pitcairn'),
    ('PL', 'Poland'),
    ('PT', 'Portugal'),
    ('PR', 'Puerto Rico'),
    ('QA', 'Qatar'),
    ('RE', 'Reunion'),
    ('RO', 'Romania'),
    ('RU', 'Russian Federation'),
    ('RW', 'Rwanda'),
    ('KN', 'Saint Kitts And Nevis'),
    ('LC', 'Saint Lucia'),
    ('VC', 'St Vincent/Grenadines'),
    ('WS', 'Samoa'),
    ('SM', 'San Marino'),
    ('ST', 'Sao Tome'),
    ('SA', 'Saudi Arabia'),
    ('SN', 'Senegal'),
    ('SC', 'Seychelles'),
    ('SL', 'Sierra Leone'),
    ('SG', 'Singapore'),
    ('SK', 'Slovakia'),
    ('SI', 'Slovenia'),
    ('SB', 'Solomon Islands'),
    ('SO', 'Somalia'),
    ('ZA', 'South Africa'),
    ('ES', 'Spain'),
    ('LK', 'Sri Lanka'),
    ('SH', 'St. Helena'),
    ('PM', 'St.Pierre'),
    ('SD', 'Sudan'),
    ('SR', 'Suriname'),
    ('SZ', 'Swaziland'),
    ('SE', 'Sweden'),
    ('CH', 'Switzerland'),
    ('SY', 'Syrian Arab Republic'),
    ('TW', 'Taiwan'),
    ('TJ', 'Tajikistan'),
    ('TZ', 'Tanzania'),
    ('TH', 'Thailand'),
    ('TG', 'Togo'),
    ('TK', 'Tokelau'),
    ('TO', 'Tonga'),
    ('TT', 'Trinidad And Tobago'),
    ('TN', 'Tunisia'),
    ('TR', 'Turkey'),
    ('TM', 'Turkmenistan'),
    ('TV', 'Tuvalu'),
    ('UG', 'Uganda'),
    ('UA', 'Ukraine'),
    ('AE', 'United Arab Emirates'),
    ('UK', 'United Kingdom'),
    ('UY', 'Uruguay'),
    ('UZ', 'Uzbekistan'),
    ('VU', 'Vanuatu'),
    ('VA', 'Vatican City State'),
    ('VE', 'Venezuela'),
    ('VN', 'Viet Nam'),
    ('VG', 'Virgin Islands (British)'),
    ('VI', 'Virgin Islands (U.S.)'),
    ('EH', 'Western Sahara'),
    ('YE', 'Yemen'),
    ('YU', 'Yugoslavia'),
    ('ZR', 'Zaire'),
    ('ZM', 'Zambia'),
    ('ZW', 'Zimbabwe')]
c=StringVar()
droplist=OptionMenu(root,c,*list1)
droplist.config(width=25)
c.set('Select your Country')
droplist.place(x=240,y=295)
lab7=Label(root,text="Programming : ",width=24,font=('bold',10)).place(x=85,y=340)
var1=IntVar()
Checkbutton(root,text="Java",variable=var1,bg="snow").place(x=235,y=340)
var2=IntVar()
Checkbutton(root,text="Python",variable=var2,bg="snow").place(x=290,y=340)
var3=IntVar()
Checkbutton(root,text="C++",variable=var3,bg="snow").place(x=360,y=340)
Button(root,text="Submit",width=24,bg="gray",fg="white",command=getvals).place(x=200,y=380)
mainloop()
```

### Quiz base application
```
from tkinter import *
import os
from PIL import ImageTk,Image
import random
import json

def delete3():
    screen4.destroy()


def delete4():
    screen5.destroy()


with open('./data.json', encoding="utf8") as f:
    data = json.load(f)

questions = [v for v in data[0].values()]
answers_choice = [v for v in data[1].values()]

answers = [1, 2, 1, 1, 3, 1, 0, 1, 3, 3]

user_answer = []


def Res():
    print("Score List")
    uid_info=uid.get()
    score_info=score.get()
    file = open(uid_info, "w")
    file.write(uid_info+" "+score_info+"\n")
    file.close()

indexes = []

def gen():
    global indexes
    while (len(indexes) < 5):
        x = random.randint(0, 9)
        if x in indexes:
            continue
        else:
            indexes.append(x)


def showresult(score):
    lblQuestion.destroy()
    r1.destroy()
    r2.destroy()
    r3.destroy()
    r4.destroy()
    labelimage = Label(
        screen6,
        background="#ffffff",
        border=0,
    )
    labelimage.pack(pady=(50, 30))
    labelresulttext = Label(
        screen6,
        font=("Consolas", 20),
        background="#ffffff",
    )
    Label(screen6,bg="black",width=250,height=5).place(x=0,y=0)
    Label(screen6,bg="snow",width=10,height=250).pack(side=LEFT)
    Label(screen6,bg="snow",width=10,height=250).pack(side=RIGHT)
    Label(screen6,bg="black",width=250,height=5).pack(side=BOTTOM)
    labelresulttext.pack()
    if score >= 20:
        labelresulttext.configure(text="You Are Excellent !!",bg=None,fg="red",font=('arial', 30, 'bold'))
        Label(screen6,text=("Your score : "+str(score)),fg="red",bg=None,font=('arial', 40, 'bold'),justify=CENTER).pack()
    elif (score >= 10 and score < 20):
        labelresulttext.configure(text="You Can Be Better !!",bg=None,fg="red",font=('arial', 30, 'bold'))
        Label(screen6,text=("Your score : "+str(score)),fg="red",bg=None,font=('arial', 40, 'bold'),justify=CENTER).pack()
    else:
        labelresulttext.configure(text="You Should Work Hard !!",bg=None,fg="red",font=('arial', 30, 'bold'))
        Label(screen6,text=("Your score : "+str(score)),fg="red",bg=None,font=('arial', 40, 'bold'),justify=CENTER).pack()

def calc():
    global indexes, user_answer, answers,score
    x = 0
    score = 0
    for i in indexes:
        if user_answer[x] == answers[i]:
            score = score + 5
        x += 1
    print(score)
    showresult(score)


ques = 1


def selected():
    global radiovar, user_answer
    global lblQuestion, r1, r2, r3, r4
    global ques
    x = radiovar.get()
    user_answer.append(x)
    radiovar.set(-1)
    if ques < 5:
        lblQuestion.config(text=questions[indexes[ques]])
        r1['text'] = answers_choice[indexes[ques]][0]
        r2['text'] = answers_choice[indexes[ques]][1]
        r3['text'] = answers_choice[indexes[ques]][2]
        r4['text'] = answers_choice[indexes[ques]][3]
        ques += 1
    else:
        calc()



def startquiz():
    global screen6
    screen6 = Toplevel(screen)
    screen6.config(bg="snow")
    screen6.geometry("1200x800")
    global lblQuestion, r1, r2, r3, r4
    screen6.iconbitmap("img.ico")


    lblQuestion = Label(
        screen6,
        text=questions[indexes[0]],
        font=("Consolas", 25,'bold'),
        width=500,
        justify="center",
        wraplength=400,
        background="#ffffff",
    )
    lblQuestion.pack(pady=(100, 30))

    global radiovar
    radiovar = IntVar()
    radiovar.set(-1)

    r1 = Radiobutton(
        screen6,
        text=answers_choice[indexes[0]][0],
        font=('arial', 25, 'bold'),
        value=0,
        variable=radiovar,
        command=selected,
        background="#ffffff",
    )
    r1.pack(pady=5)

    r2 = Radiobutton(
        screen6,
        text=answers_choice[indexes[0]][1],
        font=('arial', 25, 'bold'),
        value=1,
        variable=radiovar,
        command=selected,
        background="#ffffff",
    )
    r2.pack(pady=5)

    r3 = Radiobutton(
        screen6,
        text=answers_choice[indexes[0]][2],
        font=('arial', 25, 'bold'),
        value=2,
        variable=radiovar,
        command=selected,
        background="#ffffff",
    )
    r3.pack(pady=5)

    r4 = Radiobutton(
        screen6,
        text=answers_choice[indexes[0]][3],
        font=('arial', 25, 'bold'),
        value=3,
        variable=radiovar,
        command=selected,
        background="#ffffff",
    )
    r4.pack(pady=5)


def startIspressed():
    gen()
    startquiz()
    countDown()


def login_sucess():
    global screen3
    screen3 = Toplevel(screen)
    screen3.title("Quiz Start")
    screen3.geometry("1200x800")
    screen3.iconbitmap("img.ico")
    lblInstruction = Label(
        screen3,
        text="Read The Rules And\nClick Start Once You Are ready",
        background="#ffffff",
        font=("Consolas", 14),
        justify="center",
    )
    lblInstruction.pack(pady=(10, 100))
    btnStart = Button(screen3, text="Start Quiz", width=24, height=1, bg="gray", borderwidth=15, relief=SUNKEN,
                      fg="#FACA2F", padx=5, pady=5, font=('arial', 10, 'bold'), command=startIspressed)
    btnStart.place(x=650,y=400)
    Label(screen3,text="Are you ready for Quiz",bg=None,fg="#FACA2F",font=('arial', 20, 'bold')).place(x=615,y=350)
    lblRules = Label(
        screen3,
        text="This quiz contains 10 questions\nYou will get 20 seconds to solve a question\nOnce you select a radio button that will be a final choice\nhence think before you select",
        width=155,
        font=("Times", 14),
        background="#000000",
        foreground="#FACA2F",
    )
    lblRules.pack(side=BOTTOM)


def password_not_recognised():
    global screen4
    screen4 = Toplevel(screen)
    screen4.title("Success")
    screen4.geometry("150x100")
    Label(screen4, text="Password Error").pack()
    Button(screen4, text="OK", command=delete3).pack()

def user_not_found():
    global screen5
    screen5 = Toplevel(screen)
    screen5.title("Success")
    screen5.geometry("150x100")
    Label(screen5, text="User Not Found").pack()
    Button(screen5, text="OK", command=delete4).pack()


def register_user():
    print("working")

    email_info = email.get()
    password_info = password.get()
    name_info=name.get()
    uid_info=uid.get()
    file = open(email_info, "w")
    file.write(email_info + "\n")
    file.write(password_info+"\n")
    file.write(name_info+"\n")
    file.write(uid_info+"\n")
    file.close()
    email_entry.delete(0, END)
    password_entry.delete(0, END)
    name_entry.delete(0,END)
    uid_entry.delete(0,END)


    Label(screen1, text="Registration Sucess", fg="green", font=("calibri", 11)).place(x=750,y=670)


def login_verify():
    email1 = email_verify.get()
    password1 = password_verify.get()
    email_entry1.delete(0, END)
    password_entry1.delete(0, END)

    list_of_files = os.listdir()
    if email1 in list_of_files:
        file1 = open(email1, "r")
        verify = file1.read().splitlines()
        if password1 in verify:
            login_sucess()
        else:
            password_not_recognised()

    else:
        user_not_found()


def register():
    global screen1
    screen1 = Toplevel(screen)
    screen1.title("Register")
    screen1.geometry("1200x800")
    screen1.iconbitmap("img.ico")
    screen1.config(bg="peach puff")
    def button_hover(e):
        my_button1["bg"] = "orange"
    def button_hover_leave(e):
        my_button1["bg"] = "black"
    global email
    global password
    global name
    global uid
    global name_entry
    global uid_entry
    global email_entry
    global password_entry
    global font1
    font1=('open sans',10,'bold')
    email = StringVar()
    password = StringVar()
    name=StringVar()
    uid=StringVar()
    Label(screen1,bg="black",width=250,height=5).place(x=0,y=0)
    Label(screen1,bg="light blue",width=10,height=250).pack(side=LEFT)
    Label(screen1,bg="light blue",width=10,height=250).pack(side=RIGHT)
    Label(screen1,bg="black",text="Register only once",fg="gold",font=('arial',20,'bold'),width=250,height=3).pack(side=BOTTOM)
    Label(screen1, text="Please enter details below",fg="red",bg=None,relief=SUNKEN,font=('arial', 20, 'bold')).place(x=600,y=155)
    Label(screen1,text="Name : ",borderwidth=15,width=10,relief=SUNKEN,font=('arial', 20, 'bold')).place(x=500,y=200)
    name_entry=Entry(screen1,textvariable=name, width=50, bd=5,font=font1, insertwidth=4,borderwidth=15,relief=SUNKEN, bg="snow",justify="center")
    name_entry.place(x=720,y=202)
    Label(screen1,text="Uid : ",borderwidth=15,width=10,relief=SUNKEN,font=('arial', 20, 'bold')).place(x=500,y=300)
    uid_entry=Entry(screen1,textvariable=uid, width=50, bd=5,font=font1, insertwidth=4,borderwidth=15,relief=SUNKEN, bg="snow",justify="center")
    uid_entry.place(x=720,y=302)
    Label(screen1, text="Email : ",borderwidth=15,width=10,relief=SUNKEN,font=('arial', 20, 'bold')).place(x=500,y=400)
    email_entry = Entry(screen1,textvariable=email, width=50, bd=5,font=font1, insertwidth=4,borderwidth=15,relief=SUNKEN, bg="snow",justify="center")
    email_entry.place(x=720,y=402)
    Label(screen1, text="Password : ",borderwidth=15,width=10,relief=SUNKEN,font=('arial', 20, 'bold')).place(x=500,y=500)
    password_entry = Entry(screen1,textvariable=password, width=50, bd=5,font=font1, insertwidth=4,borderwidth=15,relief=SUNKEN, bg="snow",justify="center",show="*")
    password_entry.place(x=720,y=502)
    my_button1=Button(screen1, text="Register", width=24, height=1, bg="gray",borderwidth=15,relief=SUNKEN, fg="white", padx=5, pady=5, font=('arial', 10, 'bold'), command=register_user)
    my_button1.place(x=700,y=602)
    my_button1.bind("<Enter>",button_hover)
    my_button1.bind("<Leave>",button_hover_leave)

def login():
    global screen2
    screen2 = Toplevel(screen)
    screen2.title("Login")
    screen2.geometry("1200x800")
    screen2.iconbitmap("img.ico")
    Label(screen2, text="Please enter details below to login",fg="red",bg=None,font=('arial', 15, 'bold')).place(x=650,y=160)
    screen2.config(bg="light cyan")
    global  email_verify
    global password_verify

    email_verify = StringVar()
    password_verify = StringVar()
    global email_entry1
    global password_entry1
    def button_hover(e):
        my_button1["bg"] = "orange"
    def button_hover_leave(e):
        my_button1["bg"] = "black"
    font2=('open sans',10,'bold')
    Label(screen2,bg="black",width=250,height=5).place(x=0,y=0)
    Label(screen2,bg="snow4",width=10,height=250).pack(side=LEFT)
    Label(screen2,bg="snow4",width=10,height=250).pack(side=RIGHT)
    Label(screen2,bg="black",width=250,height=5).pack(side=BOTTOM)
    Label(screen2, text="Email : ",borderwidth=15,width=9,relief=SUNKEN,font=('arial', 20, 'bold')).place(x=500,y=200)
    email_entry1 = Entry(screen2, width=50, bd=5, insertwidth=4,font=font2, bg="snow",borderwidth=15,relief=SUNKEN,justify="center", textvariable=email_verify)
    email_entry1.place(x=700,y=205)
    Label(screen2, text="Password : ",borderwidth=15,relief=SUNKEN,font=('arial', 20, 'bold')).place(x=500,y=300)
    password_entry1 = Entry(screen2, width=50, bd=5, insertwidth=4,font=font2,show="*",bg="snow",borderwidth=15,relief=SUNKEN,justify="center", textvariable=password_verify)
    password_entry1.place(x=700,y=305)
    my_button1=Button(screen2, text="Login",  width=24, height=1, bg="gray",borderwidth=15,relief=SUNKEN, fg="white", padx=5, pady=5, font=('arial', 10, 'bold'),command=login_verify)
    my_button1.place(x=700,y=400)
    my_button1.bind("<Enter>",button_hover)
    my_button1.bind("<Leave>",button_hover_leave)


def main_screen():
    global screen
    def button_hover(e):
        my_button1["bg"] = "orange"
    def button_hover_leave(e):
        my_button1["bg"] = "white"

    def button_hover_1(e):
        my_button2["bg"] = "orange"

    def button_hover_leave_1(e):
        my_button2["bg"] = "white"

    def button_hover3(e):
        Low["bg"] = "red"

    def button_hover_leave3(e):
        Low["bg"] = "black"

    screen = Tk()
    screen.geometry("1200x800")
    screen.config(bg="green4")
    screen.title("Quiz")
    screen.iconbitmap("img.ico")
    img=ImageTk.PhotoImage(Image.open("img3.jpg"))
    lab = Label(image=img,bg=None)
    lab.place(x=650,y=50)
    my_button1=Button(text="Login", height="2", width="25", bg="white",borderwidth=15,relief=SUNKEN, fg="black", padx=5, pady=5, font=('arial', 15, 'bold'), command=login)
    my_button1.place(x=595,y=300)
    my_button2=Button(text="Register", height="2", width="25", bg="white",borderwidth=15,relief=SUNKEN, fg="black", padx=5, pady=5, font=('arial', 15, 'bold'), command=register)
    my_button2.place(x=595,y=450)
    my_button1.bind("<Enter>",button_hover)
    my_button1.bind("<Leave>",button_hover_leave)
    my_button2.bind("<Enter>",button_hover_1)
    my_button2.bind("<Leave>",button_hover_leave_1)
    Label(bg="gold4",width=250,height=2).pack(side=TOP)
    Label(bg="snow",width=10,height=60).pack(side=LEFT)
    Label(bg="snow",width=10,height=60).pack(side=RIGHT)
    Low=Label(text="Click on register button if not registered else press login",bg="black",width=100,height=4,fg="white", font=('arial', 25, 'bold'))
    Low.pack(side=BOTTOM)
    Low.bind("<Enter>",button_hover3)
    Low.bind("<Leave>",button_hover_leave3)
    screen.mainloop()


main_screen()
```
