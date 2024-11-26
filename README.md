You can see the code below:
    
    valid=True
    vacationDays=int(input("Please enter the days you are going to be in vacation: "))
    if vacationDays <4:
        print("Sorry, vacation days cannot be less than 4.")
        valid=False
    else:
        offDay1=int(input("Please enter the first day you are going to be in a vacation(1-7): "))
        offDay2=int(input("Please enter the second day you are going to be in a vacation(1-7): "))
        if offDay1==offDay2:
            print("Sorry, your vacation days can not be the same day.")
            valid=False
        if valid:
            weeks=int(input("Please enter the number of the weeks that you work: "))
            total_amount=0
    
            for week in range(1,weeks+1):
                for day in range(1,8):
                    if day!=offDay1 and day!=offDay2:
                        total_amount= total_amount+(week*day)
    
            print("The total amount of money you have is: "+str(total_amount))
            money_left = total_amount
            day=1
            while day <= vacationDays:
                if day % 7 == 6 or day % 7 ==0:
                    spent= 2 * (10 + day)
                else:
                    spent=10 + day
                money_left = money_left-spent
                if money_left <0:
                    print("Sorry, you do not have enough money for day "+str(day))
                else:
                    print("At the end of the day "+str(day)+" you have "+str(money_left)+" $ left.")
                day = day +1
