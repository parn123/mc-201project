# mc-201project
code
import random
import pyautogui
import string
import time

chars = string.printable
chars_list =string.ascii_lowercase + string.digits

password = pyautogui.password("Enter a password : ")
start_time = time.time()
guess_password = ""
guess_list=[]
attempts=0
while(guess_password != password):
    guess_password = random.choices(chars_list, k=len(password))
    if (guess_password in guess_list):
        continue
    guess_list.append(guess_password)
    print("<=================="+ str(guess_password)+ "==================>")
    attempts=attempts+1
    if(guess_password == list(password)):
        print("Your password is : "+ "".join(guess_password))
        print("attempts:- ",attempts)
        print("--- %s seconds ---" % (time.time() - start_time))
        print("speed=",attempts/(time.time() - start_time))
        break
