# turtle_race

from turtle import Turtle, Screen
import random
screen=Screen()
screen.setup(width=500, height=400)
user_bet=screen.textinput(title="make your bet", prompt="which turtle will win the race? Enter a colour: ")
colors=["red","orange","yellow","green","blue","purple","brown","pink","green","grey"]
Y_position=[-70,-50,-20,20,50,70,120,90,-100,-130,150]
all_turtle=[]
for turtle_index in range (1,8):
    new_turtle=Turtle(shape="turtle")
    new_turtle.penup()
    new_turtle.color(colors[turtle_index])

    new_turtle.goto(x=-230, y=Y_position[turtle_index])
    all_turtle.append(new_turtle)

if user_bet:
    is_race_on=True
while is_race_on:
    for turtle in all_turtle:
        if turtle.xcor()>230:
            is_race_on=False
            winning_color=turtle.pencolor()
            if winning_color==user_bet:
                print(f"you've won! The {winning_color} turtle is the winner! enjoy")
            else:
                print(f"You've lose! the {winning_color} turtle is the winner!")
        rand_distance=random.randint(0,10)
        turtle.forward(rand_distance)



screen.exitonclick()
