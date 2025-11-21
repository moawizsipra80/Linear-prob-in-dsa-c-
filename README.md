# Hashtable Implementation in C++

This project provides a simple implementation of a **Hashtable** using **linear probing** for collision resolution.  
The class uses C++ templates, allowing it to store different data types such as `string`, `int`, etc.

---

## 📌 Features

- Custom hash function (ASCII–sum based)
- Linear probing collision handling
- Insert operation
- Search operation
- Remove (delete) operation
- Display and debugging functions
- Template-based reusable structure

---

## 🏗️ Class Overview

### **Hashtable<T>**
A dynamic array is created to store values inside the table.  
All empty positions are initialized with `"0"` to represent unused slots.

---

## 🔢 Hash Function

The hash function calculates the ASCII sum of all characters in a string and returns:


This index is used to place the value in the table.

---

## ➕ Insert Operation

The insertion process:

1. Calculate index using the hash function.
2. If the slot contains `"0"` or `"-1"`, insert the value.
3. If the slot is occupied, apply **linear probing** (move to the next index until a free spot is found).

---

## 🔍 Search Operation

The search process:

- Compute the hashed index of the target value.
- Check the slot; if not matched, use linear probing.
- Returns  
  - `true` (1) if the value is found  
  - `false` (0) if not found  

---

## ➖ Remove Operation

The remove method:

- Computes the hash index.
- If the matching value is found, it resets the slot to `"0"`.
- If an empty slot (`"0"`) is found early, the value does not exist.

---

## 📤 Display Functions

### **display()**
Shows only the values stored in the table.

### **displaycontents()**
Shows the entire table and then prints only the non-empty values.

---

## ▶️ Example Usage

```cpp
Hashtable<string> h(20);

h.insert("moawiz");
h.insert("ali");
h.insert("sipra");
h.insert("rehan");

cout << h.search("ali") << endl;

h.remove("moawiz");

h.display();
