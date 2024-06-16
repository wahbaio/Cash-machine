# Create a cash machine program that takes a pin number and amount. Outputs cash is being dispensed if the pin is correct and there is enough money to withdraw. Finally outputs the newbalance.

# New features:
# £ Menu to select options
# £ Option to create new accounts
# £ Option to deposit cash
# £ Fucnctions to check if inputs are correct (PIN and amounts)

# Dictionary PIN: Balance
# Initial 3 accounts
accounts = {
    '1234': 1000,  # PIN: Balance
    '0000': 900,
    '5678': 3700,
}

# Function to display the menu
def print_menu():
    print("\nIf you want to change account please select option 3.") 
    print("££££££££££££££££££££££££") 
    print("0. Create New Account.")
    print("1. Deposit.")
    print("2. Withdraw.")
    print("3. Exit.")
    print("££££££££££££££££££££££££") 

# Function to check if the PIN is valid
def is_valid_pin(pin):
    return pin.isdigit() and len(pin) == 4

# Function to check if the amount is valid
def is_valid_amount(amount):
    try:
        value = float(amount)
        return value > 0
    except ValueError:
        return False

# Function to create a new account
def add_new_account(accounts):
    while True:
        new_pin = input("Enter your new PIN: ")
        if is_valid_pin(new_pin):
            if new_pin in accounts:
                print("PIN already registered. Please enter a different PIN.")
            else:
                accounts[new_pin] = 0
                print(f"Account {new_pin} successfully created. Initial balance: £0.00.")
                break
        else:
            print("Invalid PIN. Please enter 4 digits PIN.")

# Function to deposit cash
def deposit_cash(accounts, pin):
    deposit_amount = input("Enter amount to deposit: ")
    if is_valid_amount(deposit_amount):
        deposit_amount = float(deposit_amount)
        accounts[pin] += deposit_amount
        print(f"£{deposit_amount} deposited. New balance: £{accounts[pin]}")
    else:
        print("Invalid amount. Enter amount to deposit. ")

# Function to withdraw cash
def withdraw_cash(accounts, pin):
    withdraw_amount = input("Enter amount to withdraw: ")
    if is_valid_amount(withdraw_amount):
        withdraw_amount = float(withdraw_amount)
        if withdraw_amount <= accounts[pin]:
            accounts[pin] -= withdraw_amount
            print(f"£{withdraw_amount} withdrawn. New balance: £{accounts[pin]}")        
        else:
            print("Insufficient balance. ")
    else:
        print("Invalid amount. Enter amount to withdraw. ")

# Create a loop to run the selection process
while True:
    # Request PIN
    pin = input("Please enter your 4-digit PIN: ")
    # Check if the PIN is valid
    if is_valid_pin(pin) and pin in accounts:
        print(f"PIN accepted. Balance: £{accounts[pin]}")

        while True:
            # Print menu
            print_menu()

            choice = input("Enter your choice (0-3): ")

            if choice == '0':
                # Add new account
                add_new_account(accounts)

            elif choice == '1':
                # Deposit cash
                deposit_cash(accounts, pin)

            elif choice == '2':
                # Withdraw cash
                withdraw_cash(accounts, pin)

            elif choice == '3':
                # Exit to main PIN entry
                print("See you soon!")
                break

            else:
                print("\n\nPlease select an option.")

    else:
        print("Invalid PIN. Please enter 4 digits PIN.")
