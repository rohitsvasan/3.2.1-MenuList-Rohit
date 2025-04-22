# 3.2.1-MenuList-Rohit

menu = ["Chicken sandwich", "Beef sandwich", "Tofu sandwich", "Small fries", "Medium fries", "Large fries", "Curly fries", "Small drink", "Medium drink", "Large drink", "Water"]
print("This is our menu:")

"Sandwiches:"
menu[0]+" - $5.25"
menu[1]+" - $6.25"
menu[2]+" - $5.75"
sandwiches = [menu[0], menu[1], menu[2]]

"Fries:"
menu[3]+" - $1.00"
menu[4]+" - $1.50"
menu[5]+" - $2.00"
menu[6]+" - $1.75"
fries = [menu[3], menu[4], menu[5], menu[6]]

"Drinks:"
menu[7]+" - $1.00"
menu[8]+" - $1.75"
menu[9]+" - $2.25"
menu[10]+" - Free!"
drinks = [menu[7], menu[8], menu[9], menu[10]]

sandwich = str(0)
sandwichamount = 0
responsetruth = False
totalcost = 0.00
while responsetruth == False:
    sandwich = input("What type of sandwich do you want? Chicken (1), Beef (2), or Tofu (3)?")
    if sandwich == "1":   
        print("Great! Got that.")
        confirm1 = input("One Chicken sandwich, correct?")
        if confirm1 == "Yes":
            sandwichamount = int(input())
            totalcost = 5.25
            print("Alright got it!")
            responsetruth = True
        else:
            sandwich = "No sandwich"
            print("Oh ok.")
            responsetruth = True
    elif sandwich == "2":
        print("Great! Got that.")
        confirm1 = input("One Beef sandwich, correct?")
        if confirm1 == "Yes":
            totalcost = 6.25
            print("Alright got it!")
            responsetruth = True
        else:
            sandwich = "No sandwich"
            print("Oh ok.")
            responsetruth = True
    elif sandwich == "3":
        print("Great! Got that.")
        confirm1 = input("One Tofu sandwich, correct?")
        if confirm1 == "Yes":
            totalcost = 5.75
            print("Alright got it!")
            responsetruth = True
        else:
            sandwich = "No sandwich"
            print("Oh ok.")
            responsetruth = True
    else:
        responsetruth = False
        print("Invalid response. Respond with Chicken, Beef, or Tofu.")

if responsetruth == True: 
    responsetruth1 = False
    while responsetruth1 == False:
        beverage = input("Alright, would you like a drink?")
        if beverage == "Yes":
            beveragetype = input("What size of drink would you like? Small soda ($1.00), Medium soda ($1.75), Large soda ($2.25), or Water (Free)?")
            if beveragetype == "Small soda":
                totalcost = totalcost + 1.00
                print("Alright got it!")
                responsetruth1 = True
            elif beveragetype == "Medium soda":
                totalcost = totalcost + 1.75
                print("Alright got it!")
                responsetruth1 = True
            elif beveragetype == "Large soda":
                totalcost = totalcost + 2.25
                print("Alright got it!")
                responsetruth1 = True
            elif beveragetype == "Water":
                print("Alright that's good. There won't be any extra cost!")
                responsetruth1 = True
            else:
                print("Invalid response. Respond with either the size of soda or water.")
                responsetruth1 = False
        else:
            beveragetype = "No drink"
            print("Oh ok.")
            responsetruth1 = True

if responsetruth1 == True:
    responsetruth2 = False
    while responsetruth2 == False:
        friestype = input("Alright, would you like some fries?")
        if friestype == "Yes":
            friestype = input("What size of fries would you like? Small fries ($1.00), Medium fries ($1.50), Large fries ($2.00)")
            if friestype == "Small fries":
                supersize = input("Would you like to supersize your fries?")
                if supersize == "Yes":
                    totalcost = totalcost + 2.00
                    print("Alright got it!")
                    responsetruth2 = True
                else:
                    totalcost = totalcost + 1.00
                    print("Alright got it!")
                    responsetruth2 = True
            elif friestype == "Medium fries":
                totalcost = totalcost + 1.50
                print("Alright got it!")
                responsetruth2 = True
            elif friestype == "Large fries":
                totalcost = totalcost + 2.00
                print("Alright got it!")
                responsetruth2 = True
            else:
                print("Invalid response. Respond with the size of the fries you want.")
                responsetruth2 = False
        else:
            friestype = "No fries"
            print("Oh ok.")
            responsetruth2 = True

if responsetruth2 == True:
    responsetruth3 = False
    condiment = str(0)
    packets = str(0)
    checkfood = str(0)
    while responsetruth3 == False:
        condiment = input("Alright would you like ketchup, mayo, or neither?")
        if condiment == "Ketchup":
            packets = input("How many packets of ketchup would you like? One packet is $0.25.")
            totalcost = totalcost + int(packets)*0.25
            checkfood = input("Alright you ordered "+sandwich+", "+beveragetype+", "+friestype+", and "+str(packets)+" packets of ketchup, right?")
            if checkfood == "Yes":
                totalcost = totalcost - 1
                print("Alright that would be $"+str(totalcost)+"." "Pay here!")
                print("Thank you! Have a good one!")
                responsetruth3 = True
        elif condiment == "Mayo":
            packets = input("How many packets of mayo would you like? One packet is $0.35.")
            totalcost = totalcost + int(packets)*0.35
            checkfood = input("Alright you ordered "+sandwich+", "+beveragetype+", "+friestype+", and "+str(packets)+" packets of mayo, right?")
            if checkfood == "Yes":
                totalcost = totalcost - 1
                print("Alright that would be $"+str(totalcost)+"." "Pay here!")
                print("Thank you! Have a good one!")
                responsetruth3 = True
        elif condiment == "Neither":
            checkfood = input("Alright you ordered "+sandwich+", "+beveragetype+", "+friestype+", and no condiments, right?")
            if checkfood == "Yes":
                totalcost = totalcost - 1
                print("Alright that would be $"+str(totalcost)+"." "Pay here!")
                print("Thank you! Have a good one!")
                responsetruth3 = True
