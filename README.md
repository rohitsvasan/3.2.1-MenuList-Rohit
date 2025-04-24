# 3.2.1-MenuList-Rohit

menu = ["Chicken sandwich", "Beef sandwich", "Tofu sandwich", "Small fries", "Medium fries", "Large fries", "Small drink", "Medium drink", "Large drink", "Water"]
order = []
item = str(0)
print("This is our menu:")

print("Sandwiches:")
print(menu[0]+" - $5.25")
print(menu[1]+" - $6.25")
print(menu[2]+" - $5.75")

print("Fries:")
print(menu[3]+" - $1.00")
print(menu[4]+" - $1.50")
print(menu[5]+" - $2.00")

print("Drinks:")
print(menu[6]+" - $1.00")
print(menu[7]+" - $1.75")
print(menu[8]+" - $2.25")
print(menu[9]+" - Free!")

while item != "done":
    item = input("What item(s) would you like? Type done to continue onwards.")
    if item in menu:
        itemcount= input("How many of these would you like?")
        item = str(itemcount) + item
        order.append(item)
        if int(itemcount) < 0:
            print("Please enter a non negative number")
    else:
        print("Sorry. We don't offer this right now.")

if item == "done": 
    checkfood = input("So you want"+ order)
    if checkfood.casefold == "yes":
