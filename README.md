# turtle-hangman
import random
import turtle

#Function to draw wrong guesses
def draw_hangman(incorrect_count):
    if incorrect_count == 1:
        turtle.setpos(-75, 55)
        turtle.down()
        turtle.circle(10)
        turtle.up()
    if incorrect_count ==2:   
        turtle.setpos(-75, 55)
        turtle.seth(270)
        turtle.down()
        turtle.forward(30)
        turtle.up()
    if incorrect_count == 3:
        turtle.setpos(-75,45) 
        turtle.seth(0)
        turtle.down()
        turtle.fd(15)
        turtle.up()
    if incorrect_count == 4:
        turtle.setpos(-75, 45)
        turtle.seth(180)
        turtle.down()
        turtle.fd(15)
        turtle.up()
    if incorrect_count == 5:
        turtle.setpos(-75, 25)
        turtle.seth(285)
        turtle.down()
        turtle.fd(20)
        turtle.up()
    if incorrect_count == 6:
        turtle.setpos(-75, 25)
        turtle.seth(255)
        turtle.down()
        turtle.fd(20)
        turtle.up()

#draw the lines
def drawlines():
    #making the hanging area
    turtle.speed(0)
    turtle.ht()
    turtle.bk(50)
    turtle.up()
    turtle.fd(25)
    turtle.down()
    turtle.left(90)
    turtle.fd(100)
    turtle.left(90)
    turtle.fd(50)
    turtle.left(90)
    turtle.fd(25)
    turtle.up()
    turtle.fd(150)
    turtle.left(90)
    for i in range(len(random)):
        turtle.down()
        turtle.fd(10)
        turtle.up()
        turtle.fd(5)
    turtle.bk(len(random)*15)
    turtle.down()

written=0
attempt=0

def goodbye():
    turtle.textinput("Goodbye", "")

#Guessing
#select a random word
words = "rabbit rustle accomplice bite trauma aimless getaway downtown \
conversation exponential healthy terminal collapsing mustache ginger cathedral \
powerless bedtime insurance privilege".split()
num=random.randint(0, 19)
random = words[num]
drawlines()
while attempt<=5:
    guess=turtle.textinput("Guess!", "Enter the letter you are guessing:").lower()
    number_count=random.count(guess)
    #set up a way to determine if correct and write letter
    written=number_count
    if number_count > 0:
        for i in random:
            if guess==str(i):
                place = random.index(guess)
                xpos = (-75+(15*place))
                turtle.setpos(xpos, -75)
                turtle.down()
                turtle.write(guess)
                turtle.up()
                random=random.replace(str(i), " ", 1)
        if random ==(len(random)*' '):
            turtle.up()
            turtle.setpos(-75, -90)
            turtle.down()
            turtle.write("Congratulations!! You win!")
            goodbye()
    #draw body parts and count attempts
    elif number_count == 0:
        attempt+=1
        turtle.up()
        draw_hangman(attempt)   
turtle.up()
turtle.setpos(-75, -90)
turtle.down()
turtle.write("Sorry, you lose! :(")
goodbye()



        

       
    





    
