# Dynamic-Expense-Tracker
class ExpenseTracker:
    def __init__(self):
        self.expenses = {}

    def add_expense(self, category, amount):
        if category in self.expenses:
            self.expenses[category] += amount
        else:
            self.expenses[category] = amount
        print(f"Added {amount} to {category}.")

    def show_expenses(self):
        print("\nExpense Summary:")
        if self.expenses:
            total = 0
            for category, amount in self.expenses.items():
                print(f"{category}: ${amount}")
                total += amount
            print(f"Total Expenses: ${total}")
        else:
            print("No expenses recorded yet.")

    def run(self):
        while True:
            print("\nExpense Tracker Menu:")
            print("1. Add Expense")
            print("2. Show Expenses")
            print("3. Exit")
            
            choice = input("Choose an option (1/2/3): ")
            
            if choice == '1':
                category = input("Enter expense category: ")
                amount = float(input("Enter expense amount: "))
                self.add_expense(category, amount)
            elif choice == '2':
                self.show_expenses()
            elif choice == '3':
                print("Exiting Expense Tracker. Goodbye!")
                break
            else:
                print("Invalid option, please try again.")

# Create an instance of ExpenseTracker and run the program
tracker = ExpenseTracker()
tracker.run()
