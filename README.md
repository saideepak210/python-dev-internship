# python-dev-internship
tasks = []

# Function to add a task
def add_task():
    task = input("Enter the task: ")
    tasks.append(task)
    print("Task added successfully!")

# Function to mark a task as completed
def mark_completed():
    task_index = int(input("Enter the index of the task to mark as completed: "))
    if task_index < len(tasks):
        tasks[task_index] = "✓ " + tasks[task_index]
        print("Task marked as completed!")
    else:
        print("Invalid task index!")

# Function to remove completed tasks
def remove_completed():
    completed_tasks = [task for task in tasks if task.startswith("✓")]
    for task in completed_tasks:
        tasks.remove(task)
    print("Completed tasks removed successfully!")

# Function to display the to-do list
def display_tasks():
    print("To-Do List:")
    for index, task in enumerate(tasks):
        print(f"{index}. {task}")

# Main program loop
while True:
    print("\nMenu:")
    print("1. Add Task")
    print("2. Mark Task as Completed")
    print("3. Remove Completed Tasks")
    print("4. Display Tasks")
    print("5. Exit")

    choice = input("Enter your choice (1-5): ")

    if choice == "1":
        add_task()
    elif choice == "2":
        mark_completed()
    elif choice == "3":
        remove_completed()
    elif choice == "4":
        display_tasks()
    elif choice == "5":
        print("Goodbye!")
        break
    else:
        print("Invalid choice. Please try again.")
