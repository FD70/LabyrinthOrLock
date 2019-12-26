from PIL import Image
import subprocess, os, pyautogui, time


fd70 = Image.open('startPoint.jpg')
WHITE = (240, 240, 240)


def lock():
    subprocess.check_output('rundll32.exe user32.dll, LockWorkStation')


def cursorPoint():
    while True:
        x, y = 0,0
        check = pyautogui.locateOnScreen(fd70, confidence=0.95)
        if (check is not None):
            x,y = check[0], check[1]
            return (x+5,y-5)

 
def mainLoop():
    while True:
        x = pyautogui.position()[0]
        y = pyautogui.position()[1]
        if (pyautogui.pixel(x,y) <= WHITE):
            lock()
            break
            
        
os.startfile(r'fd70.jpg')

pyautogui.moveTo(cursorPoint())
time.sleep(0.2)

mainLoop()


