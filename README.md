# 4-2-26
#theory
Python has a built-in intersection operation.

Method 1: using &
a = [1, 2, 3, 4]
b = [3, 4, 5, 6]

result = list(set(a) & set(b))
print(result)
Method 2: using .intersection()
result = list(set(a).intersection(b))

Output
[3, 4]
✅ Time Complexity
O(n + m)  ← fastest
👉 Recommended method
✅ 2. If you just want to check present or not

(only True/False)

Method 1: any()
a = [1,2,3]
b = [5,6,3]

print(any(x in b for x in a))

Output
True

Method 2: set + bool (faster)
print(bool(set(a) & set(b)))

✅ 3. Using loop (basic way)
res = []
for x in a:
    if x in b:
        res.append(x)
print(res)

❌ Slower
O(n*m)
Only for beginners/learning.

✅ 4. If duplicates matter (important)

Example:

a = [1,2,2,3]
b = [2,2,4]


If you want:

[2,2]


Use Counter

from collections import Counter

res = list((Counter(a) & Counter(b)).elements())
print(res)

🎯 Quick guide
Need	Best method
Common unique elements	set(a) & set(b)
Just check present or not	bool(set(a) & set(b))
Keep duplicates	Counter
Learning basics	loop

If you want, tell me:
👉 do you want unique intersection or duplicates also?
I can give exact code for your case 😊

[2,2] not like that i want[2]

Got it 👍
You don’t want duplicates, you only want unique common elements.

So:

a = [1,2,2,3]
b = [2,2,4]


You want:

[2]


NOT

[2,2]

✅ Best solution → use set (removes duplicates automatically)
⭐ Recommended
a = [1,2,2,3]
b = [2,2,4]

result = list(set(a) & set(b))
print(result)

Output
[2]

✅ Alternative ways
Method 2: using intersection()
result = list(set(a).intersection(b))

Method 3: loop + set (manual)
res = set()

for x in a:
    if x in b:
        res.add(x)

print(list(res))

❌ Why Counter is wrong here?

Counter keeps duplicates:

[2,2]


So don’t use Counter if you want unique.

🎯 Rule to remember

If you want:

Unique common → set

With duplicates → Counter

Only check exists → bool(set(a) & set(b))

⚡ Final one-line solution
result = list(set(a) & set(b))


Simple + fastest 🚀

list(set(a).intersection(b))

Yes ✅
Your line is correct and perfect:

list(set(a).intersection(b))

🔍 What happens step-by-step?

Suppose:

a = [1,2,2,3]
b = [2,2,4]

Step 1 → set(a)

Removes duplicates

{1, 2, 3}

Step 2 → .intersection(b)

Keeps only common elements

{2}

Step 3 → list(...)

Convert back to list

[2]

✅ Final Output
[2]

⚡ Even shorter (Pythonic)

You can also write:

list(set(a) & set(b))


Both are same:

intersection()  ==  &

🎯 Recommendation

Most Python developers prefer:

list(set(a) & set(b))
because it's:
shorter
faster
cleaner
#prb

