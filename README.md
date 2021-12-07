# python_fall2021
#python class
#Amy Ollomani and Sharron Tum
#Final Project

import turtle
import random

wn = turtle.Screen()
tess = turtle.Turtle()


tess.speed(50)


phraselst = ["santa claus", "hanukkah", "christmas", "coal", "present", "menorah", "dreidel", "kwanzaa", "rudolph", "reindeer"]
phrase = random.choice(phraselst)

dictx = {"1x":-580,"2x": -420,"3x": -260,"4x": -100,"5x": 60,"6x": 220,"7x": 380,"8x": 540,"9x": -580,"10x": -420,"11x": -260,"12x":-100,"13x": 60,"14x": 220,"15x": 380,"16x": 540}

dicty = {"1y":0,"2y": 0,"3y": 0,"4y": 0,"5y": 0,"6y": 0,"7y": 0,"8y": 0,"9y": -160,"10y": -160,"11y": -160,"12y": -160,"13y": -160,"14y": -160,"15y": -160,"16y": -160}

wronglst = []



#Draws out each line for each character
def character(n):
    tess.penup()
    tess.goto(-600,0)
    count = 0
    char1 = 0
    for char in n:
        if char!= " ":
            tess.pendown()
            tess.forward(80)
            tess.penup()
            tess.forward(80)
            if char1 == 7:
                tess.goto(-600,-150)
            if char1 ==15:
                tess.goto(-600,-300)
                
            char1+=1
        if char == " ":
            tess.forward(160)
            if char1 == 7:
                tess.goto(-600,-150)
            if char == 15:
                 tess.goto(-600,-300)
            char1+= 1


#draws out board
def pole():
    tess.penup()
    tess.goto(-400,100)
    tess.left(90)
    tess.pendown()
    tess.forward(250)
    tess.left(90)
    tess.forward(100)
    tess.left(90)
    tess.forward(30)
    tess.right(270)



def guess1(wordlst):
    count = 0
    wrong = 0
    tess.penup()
    count1=0

    for elm in wordlst:
        count+=1
    while True:
        guess = str(input("Guess character: "))
        if guess in wordlst:
            count
            for i in wordlst:
                count1+=1
                if guess ==i:
                    keyx = str(count1) + "x"
                    x = dictx[keyx]
                    tess.goto(x,0)
                    tess.pendown()
                    tess.write(guess, font=("Arial", 60, "normal"))
                    correct = 1
                    tess.penup()
                    count1=0
        if correct == count:
            tess.goto(100,280)
            tess.color('green')
            tess.write("You WON!!!!!", font=("Arial", 60, "normal"))
        if guess not in wordlst:
            wrong+=1
            if wrong == 1:
                head()
                print(wrong)
            elif wrong == 2:
                body()
                print(wrong)
            elif wrong == 3:
                leftleg()
                print(wrong)
            elif wrong == 4:
                rightleg()
                print(wrong)
            elif wrong == 5:
                rightarm()
                print(wrong)
            elif wrong == 6:
                leftarm()
                print(wrong)
            elif wrong == 7:
                tess.goto(100, 280)
                tess.color('red')
                tess.write("You LOSEEEE!!!!!!!", font=("Arial", 60, "normal"))

                
            
            
                
                


        
    


#returns whether user's guess was incorrect or correct
                    
                 
def head():
    tess.penup()
    tess.goto(-500, 280)
    tess.pendown()
    tess.circle(20)
    tess.penup()

 
def body():
    tess.goto(-500, 280)
    tess.right(90)
    tess.pendown()
    tess.forward(100)
    tess.penup()

def leftleg():
    tess.goto(-500, 180)
    tess.right(45)
    tess.pendown()
    tess.forward(50)
    tess.penup()

def rightleg():
    tess.goto(-500, 180)
    tess.pendown()
    tess.left(90)
    tess.forward(50)
    tess.penup()
    

def rightarm():
    tess.penup()
    tess.goto(-500, 250)
    tess.left(45)
    tess.pendown()
    tess.forward(50)
    tess.penup()
 
def leftarm():
    tess.penup()
    tess.goto(-500, 250)
    tess.left(180)
    tess.pendown()
    tess.forward(50)
    tess.penup()

def main():
    pole()
    n = random.choice(phraselst)
    character(n)
    wordlst = list(n)   
    guess1(wordlst)
        


main()










