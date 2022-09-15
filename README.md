# Python_Exercise07
## 7. Tuple, set, and dictionary

1. Write a program that asks the user for a number of a month and then prints out the corresponding season (`spring`, 
`summer`, `autumn`, `winter`). Save the seasons as strings into a tuple in your program. We can define each season to
last three months, December being the first month of winter.
```python
season = ("Spring", "Summer", "Autumn", "Winter")
month = ([3, 4, 5], [6, 7, 8], [9, 10, 11], [12, 1, 2])
inputNum = int(input("Input a month in number (1..12:) "))
for i in range(len(month)):
    if inputNum in month[i]:
        print(season[i])
        break
```
Output console:
```
Input a month in number (1..12:) 9
Autumn
```
2. Write a program that asks the user to enter names. After each name is read the program either prints out `New name` or
`Existing name` depending on whether the name was entered for the first time. Finally, the program lists out the input names
one by one, one below another in any order. Use the set data structure to store the names.
```python
nameSet = set()
tmpList = []
print("Input 5 names, please!")
i = 1
while i <= 5:
    nameInput = input(f"Name {i}: ")
    if nameInput not in nameSet:
        tmpList.append(nameInput)
        nameSet.update(tmpList)
        print("New name")
        i += 1
    else:
        print("Existing name")
for i in nameSet:
    print(i)
```
Output console:
```
Input 5 names, please!
Name 1: mong
New name
Name 2: mong
Existing name
Name 2: khai
New name
Name 3: xuan
New name
Name 4: trang
New name
Name 5: minh
New name
xuan
khai
mong
trang
minh
```
3. Write a program for fetching and storing airport data. The program asks the user if they want to enter a new airport, fetch
the information of an existing airport or quit. If the user chooses to enter a new airport, the program asks the user to enter
the ICAO code and name of the airport. If the user chooses to fetch airport information instead, the program asks for the ICAO
code of the airport and prints out the corresponding name. If the user chooses to quit, the program execution ends. The user can
choose a new option as many times they want until they choose to quit. (The ICAO code is an identifier that is unique to each
airport. For example, the ICAO code of Helsinki-Vantaa Airport is EFHK. You can easily find the ICAO codes of different airports online.)
https://www.airport-data.com/world-airports/countries/FI-Finland-Airports.html
```python
dashboard = {}
print("Choose what you want to do:")
print("n: add new airport")
print("f: fetch airport name")
print("ENTER to quit program")
query = input()
while query == "n" or query == "f":
    if query == "n":
        newIcao = input("input ICAO code: ")
        newName = input("input name of airport: ")
        dashboard.update({newIcao: newName})
    else:
        icao = input("input ICAO code: ")
        if icao in dashboard:
            print("Airport name:", dashboard[icao])
        else:
            print("Airport not found")
    print("Choose what you want to do:")
    print("n: add new airport")
    print("f: fetch airport name")
    print("ENTER to quit program")
    query = input()
print("Thank you! Bye!")
```
Output console:
```
Choose what you want to do:
n: add new airport
f: fetch airport name
ENTER to quit program
f
input ICAO code: EFHK
Airport not found
Choose what you want to do:
n: add new airport
f: fetch airport name
ENTER to quit program
n
input ICAO code: EFHK
input name of airport: Helisinki-Vantaa airport
Choose what you want to do:
n: add new airport
f: fetch airport name
ENTER to quit program
n
input ICAO code: EFPO
input name of airport: Pori Airport
Choose what you want to do:
n: add new airport
f: fetch airport name
ENTER to quit program
n
input ICAO code: EFTU
input name of airport: 	Turku Airport
Choose what you want to do:
n: add new airport
f: fetch airport name
ENTER to quit program
n
input ICAO code: EFVA
input name of airport: 	Vaasa Airport
Choose what you want to do:
n: add new airport
f: fetch airport name
ENTER to quit program
f
input ICAO code: EFHK
Airport name: Helisinki-Vantaa airport
Choose what you want to do:
n: add new airport
f: fetch airport name
ENTER to quit program
f
input ICAO code: EFVA
Airport name: 	Vaasa Airport
Choose what you want to do:
n: add new airport
f: fetch airport name
ENTER to quit program
f
input ICAO code: EFTU
Airport name: 	Turku Airport
Choose what you want to do:
n: add new airport
f: fetch airport name
ENTER to quit program
f
input ICAO code: EFLP
Airport not found
Choose what you want to do:
n: add new airport
f: fetch airport name
ENTER to quit program

Thank you! Bye!
```
