# Hardware Store using Python

### As a capstone project at the end of my business programming course I led a team project to create a store using the pandas library. The project helps shoppers browse through departments, items, its price, and completes the purchase.

### The data created is stored in an Excel sheet. When importing the data its important to first set the directory to where the data is located on your device.

'#Hardware Store Team Project

#Function to greet the user and ask for a category

import pandas
storedf=pandas.read_csv("Team_DB.csv")
toolslist = list(storedf.Tools)
paintlist = list(storedf.Paint)
lumberlist = list(storedf.Lumber)
outdoorlist = list(storedf.Outdoor)
def greet_user(greeting,sentinel,categoryq,readyq):
    canswer = ' '
    ranswer = sentinel
    print(greeting)
    while ranswer == sentinel:
        canswer = input(categoryq)
        ranswer = input(readyq)
    if canswer == "Tools":
        tools("Welcome to our Tools section! Here are your choices:",toolslist,"Which type tool would you like or enter None? ")
    elif canswer == "Paint":
        paint("Welcome to our Paint section!  Here are your choices:",paintlist,"Which type of paint would you like or enter None? ")
    elif canswer == "Lumber":
        lumber("Welcome to our Lumber section!  Here are your choices:",lumberlist,"Which Lumber item would you like or enter None? ")
    elif canswer == "Outdoor":
        outdoor("Welcome to our Outdoor section!  Here are your choices:",outdoorlist,"Which Outdoor item would you like or enter None? ")    
    else:
        print('Sorry, we do not carry that category.  See you next time!')


#Function ask user to pick Tools
def tools(greeting,selection,pickq):
    print(greeting)
    for item in selection:
        print(item)
    toolspick = input(pickq)
    if toolspick == "None":
        print("Goodbye")
    elif toolspick == "Electric Saw":
        closing("Electric Saw",100,"Enjoy your Electric Saw!" )
    elif toolspick == "Chainsaw":
        closing("Chainsaw",90,"Enjoy your Chainsaw!" )
    elif toolspick == "Power Drill":
        closing("Power Drill",100,"Enjoy your Power Drill!" )
    elif toolspick == "Hammer":
        closing("Hammer",30,"Enjoy your Hammer!" )
    else:
        closing("Wrench",20,"Enjoy your Wrench!" )
 
    
# Function ask user to pick Paint items
def paint(greeting,selection,pickq):
    print(greeting)
    for item in selection:
        print(item)
    paintpick = input(pickq)
    if paintpick == "None":
        print("Goodbye")
    elif paintpick == "Paint":
        closing("Paint",15,"Enjoy your Paint!" )
    elif paintpick == "Primer":
        closing("Primer",25,"Enjoy your Primer!" )
    elif paintpick == "Brushes":
        closing("Brushes",10,"Enjoy your Brushes!" )
    elif paintpick == "Tarp":
        closing("Tarp",80,"Enjoy your Tarp!" )
    else:
        closing("Specialty Paint",35,"Enjoy your Specialty Paint!" )


# Function ask user to pick Lumber items
def lumber(greeting,selection,pickq):
    print(greeting)
    for item in selection:
        print(item)
    lumberpick = input(pickq)
    if lumberpick == "None":
        print("Goodbye")
    elif lumberpick == "Ply Wood":
        closing("Ply Wood",15,"Enjoy your Ply Wood!" )
    elif lumberpick == "Machine Screws":
        closing("Machine Screws",10,"Enjoy your Machine Screws!" )
    elif lumberpick == "Wood Screws":
        closing("Wood Screws",8,"Enjoy your Wood Screws!" )
    elif lumberpick == "PVC Boards":
        closing("PVC Boards",20,"Enjoy your PVC Boards!" )
    else:
        closing("Oak Wood",25,"Enjoy your Oak Wood!" )  

# Function ask user to pick Outdoor items
def outdoor(greeting,selection,pickq):
    print(greeting)
    for item in selection:
        print(item)
    outdoorpick = input(pickq)
    if outdoorpick == "None":
        print("Goodbye")
    elif outdoorpick == "Lawn Mower":
        closing("Lawn Mower",100,"Enjoy your Lawn Mower!" )
    elif outdoorpick == "Soil":
        closing("Soil",20,"Enjoy your Soil!" )
    elif outdoorpick == "Bricks":
        closing("Bricks",10,"Enjoy your Bricks!" )
    elif outdoorpick == "Fertilizer":
        closing("Fertilizer",25,"Enjoy your Fertilizer!" )
    else:
        closing("Plants",30,"Enjoy your Plants!" )  

        
#Function to give user total price of purchase
def closing(pickeditem,price,goodbye):
    print("Your cost for the",pickeditem,"is $"+str(price))
    more = input("Would you like to pick another item (y/n)?")
    if more == "y":
        greet_user("Great!", "n", "What category would you like to browse (Tools, Paint, Lumber, or Outdoor)? ", "Ready to browse (y/n)? ")
    else:
        for l in goodbye:
            print(l)
    
    
        
greet_user("Welcome to the Hardware store", "n", "What category would you like to browse (Tools, Paint, Lumber, or Outdoor)? ", "Ready to browse (y/n)? ")
'
