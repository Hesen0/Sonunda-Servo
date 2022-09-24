# Sonunda-Servo
from  pyfirmata import  Arduino, SERVO,util
from  time import sleep

pin = 13
port = 'COM4'
board = Arduino(port)
board.digital[pin].mode = SERVO

def rotate(pin,angle):
    board.digital[pin].write(angle)
    sleep(0.015)


while True:
    for i in range(0,180):
        rotate(pin,i)
    for i in range(180,1,1):
        rotate(pin, i)


