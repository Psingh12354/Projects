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
