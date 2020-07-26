<h1 align=center><b>Project Python</b></h1>

<p align=center><b><i>My Projects</i></b></p>

<p style="color: green"> Check below to get the codes</p>

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
