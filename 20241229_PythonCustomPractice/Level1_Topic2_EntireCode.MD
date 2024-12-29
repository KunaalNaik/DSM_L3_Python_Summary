### **Stage 1: Data Structures Problem Statements**  
Below are 10 progressively challenging problem statements. Each includes a scenario, starter code, and clear instructions. 

---

### **Topic: Lists**

#### **1. Easy Problem - Creating a To-Do List**  
**Scenario:** You are building a simple to-do list app. Each task in the list is represented as a string.  

**Starter Code:**  
```python
tasks = []
```

**Problem Statement:**  
1. Add three tasks to the list: "Buy groceries", "Clean room", "Finish project".  
2. Print the list after adding the tasks.  

---

#### **2. Medium Problem - Task Organizer**  
**Scenario:** The to-do list app now needs to sort tasks by priority. Tasks starting with "!" are high priority.  

**Starter Code:**  
```python
tasks = ["Clean room", "!Pay bills", "Buy groceries", "!Submit report"]
```

**Problem Statement:**  
1. Separate high-priority tasks (those starting with "!") into a new list.  
2. Print the high-priority list and the remaining tasks.  

---

### **Topic: Dictionaries**

#### **3. Easy Problem - Contact Book**  
**Scenario:** You are creating a contact book where each contact is stored as a key-value pair with names as keys and phone numbers as values.  

**Starter Code:**  
```python
contacts = {}
```

**Problem Statement:**  
1. Add the following contacts to the dictionary: "Alice: 1234567890", "Bob: 9876543210".  
2. Retrieve and print Bob's phone number.  

---

#### **4. Medium Problem - Contact Search**  
**Scenario:** You want to search for contacts by their phone number.  

**Starter Code:**  
```python
contacts = {
    "Alice": "1234567890",
    "Bob": "9876543210",
    "Charlie": "1122334455"
}
```

**Problem Statement:**  
1. Write a function `find_contact(phone_number)` to return the name of the contact given a phone number.  
2. Test the function with the input `"9876543210"`.  

---

### **Topic: Tuples**

#### **5. Easy Problem - Coordinate Storage**  
**Scenario:** A GPS app stores locations as tuples of latitude and longitude.  

**Starter Code:**  
```python
locations = []
```

**Problem Statement:**  
1. Add three locations to the list as tuples: (12.9716, 77.5946), (28.7041, 77.1025), (19.0760, 72.8777).  
2. Print the list of locations.  

---

#### **6. Medium Problem - Distance Calculator**  
**Scenario:** The GPS app now needs to find the closest location to a given point.  

**Starter Code:**  
```python
locations = [(12.9716, 77.5946), (28.7041, 77.1025), (19.0760, 72.8777)]
current_location = (13.0827, 80.2707)  # Example current location
```

**Problem Statement:**  
1. Write a function `find_closest(locations, current_location)` to find and return the closest location.  
2. Test it with the given `current_location`.  

---

### **Topic: Sets**

#### **7. Easy Problem - Unique Visitors**  
**Scenario:** A website tracks visitors using their IP addresses.  

**Starter Code:**  
```python
visitors = set()
```

**Problem Statement:**  
1. Add the following IPs to the set: "192.168.1.1", "192.168.1.2", "192.168.1.1", "192.168.1.3".  
2. Print the unique visitor count.  

---

#### **8. Medium Problem - Common Visitors**  
**Scenario:** Find common visitors between two different days.  

**Starter Code:**  
```python
day1_visitors = {"192.168.1.1", "192.168.1.2", "192.168.1.3"}
day2_visitors = {"192.168.1.2", "192.168.1.4", "192.168.1.1"}
```

**Problem Statement:**  
1. Find and print the set of common visitors between the two days.  
2. Find and print the set of visitors unique to each day.  

---

### **Topic: Strings**

#### **9. Easy Problem - Sentence Analyzer**  
**Scenario:** Analyze the words in a sentence to count their occurrences.  

**Starter Code:**  
```python
sentence = "Python is great and Python is easy"
```

**Problem Statement:**  
1. Split the sentence into words and count the frequency of each word using a dictionary.  
2. Print the dictionary of word frequencies.  

---

#### **10. Medium Problem - Anagram Checker**  
**Scenario:** Check if two strings are anagrams of each other (contain the same characters in any order).  

**Starter Code:**  
```python
def is_anagram(str1, str2):
    pass
```

**Problem Statement:**  
1. Complete the `is_anagram` function to return `True` if the strings are anagrams, otherwise `False`.  
2. Test the function with inputs `"listen"` and `"silent"`.  