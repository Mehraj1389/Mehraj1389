import turtle
import random
score=0
s=turtle.Screen()
s.setup(600,600)
s.title('بازي لاکپشت')
s.bgcolor('lightgreen')
#ترسيم ديوار
wall=turtle.Turtle()
wall.up()
wall.goto(-275,275)
wall.down()
wall.width(4)
for i in range(4):
    wall.fd(550)
    wall.rt(90)
wall.ht()
#ايجاد شخصيت بازي
laki=turtle.Turtle()
laki.shape('turtle')
laki.color('darkgreen')
laki.shapesize(2)
laki.up()
#ايجاد شخصيت توپ
ball=turtle.Turtle()
ball.shape('circle')
ball.color('red')
ball.up()
ball.goto(random.randint(-260.260),random.randint(-260.260))
#ايجاد امتياز
wr=turtle.Turtle()
wr.up()
wr.goto(-270.270)
wr.ht()
wr.color('navy')
wr.write('امتياز'+str(score),font=('b koodak',12,'blod'))
#توابع حرکت با کيبورد
def move_right():
    laki.right(30)
def move_left():
    laki.left(30)
s.listen()
s.onkey(move_right,'Right')
s.onkey(move_left,'Left')
#حرکت مداوم
while True:
    laki.fd(1)
    if laki.xcor()>270 or laki.xcor()<-270 or laki.ycor()>270 or laki.ycor()<-270:
        laki.right(180)
        score=score-5
        wr.clear()
        wr.write('امتياز'+str(score),font=('b koodak',12,'blod'))
    if laki.distance(ball)<15:
        ball.goto(random.randint(-260.260),random.randint(-260.260))
        score=score+10
        wr.clear()
        wr.write('امتياز'+str(score),font=('b koodak',12,'blod'))
