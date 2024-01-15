```python
#checking whether the given year if leapyera or not
x=int(input("Enter a year : "))
leap_years = [f"{x} is leap year" if (x % 4 == 0 and x % 100 != 0) or (x % 400 == 0) else f"{x} is not a leap year"]
print(leap_years)

```

    Enter a year : 2024
    ['2024 is leap year']
    


```python

```
