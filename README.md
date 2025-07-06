# To-Do List Program

def display_tasks(tasks):
    """Display the list of tasks"""
    if len(tasks) == 0:
        print("No tasks in the list.")
    else:
        print("\nTask List:")
        for index, task in enumerate(tasks, 1):
            print(f"{index}. {task}")

def add_task(tasks):
    """Add a new task to the list"""
    task = input("Enter the new task: ")
    tasks.append(task)
    print(f"Task '{task}' has been added to the list.")

def remove_task(tasks):
    """Remove a task from the list"""
    try:
        task_index = int(input("Enter the number of the task you want to remove: ")) - 1
        if 0 <= task_index < len(tasks):
            removed_task = tasks.pop(task_index)
            print(f"Task '{removed_task}' has been removed from the list.")
        else:
            print("The number entered is not valid.")
    except ValueError:
        print("Please enter a valid integer.")

def main():
    tasks = []
    while True:
        print("\n--- To-Do List Menu ---")
        print("1. Display Task List")
        print("2. Add a New Task")
        print("3. Remove a Task")
        print("4. Exit")
        
        choice = input("Enter your choice: ")

        if choice == '1':
            display_tasks(tasks)
        elif choice == '2':
            add_task(tasks)
        elif choice == '3':
            remove_task(tasks)
        elif choice == '4':
            print("Exiting the program.")
            break
        else:
            print("Please select a valid option.")

if __name__ == "__main__":
    main()
