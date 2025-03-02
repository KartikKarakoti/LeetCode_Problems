class Solution:
    def calPoints(self, operations: List[str]) -> int:
        record = []
        for i in operations:
            if i.isdigit() or (i.startswith('-') and i[1:].isdigit()):
                record.append(int(i))
            elif i == "C":
                if record:
                    record.pop()
            elif i == "D":
                if record:
                    record.append(record[-1]*2)
            elif i == "+":
                if len(record) >= 2:
                    record.append(record[-1] + record[-2])        
        return sum(record)
