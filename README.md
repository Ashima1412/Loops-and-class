# Loops-and-class
#1 A Robot moves in a Plane starting from the origin point (0,0). The robot can move toward UP, DOWN, LEFT, RIGHT. The trace of Robot movement is as given following:
UP 5
DOWN 3
LEFT 3
RIGHT 2
The numbers after directions are steps. Write a program to compute the distance current position after sequence of movements.

Code:

import math

x, y = 0, 0

while True:
    moves = input('enter the directions: UP/DOWN/LEFT/RIGHT with steps count:  ')
   
    
    if(moves==''):
        break
    else:
         moves = moves.split(' ')
         if(moves[0] == 'UP'):
            x+=int(moves[1])
         if(moves[0] == 'DOWN'):
            x-=int(moves[1])
         if(moves[0] == 'LEFT'):
            y-=int(moves[1])
         if(moves[0] == 'RIGHT'):
            y+=int(moves[1])
            
dist = math.sqrt(x**2+y**2)
print('The distance is: ',dist)

Output:
enter the directions: UP/DOWN/LEFT/RIGHT with steps count:  UP 5
enter the directions: UP/DOWN/LEFT/RIGHT with steps count:  DOWN 3
enter the directions: UP/DOWN/LEFT/RIGHT with steps count:  LEFT 3
enter the directions: UP/DOWN/LEFT/RIGHT with steps count:  RIGHT 2
enter the directions: UP/DOWN/LEFT/RIGHT with steps count:  
The distance is:  2.23606797749979  



#2 Data of XYZ company is stored in sorted list. Write a program for searching specific data from that list.

Code:

list_xyz = ['bag','mug','jug','ball','bat']
list2 = sorted(list_xyz)
find = input('enter the item to be find: ')
if find in list2:
    print('Item {} is available!!'.format(find))
else:
    print('Item is not found')

Output:

enter the item to be find: bag
Item bag is available!!




#3 Weather forecasting organization wants to show is it day or night. So, write a program for such organization to find whether is it dark outside or not.

Code:

import time

time_check = time.localtime()
print(time_check)
if(time_check.tm_hour>18 and time_check.tm_hour<6):
    print('It is dark outside')
else:
    print('It is day outside')

Output:

time.struct_time(tm_year=2021, tm_mon=1, tm_mday=9, tm_hour=11, tm_min=8, tm_sec=10, tm_wday=5, tm_yday=9, tm_isdst=0)
It is day outside


#4 Write a program to find distance between two locations when their latitude and longitudes are given.

Code:

from math import radians, sin, cos, acos

print("Input coordinates of two points:")
slat = radians(float(input("Starting latitude: ")))
slon = radians(float(input("Ending longitude: ")))
elat = radians(float(input("Starting latitude: ")))
elon = radians(float(input("Ending longitude: ")))

dist = 6371.01 * acos(sin(slat)*sin(elat) + cos(slat)*cos(elat)*cos(slon - elon))
print("The distance is %.2fkm." % dist)

Output:

Input coordinates of two points:
Starting latitude: 22
Ending longitude: 53
Starting latitude: 24
Ending longitude: 62
The distance is 947.453611km.



#5 Design a software for bank system. There should be options like cash withdraw, cash credit and change password. According to user input, the software should provide required output.

Code:
def cash_withdraw():
        pin = int(input('enter your pin: '))
        if pin==142:
            print('You can withdraw the money')
        else:
            print('Please enter the valid pin!!')

def cash_credit():
        pin = int(input('enter your pin: '))
        if pin==142:
            cash = input('enter the money you want to deposit ')
            print('Money is successfully added!!!!')
        else:
            print('Please enter the valid pin!!')
            
def change_pwd():
        pin = int(input('enter your pin: '))
        if pin==142:
            pwd = input('Please enter the old password: ')
            print('You can change your password')
        else:
            print('You have entered the wrong password!!!!')
            
def bank():
    select = int(input('Enter your choice: 1. cash withdraw\n 2. cash credit\n 3. cahnge password'))
    if select==1:
        cash_withdraw()
    elif select==2:
        cash_credit()
    elif select==3:
        change_pwd()
    else:
        print('Please enter valid choice')

bank()

Output:

Enter your choice: 1. cash withdraw
 2. cash credit
 3. cahnge password2
enter your pin: 142
enter the money you want to deposit 2000
Money is successfully added!!!!




#6 Write a program which will find all such numbers which are divisible by 7 but are not a multiple of 5, between 2000 and 3200 (both included). The numbers obtained should be printed in a comma-separated sequence on a single line.

Code:
list1=[]
for i in range(2000,3201):
    if i%5!=0 and i%7==0:
        list1.append(str(i))
print(','.join(list1))


output:
2002,2009,2016,2023,2037,2044,2051,2058,2072,2079,2086,2093,2107,2114,2121,2128,2142,2149,2156,2163,2177,2184,2191,2198,2212,2219,2226,2233,2247,2254,2261,2268,2282,2289,2296,2303,2317,2324,2331,2338,2352,2359,2366,2373,2387,2394,2401,2408,2422,2429,2436,2443,2457,2464,2471,2478,2492,2499,2506,2513,2527,2534,2541,2548,2562,2569,2576,2583,2597,2604,2611,2618,2632,2639,2646,2653,2667,2674,2681,2688,2702,2709,2716,2723,2737,2744,2751,2758,2772,2779,2786,2793,2807,2814,2821,2828,2842,2849,2856,2863,2877,2884,2891,2898,2912,2919,2926,2933,2947,2954,2961,2968,2982,2989,2996,3003,3017,3024,3031,3038,3052,3059,3066,3073,3087,3094,3101,3108,3122,3129,3136,3143,3157,3164,3171,3178,3192,3199




#7 Write a program which can compute the factorial of a given numbers. Use recursion to find it.

Code:
def fact(n):
    if n==1:
        return n
    else:
        return n*fact(n-1)

num = int(input('enter the number: '))
if(num<0):
    print('cannot find the factorial ')
elif(num==0):
    print('The factorial of number is:  1')
else:
    print('The factorial of number is:  ',fact(num))

Output:
enter the number: 10
The factorial of number is:   3628800


#8 Write a program that calculates and prints the value according to the given formula:
Q = Square root of [(2 * C * D)/H]


Code:
import math
C=50
H=30

#Q = Square root of [(2 * C * D)/H]
str1 = input('enter values seperated with comma ')
nums = str1.split(',')
list1 = []
for D in nums:
    Q = round(math.sqrt((2*C*int(D))/H))
    list1.append(Q)

print('the values of Q are: ', list1)

Output:
enter values seperated with comma 100,150,180
the values of Q are:  [18, 22, 24]




#9 Write a program which takes 2 digits, X,Y as input and generates a 2-dimensional
array.

Code:

def arr(x,y):
    list1=[[0 for j in range(y)] for i in range(x)]
    
    for i in range(0,x):
        for j in range(0,y):
            list1[i][j] =  i*j
    print(list1)
arr(3,5)

Output:

[[0, 0, 0, 0, 0], [0, 1, 2, 3, 4], [0, 2, 4, 6, 8]]



#10 Write a program that accepts a comma separated sequence of words as input and
prints the words in a comma-separated sequence after sorting them alphabetically. 

Code:

str1=input('enter the words to be sorted with comma: ')
str2 = str1.split(',')
str3=[]
str2.sort()
print('The sorted words are: ',str2)

Output:

enter the words to be sorted with comma: mug,bag,jug,tag
The sorted words are:  ['bag', 'jug', 'mug', 'tag']




#11 Write a program that accepts sequence of lines as input and prints the lines after
making all characters in the sentence capitalized. 

Code:

str2=[]
while True:
    str1 = input('enter the sentences: ')
    if not str1:
        break
    str2.append(str1.upper())
#print(str2)
print('final result is: ', '\n'.join(str2))

Output:

enter the sentences: hello word
enter the sentences: practice makes perfect
enter the sentences: 
final result is:  HELLO WORD
PRACTICE MAKES PERFECT



#12 Write a program that accepts a sequence of whitespace separated words as input
and prints the words after removing all duplicate words and sorting them
alphanumerically

Code:

str1 = input('enter the sentence:  ')
x = str1.split(' ')
#str2 = ' '.join(reversed(str1))
str2 =[]

for i in x:
    if i not in str2:
        str2.append(i)
    else:
        continue
print(str2)
str2.sort()
print('final result is: ',(' ').join(str2))

Output:

enter the sentence:  hello world and practice makes perfect and hello world again
['hello', 'world', 'and', 'practice', 'makes', 'perfect', 'again']
final result is:  again and hello makes perfect practice world





#13 Write a program which accepts a sequence of comma separated 4 digit binary
numbers as its input and then check whether they are divisible by 5 or not. The
numbers that are divisible by 5 are to be printed in a comma separated sequence.\

Code:

num = input('enter 4 numbers with comma: ')
x=num.split(',')
str1 =[]
for i in x:
    y = int(i,2)
    #print(y)
    if not y%5:
        str1.append(i)
print(','.join(str1))

Output:

enter 4 numbers with comma: 0100,1010,0011,1001
1010




#14 Write a program that accepts a sentence and calculate the number of upper case
letters and lower case letters.

Code:

str1 = input('enter the string:  ')
count1=0
count2=0
count3=0
for i in str1:
    if i.isupper():
        count1+=1
    elif i.islower():
        count2+=1
    else:
        count3+=1
print('No of upper case letters are: ',count1)
print('No of lower case letters are: ',count2)
print('No of spaces are: ',count3)

Output: 

enter the string:  I am John
No of upper case letters are:  2
No of lower case letters are:  5
No of spaces are:  2


#15 Give example of fsum and sum function of math library

Code:

import math
print(math.fsum([1, 2, 3, 4, 5]))
print(math.fsum([1.7, 0.3, 1.5, 4.5]))
print(sum([1,2,3,4,5]))
print(sum([1,2,3,4,5],5)) #adding all no+5
print(sum([1.7,0.3,1.5,4.5]))
print(sum([1.7,0.3,1.5,4.5],5))  #adding all no+5

Output:

15.0
8.0
15
20
8.0
13.0

