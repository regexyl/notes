`for` + `while` loop combination
```python
def sliding_window(word):
  left, right = 0, 0
  # ...
  for right in range(len(word)):
    while left < right:
      # ...
      # if something: break
```