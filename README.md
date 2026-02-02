# FInd-odd-or-evenimport random
import time


user_point = 0

com_point = 0

com_find = ["odd" , "even"]

start_cho = ["com" , "use"]

chance = 10

print("Welcome to my own game.You have total ten chances!!")

while chance>0:
    
    start = random.choice(start_cho)

    if start == "com":
        print("Its computer to start.")
        com_cho = random.randint(1,10)

        user_guess = input("What would you think, weather the computer choise is odd or even? ").lower()

        if com_cho % 2 == 0 and user_guess == 'even':
            print(f"Your choise is correct.The computer choise is {com_cho}")
            user_point += 1

        elif com_cho % 2 !=0 and user_guess == "odd":
            print(f"Your choise is correct.The computer choise is {com_cho}")
            user_point += 1

        else:
            print(f"You made the wrong guess.The computer choise is {com_cho}")
            com_point +=1
                
    elif start == "use":
        print("Its you to play.")

        user_cho = int(input("Choose a number between 1 and 10: "))

        com_cho = random.choice(com_find)

        if com_cho == "odd" and user_cho % 2 != 0:
            print(f"The computer found the correct number {user_cho}.You lose!!")
            com_point+=1

        elif com_cho == "even" and user_cho % 2 ==0:
            print(f"The computer found the correct number {user_cho}.You lose!!")
            com_point+=1

        else:
            print(f"The computer made the wrong guess.You won!!")
            user_point +=1

    chance-=1

print(f"Computer score is {com_point}")

print(f"Your score is {user_point}")

if user_point < com_point:
    print("You lose.The computer won!!")

elif user_point == com_point:
    print(f"match drawn.You both scored the same point {user_point}")

else:
    print("You won.The computer point is less than yours!!")

