# 3.2.1-MenuList-Rohit

menu = ["Chicken sandwich(es)", "Beef sandwich(es)", "Tofu sandwich(es)", "Small fries", "Medium fries", "Large fries", "Small drink(s)", "Medium drink(s)", "Large drink(s)", "Water"]
prices = str([5.25, 6.25, 5.75, 1.00, 1.50, 2.00, 1.00, 1.75, 2.25, 0.00])
order = []
item = str(0)
totalcost = 0.0
print("This is our menu:")

print("Sandwiches:")
print(menu[0]+" - $"+prices[0])
print(menu[1]+" - $"+prices[1])
print(menu[2]+" - $"+prices[2])

print("Fries:")
print(menu[3]+" - $"+prices[3])
print(menu[4]+" - $"+prices[4])
print(menu[5]+" - $"+prices[5])

print("Drinks:")
print(menu[6]+" - $"+prices[6])
print(menu[7]+" - $"+prices[7])
print(menu[8]+" - $"+prices[8])
print(menu[9]+" - Free!")

while item.casefold != "done":
    item = input("What item(s) would you like? Type done to continue onwards.")
    if item.casefold in menu:
        itemcount= input("How many of these would you like?")
        if int(itemcount) >= 0:
            totalcost += prices[menu.index[item]] * itemcount
            item = str(itemcount) + item
            order.append(item)
        else:
            print("Please enter a non-negative number.")
    else:
        print("Sorry. We don't offer this right now.")

if item == "done": 
    condiments = str(0)
    packets = 0
    checkfood = input("So you want"+ order)
    if checkfood.casefold == "yes":
        condiments = input("Would you like some packets of ketchup with your meal?")
        if condiments.casefold == ("yes"):
            while True:
                packets = int(input("How many packets would you like?"))
                if packets >= 0:
                    totalcost = totalcost + packets * 0.25
                    print("Alright your total is going to be "+totalcost+". Pay here!")
                    break
                else:
                    print("Please enter a positive integer for the number of packets.")
        else:
            print("Alright your total is going to be "+totalcost+". Pay here!")
    else:
        print("Oh ok.")
        totalcost = 0
        order = []
        item.casefold != "done"


        
