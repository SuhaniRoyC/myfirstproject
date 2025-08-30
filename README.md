# myfirstproject
# Simple To-Do List Console App

tasks = []  # to store all tasks

def show_tasks():
    if not tasks:
        print("\n✅ No tasks right now!")
    else:
        print("\n📋 Your To-Do List:")
        for i, task in enumerate(tasks, 1):
            status = "✅" if task["done"] else "❌"
            print(f"{i}. {task['title']} [{status}]")

def add_task():
    title = input("Enter new task: ")
    tasks.append({"title": title, "done": False})
    print(f"➕ Task '{title}' added!")

def mark_done():
    show_tasks()
    try:
        num = int(input("Enter task number to mark as complete: "))
        tasks[num - 1]["done"] = True
        print(f"✔ Task '{tasks[num - 1]['title']}' marked complete!")
    except (ValueError, IndexError):
        print("⚠ Invalid choice!")

def remove_task():
    show_tasks()
    try:
        num = int(input("Enter task number to remove: "))
        removed = tasks.pop(num - 1)
        print(f"🗑 Task '{removed['title']}' removed!")
    except (ValueError, IndexError):
        print("⚠ Invalid choice!")

# Main loop
while True:
    print("\n--- To-Do List Menu ---")
    print("1. Show Tasks")
    print("2. Add Task")
    print("3. Mark Task as Complete")
    print("4. Remove Task")
    print("5. Exit")

    if choice == "1":
        show_tasks()
    elif choice == "2":
        add_task()
    elif choice == "3":
        mark_done()
    elif choice == "4":
        remove_task()
    elif choice == "5":
        print("👋 Goodbye!")
        break
    else:
        print("⚠ Invalid option, try again.")
    else:
        print("⚠ Invalid option, try again.")
