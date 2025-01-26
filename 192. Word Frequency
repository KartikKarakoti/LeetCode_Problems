import re
a = open("words.txt")
b = a.read().strip()
a.close()
z = b.split("\n")
y=" ".join(z)
# I used regex to split on any whitespace bc I failed a test case
c=re.split(r"\s+", y)
d=dict()
for w in c:
	x=d.get(w,0)
	d[w]=x+1
out=[(w[1],w[0]) for w in list(d.items())]
out.sort(reverse=True)
for o in out:
	print(o[1],o[0])
