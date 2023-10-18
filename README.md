# Initialize an empty to-do list
todo_list = []

# Function to add an item to the to-do list
def add_item(item):
    todo_list.append(item)
    print(f"Added '{item}' to the to-do list.")

# Function to display the to-do list
def display_list():
    print("To-Do List:")
    for i, item in enumerate(todo_list, start=1):
        print(f"{i}. {item}")

# Function to edit an item in the to-do list
def edit_item(index, new_item):
    if 1 <= index <= len(todo_list):
        todo_list[index - 1] = new_item
        print(f"Edited item {index} to '{new_item}'")
    else:
        print("Invalid index. Item not edited.")

# Function to delete an item from the to-do list
def delete_item(index):
    if 1 <= index <= len(todo_list):
        deleted_item = todo_list.pop(index - 1)
        print(f"Deleted item {index}: '{deleted_item}'")
    else:
        print("Invalid index. Item not deleted.")

while True:
    print("\nOptions:")
    print("1. Add an item")
    print("2. Display the to-do list")
    print("3. Edit an item")
    print("4. Delete an item")
    print("5. Quit")

    choice = input("Enter your choice (1/2/3/4/5): ")

    if choice == '1':
        item = input("Enter the item to add: ")
        add_item(item)
    elif choice == '2':
        display_list()
    elif choice == '3':
        index = int(input("Enter the index of the item to edit: "))
        new_item = input("Enter the new item: ")
        edit_item(index, new_item)
    elif choice == '4':
        index = int(input("Enter the index of the item to delete: "))
        delete_item(index)
    elif choice == '5':
        break
    else:
        print("Invalid choice. Please choose a valid option.")
