## Single class example
```python
class test:  # we use the `'class'` keyword to create a new class
    # __init__ method is the main menthod of the class from where the execution will be started
    def __init__(self, fname, lname, ageinyear):  # by default the 'self' arg is passed in every method inside a class
        self.name = fname + " " + lname  # creating a new variable to store the full name*
        self.age = ageinyear # creating a variable to store the age*


t1 = test("Sabuj", "Mondal", 20)  # creating an object t1 of the class 'test'
# these provided arguments will be stored in the variables in the '__init__' method of class 'test'
print(t1.name)  # the value of the variable 'name' (inside __init__ method) will be printed for the object t1
print(t1.age)  # the value of the variable 'age' (inside __init__ method) will be printed for the object t1
```

## Multi class example
```python
# creating an object that will store patient personal info and clinical info
class patientInfo:
    def __init__(self, name, age):  # this method will store the personal data and the provided clinical data
        self.patientname = name  # patient name
        self.patientage = age  # patient age
        self.testreport = []  # patient cclinical info. This info will be come from another class

    def addtestdata(self, testinfo):  # method to fetch patient's clinical info from another class
        self.testreport.append(testinfo)  # the fetched clinical info will be appended in the 'testreport' list


class clinicalinfo:
    def __init__(self, test_name, test_value):
        self.testof = test_name
        self.value = test_value


p = patientInfo("Sabuj", 20)

print(p.patientname)
print(p.patientage)

c = clinicalinfo("BP", "80/115")
p.addtestdata(c)

for k in p.testreport:
    print(k.testof, k.value)
```
