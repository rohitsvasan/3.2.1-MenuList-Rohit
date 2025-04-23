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
menu[6]+" - $1.50"
fries = [menu[3], menu[4], menu[5], menu[6]]

"Drinks:"
menu[7]+" - $1.00"
menu[8]+" - $1.75"
menu[9]+" - $2.25"
menu[10]+" - Free!"
drinks = [menu[7], menu[8], menu[9], menu[10]]

sandwich = str(0)
sandwichcount = 0
responsetruth = False
totalcost = 0.00
while responsetruth == False:
    sandwich = input("What type of sandwich do you want? Chicken (1), Beef (2), or Tofu (3)?")
    if sandwich == "1":   
        print("Great! Got that.")
        confirm1 = input("One Chicken sandwich, correct?")
        if confirm1 == "Yes":
            sandwichcount = int(input("How many of them?"))
            totalcost = 5.25 * sandwichcount
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
            sandwichcount = int(input("How many of them?"))
            totalcost = 6.25 * sandwichcount
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
            sandwichcount = int(input("How many of them?"))
            totalcost = 5.75 * sandwichcount
            print("Alright got it!")
            responsetruth = True
        else:
            sandwich = "No sandwich"
            sandwichcount = 0
            print("Oh ok.")
            responsetruth = True
    else:
        responsetruth = False
        print("Invalid response. Respond with one of the numbers listed above.")

if responsetruth == True: 
    responsetruth1 = False
    sodacount = 0
    while responsetruth1 == False:
        beverage = input("Alright, would you like a drink?")
        if beverage == "Yes":
            beveragetype = input("What size of drink would you like? Small soda (1), Medium soda (2), Large soda (3), or Water (4)?")
            if beveragetype == "1":
                sodacount = int(input("How many sodas would you like?"))
                totalcost = totalcost + 1.00 * sodacount
                print("Alright got it!")
                responsetruth1 = True
            elif beveragetype == "2":
                sodacount = int(input("How many sodas would you like?"))
                totalcost = totalcost + 1.75 * sodacount
                print("Alright got it!")
                responsetruth1 = True
            elif beveragetype == "3":
                sodacount = int(input("How many sodas would you like?"))
                totalcost = totalcost + 2.25 * sodacount
                print("Alright got it!")
                responsetruth1 = True
            elif beveragetype == "4":
                print("Alright that's good. There won't be any extra cost!")
                responsetruth1 = True
            else:
                print("Invalid response. Respond with one of the numbers listed above.")
                responsetruth1 = False
        else:
            beveragetype = "No drink"
            sodacount = 0
            print("Oh ok.")
            responsetruth1 = True

if responsetruth1 == True:
    responsetruth2 = False
    friescount = 0
    while responsetruth2 == False:
        friestype = input("Alright, would you like some fries?")
        if friestype == "Yes":
            friestype = input("What size of fries would you like? Small fries (1), Medium fries (2), Large fries (3), or Curly fries (4)")
            if friestype == "1":
                supersize = input("Would you like to supersize your fries?")
                if supersize == "Yes":
                    friescount = int(input("How many of them would you like?"))
                    totalcost = totalcost + 2.00 * friescount
                    print("Alright got it!")
                    responsetruth2 = True
                else:
                    friescount = int(input("How many of them would you like?"))
                    totalcost = totalcost + 1.00 * friescount
                    print("Alright got it!")
                    responsetruth2 = True
            elif friestype == "2":
                friescount = int(input("How many of them would you like?"))
                totalcost = totalcost + 1.50 * friescount
                print("Alright got it!")
                responsetruth2 = True
            elif friestype == "3":
                friescount = int(input("How many of them would you like?"))
                totalcost = totalcost + 2.00 * friescount
                print("Alright got it!")
                responsetruth2 = True
            elif friestype == "4":
                supersize2 = input("Would you like to supersize your curly fries?")
                if supersize2 == "Yes":
                    friescount = int(input("How many of them would you like?"))
                    totalcost = totalcost + 2.50 * friescount
                else:
                    friescount = int(input("How many of them would you like?"))
                    totalcost = totalcost + 1.50 * friescount
            else:
                print("Invalid response. Respond with the size of the fries you want.")
                responsetruth2 = False
        else:
            friestype = "No fries"
            print("Oh ok.")
            friescount = 0
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
                if sandwichcount >= 1 and friescount >= 1:
                    totalcost = totalcost - 1
                print("Alright that would be $"+str(totalcost)+"." "Pay here!")
                print("Thank you! Have a good one!")
                responsetruth3 = True
        elif condiment == "Mayo":
            packets = input("How many packets of mayo would you like? One packet is $0.35.")
            totalcost = totalcost + int(packets)*0.35
            checkfood = input("Alright you ordered "+sandwich+", "+beveragetype+", "+friestype+", and "+str(packets)+" packets of mayo, right?")
            if checkfood == "Yes":
                if sandwichcount >= 1 and friescount >= 1:
                    totalcost = totalcost - 1
                print("Alright that would be $"+str(totalcost)+"." "Pay here!")
                print("Thank you! Have a good one!")
                responsetruth3 = True
        elif condiment == "Neither":
            checkfood = input("Alright you ordered "+sandwich+", "+beveragetype+", "+friestype+", and no condiments, right?")
            if checkfood == "Yes":
                if sandwichcount >= 1 and friescount >= 1:
                    totalcost = totalcost - 1
                print("Alright that would be $"+str(totalcost)+"." "Pay here!")
                print("Thank you! Have a good one!")
                responsetruth3 = True
