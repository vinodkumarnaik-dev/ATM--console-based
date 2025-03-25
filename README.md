# ATM--console-based
# ATM Operations - Console-Based Python Project

# Dictionary to store user details
users = {
    "1234": {"pin": "0000", "balance": 5000, "transactions": []},
    "5678": {"pin": "1111", "balance": 3000, "transactions": []}
}

def deposit(account_number, amount):
    users[account_number]["balance"] += amount
    users[account_number]["transactions"].append(f"Deposited: {amount}")
    print(f"Amount {amount} deposited successfully. New balance: {users[account_number]['balance']}")

def withdraw(account_number, amount):
    if users[account_number]["balance"] >= amount:
        users[account_number]["balance"] -= amount
        users[account_number]["transactions"].append(f"Withdrawn: {amount}")
        print(f"Amount {amount} withdrawn successfully. Remaining balance: {users[account_number]['balance']}")
    else:
        print("Insufficient balance.")

def generate_pin(account_number, new_pin):
    users[account_number]["pin"] = new_pin
    print("PIN updated successfully.")

def mini_statement(account_number):
    print("Last Transactions:")
    for transaction in users[account_number]["transactions"][-5:]:
        print(transaction)

def atm_operations():
    account_number = input("Enter Account Number: ")
    if account_number in users:
        pin = input("Enter PIN: ")
        if pin == users[account_number]["pin"]:
            while True:
                print("\n1. Deposit\n2. Withdraw\n3. Generate PIN\n4. Mini Statement\n5. Exit")
                choice = input("Choose an option: ")
                if choice == "1":
                    amount = int(input("Enter amount to deposit: "))
                    deposit(account_number, amount)
                elif choice == "2":
                    amount = int(input("Enter amount to withdraw: "))
                    withdraw(account_number, amount)
                elif choice == "3":
                    new_pin = input("Enter new PIN: ")
                    generate_pin(account_number, new_pin)
                elif choice == "4":
                    mini_statement(account_number)
                elif choice == "5":
                    print("Thank you for using ATM services.")
                    break
                else:
                    print("Invalid choice. Try again.")
        else:
            print("Incorrect PIN.")
    else:
        print("Account not found.")

# Run ATM operations
atm_operations()
