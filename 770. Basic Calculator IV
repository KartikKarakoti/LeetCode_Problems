class Solution:

    def basicCalculatorIV(self, expression: str, evalvars: List[str], evalints: List[int]) -> List[str]:
        def mult(a, b):
            c = defaultdict(int)
            for ka, va in a.items():
                for kb, vb in b.items():
                    k = tuple(sorted(ka + kb))
                    c[k] += va * vb
            return c

        def add(a, b, m=1):
            for k, v in b.items():
                a[k] += m * v

        s = expression.replace(" ", "") + ")"
        variables = {k:v for k, v in zip(evalvars, evalints)}
    
        def solve(i):
            word = ""
            tot = defaultdict(int)
            curr = {(): 1}

            while True:
                v = None
                if s[i] == "(":
                    v, i = solve(i + 1)
                    
                if s[i] in ")*-+":
                    if word:
                        v = {(word,): 1}

                        if word[0].isdigit():
                            v = {(): int(word)}
                        if word in variables:
                            v = {(): variables[word]}

                    curr = mult(curr, v)
                    word = ""
                else:
                    word += s[i]

                if s[i] in ")+-":
                    add(tot, curr)
                if s[i] in "+-":
                    curr = {(): 1 if s[i] == "+" else -1}
                if s[i] == ")":
                    return tot, (i + 1)

                i += 1
        ans,_ = solve(0)

        ret = []
        for k, v in ans.items():
            if v == 0: continue
            n = "*".join(k)
            ret.append((-1 * len(k), n, f'{v}*{n}' if n else f'{v}'))

        ret.sort()
        return list(map(lambda x: x[2], ret))

