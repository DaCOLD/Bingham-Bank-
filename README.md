class Account:
    def __init__(self, balance=0):
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount

    def withdraw(self, amount):
        if amount <= self.balance:
            self.balance -= amount
            return amount
        else:
            print("Insufficient funds")
            return 0

    def get_balance(self):
        return self.balance

    class StudentAccount:
        def __init__(self, balance=0):
            super().__init__(balance)

        def deposit(self, amount):
            if amount <= 50000:
                super().deposit(amount)
            else:
                print("Deposit limit exceeded for student account")

        def withdraw(self, amount):
            if amount <= 2000:
                super().withdraw(amount)
            else:
                print("Withdrawal limit exceeded for student account")
                if __name__ == "__main__":
                    student_acc = 'StudentAccount''(1000)'
                    print("Initial balance:", student_acc.get_balance())

                    student_acc.deposit(30000)
                    print("Balance after deposit:", student_acc.get_balance())

                    student_acc.withdraw(1500)
                    print("Balance after withdrawal:", student_acc.get_balance())
