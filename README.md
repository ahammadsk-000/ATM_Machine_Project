# ATM_Machine_Project
import time

class ATM_Machine:

    transaction = ["Balance enquiry", "Withdraw money", "Deposit", "Change your ATM PIN", "Transfer Money", "Quit"]
    #atm_pin = 5555  # here we are stroing original pin of the card internally

    def first(self):
        print('ATM Program: ')
        print("Welcome to bank world: ")
        print('Swipe your card here: ')

    def Check_pin(self,atm_pin):
        self.atm_pin= atm_pin

        chance =0
        temp=0
        for i in range(0,4):
            if chance<=2:

                 pin = int(input("Enter your pin to proceed: "))
                 if (pin == atm_pin):
                     temp=0


                     break
                 else:
                     print("Wrong pin!, try again")
                     chance +=1
                     temp=1

            else:
                print("your ATM cord hasbeen blocked for the 3 wrong pin attempts ")
                print("It will take 24 hours to activate your card")
                print("Thanks for visiting this ATM ")
        if temp ==0:

            take = self.next_step()
            self.res1(take)


    def next_step(self):

        print("Choose your transaction: ")
        print("1. Balance enquiry")
        print("2. Withdraw money")
        print("3. deposit")
        print("4. Change your ATM PIN")
        print("5.Transfer Money")
        print("6.Quit")
        response = int(input("select your response: "))
        return response


    def res1(self,res1):
        self.res1= res1
        amount = 20000

        if res1 == 1:
            print("Your Amount is ",amount, "/- RS")

        elif res1 == 2:

            amount1 = int(input("Please enter your amount: "))
            if ((amount1>=0) and (amount1 <= 20000)):
                print("Your transaction is being processed: ")
                time.sleep(4)
                print("Please collect your Money: ")
        elif res1 == 3:
            print("Insert your money into Deposit machine")
            time.sleep(4)
            print("Your money has been added to your bank account :")
        elif res1 == 4:
            print("Please change your ATM pin number : ")
            new_pin = int(input("Enter your 4 digit new pin number: "))
            time.sleep(4)
            print('Your pin number has been generated: ')
        elif res1 == 5:

            bank_num = int(input(("Please enter a bank account number: ")))
            am = int(input("Please enter amount to transfer: "))
            print("your money has been transferred to ", bank_num, " Successfully")
        elif res1 == 6:
            print("Thanks for using this ATM: ")
            print("have a nice day")
        else:
            pass


obj1= ATM_Machine()
obj1.first()
obj1.Check_pin(5555)
