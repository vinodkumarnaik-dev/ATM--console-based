# Console-Based ATM Operations

# Dictionary to store user details
users = {
    "1234": {"pin": "0000", "balance": 5000, "transactions": []}
}

def deposit(account, amount):
    users[account]["balance"] += amount
    users[account]["transactions"].append(f"Deposited: ${amount}")
    print(f"${amount} deposited successfully! New Balance: ${users[account]['balance']}")

def withdraw(account, amount):
    if users[account]["balance"] >= amount:
        users[account]["balance"] -= amount
        users[account]["transactions"].append(f"Withdrawn: ${amount}")
        print(f"${amount} withdrawn successfully! New Balance: ${users[account]['balance']}")
    else:
        print("Insufficient balance!")

def generate_pin(account, new_pin):
    users[account]["pin"] = new_pin
    print("PIN changed successfully!")

def mini_statement(account):
    print("\nMini Statement:")
    for transaction in users[account]["transactions"][-5:]:  # Last 5 transactions
        print(transaction)
    print(f"Current Balance: ${users[account]['balance']}")

def main():
    account = "1234"  # Example account number
    pin = input("Enter your PIN: ")
    
    if pin == users[account]["pin"]:
        while True:
            print("\n1. Deposit\n2. Withdraw\n3. Generate PIN\n4. Mini Statement\n5. Exit")
            choice = input("Select an option: ")
            
            if choice == "1":
                amount = int(input("Enter amount to deposit: "))
                deposit(account, amount)
            elif choice == "2":
                amount = int(input("Enter amount to withdraw: "))
                withdraw(account, amount)
            elif choice == "3":
                new_pin = input("Enter new PIN: ")
                generate_pin(account, new_pin)
            elif choice == "4":
                mini_statement(account)
            elif choice == "5":
                print("Thank you for using the ATM!")
                break
            else:
                print("Invalid option, please try again.")
    else:
        print("Invalid PIN!")

if __name__ == "__main__":
    main()
