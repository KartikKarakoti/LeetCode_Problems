class Solution:
    def lemonadeChange(self, bills: List[int]) -> bool:
        fiveCount, tenCount = 0, 0  # Track available 5-dollar and 10-dollar bills

        for bill in bills:
            if bill == 5:  # No change needed, just collect a 5-dollar bill
                fiveCount += 1
            elif bill == 10:  # Need to give back 5 dollars as change
                if fiveCount:  # If we have a 5-dollar bill for change
                    fiveCount -= 1
                    tenCount += 1
                else:
                    return False  # Can't give change
            else:  # bill == 20, need to give 15 dollars as change
                if tenCount and fiveCount:  # Prefer giving one 10 and one 5
                    tenCount -= 1
                    fiveCount -= 1
                elif fiveCount >= 3:  # If no 10-dollar bills, give three 5-dollar bills
                    fiveCount -= 3
                else:
                    return False  # Can't give 15 dollars change

        return True
