# data-sourcing-challenge


## Technology Used 

| Technology Used | Resource URL | 
| ------------- |:-------------:| 
| Python | [https://www.w3schools.com/python/python_reference.asp](https://www.w3schools.com/python/python_reference.asp) | 
| Git | [https://git-scm.com/](https://git-scm.com/) | 

## Description 
In this project I created an interactive ordering system for a food truck menu using python, that allows users to select items for purchase and after checkout receive a receipt with a subtotal for the items selected.

## Code Example 

<---- First we initialize the order list using the following empty list ----->
         
         customer_order = []

 <---- In this part of the code we launch the store and present a greeting to the customer ----->

         print("Welcome to the variety food truck.")

<---- Next we implement the main loop to handle the customer's order process ----->

         place_order = True
         while place_order:

<------ Here we prompt the customer asking them from which menu category they want to order ------>

         print("\nFrom which menu would you like to order?")

<----- Then we display menu categories and store them in a dictionary ------->

     i = 1
     menu_items = {}
     for key in menu.keys():
        print(f"{i}: {key}")
        menu_items[i] = key
        i += 1

<-----  User is then prompted for menu selection and inputs are saved ------>

         menu_selection = input("Type menu number: ")

<------ Check if the customer's input is a number and Convert menu_selection to integer-------->
         if menu_selection.isdigit():
         menu_selection = int(menu_selection)`

<---- This checks if the string contains only numeric characters (digits) and  returns True if the string consists only of digits, otherwise False. This condition ensures that the input from the user is a valid number, preventing errors if the user enters non-numeric characters (like "abc" or "1a2"). If the input string passes the isdigit() check, this line converts menu_selection from a string (e.g., "3") to an integer (3) using the int() function.
Converting it to an integer allows you to perform mathematical operations, comparisons, or use it in contexts where an integer is expected. ----->








This project was a challenge due to the learning curve with Python's syntax. But with the aid of W3 schools and ChatGPT anything that I was unfamiliar with I was able to gain understanding about through these sources. Thankfully I have experience with loops and iteration from the past so I was able to call on that knowledge in this project.



## Learning Points 
I learned that Google, W3, MDN, Youtube and ChatGPT are my best friends that I will always keep very close. 


## Author Info
Armand Araujo
Age: 29
Location: Las Vegas, NV

 
* [LinkedIn](https://www.linkedin.com/in/armand-araujo-a82ba2291/) 
* [Github](https://github.com/Armand57araujo) 


## Credits 

W3 Schools, chatgpt, MDN
