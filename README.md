# EkAnek Assignment
# Solution to Question 1
```
import operator


class Student:
    def __init__(self, name, age, marks, rollNumber):
        self.name = name
        self.age = age
        self.marks = marks
        self.rollNumber = rollNumber

    def __repr__(self):
        return "Student object: Name: {}, Age: {}, Marks: {}, rollNumber: {}".format(self.name, self.age, self.marks,
                                                                                     self.rollNumber)


def sort(students, criteria):
    return sorted(students, key=operator.attrgetter(*criteria))


# Test Case
a = Student('kunal', 25, 89, 12)
b = Student('nishu', 23, 676, 56)
c = Student('rahul', 90, 12, 1)
d = Student('rahul', 45, 12, 1)
e = Student('kunal', 25, 12, 1)
students = [a, b, c, d, e]
criteria = ['name', 'age', 'marks']
sorted_list = sort(students, criteria)
print(*sorted_list, sep="\n")

# Time complexity: O(k*nlogn),
# Space complexity: O(n)
# where k=number of keys in criteria, n= number of students
```

# Solution to Question 2
```
import heapq


def printCheapestFlights(delhi_to_mumbai, mumbai_to_delhi, k):
    combination_heap = []
    for i in delhi_to_mumbai:
        for j in mumbai_to_delhi:
            combination_heap.append((i, j))
    elements = heapq.nsmallest(k, combination_heap, key=lambda x: [sum(x), x[0]])
    print(elements)


k = 9
delhi_to_mumbai = [5, 4, 10]
mumbai_to_delhi = [1, 9, 3]
printCheapestFlights(delhi_to_mumbai, mumbai_to_delhi, k)

#Time complexity = O(n^2)
#Space complexity = O(n^2)
```
