## Holiday
```python
start = input("When do you leave?")
stay = input("How long will you stay?")

start = int(start)
stay = int(stay)

final = (start + stay) % 6 - 1

print(final)
```
