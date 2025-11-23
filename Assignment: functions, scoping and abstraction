def show_menu():
    print()
    print("What would you like to do today?")
    print()
    print("-Find a student? enter 1")
    print()
    print("-edit a student's info using student ID? enter 2")
    print()
    print("-Add a new student? enter 3")
    print()
    print("-Remove a student? enter 4")
    selection = input().strip()
    return selection

def add(students, id_, name, gpa, semester):
    students.append({
        "id": id_,
        "name": name,
        "gpa": float(gpa),
        "semester": int(semester)
    })

def remove(students, id_):
    for i, s in enumerate(students):
        if s["id"] == id_:
            del students[i]
            return True
    return False

def edit_name(students, id_, new_name):
    for s in students:
        if s["id"] == id_:
            s["name"] = new_name
            return True
    return False

def search(students, id_):
    for s in students:
        if s["id"] == id_:
            return s
    return None

def run_add(students):
    while True:
        print()
        print("Enter id of the student, followed by the student's information.")
        id_ = input("id: \n").strip()
        name = input("name: \n").strip()
        gpa = input("gpa: \n").strip()
        semester = input("semester: \n").strip()
        add(students, id_, name, gpa, semester)
        print()
        print("Student added")
        print()
        # display added student in the sample format: id  name  gpa  semester
        print(f"{id_:<8}{name:<16}{gpa:<7}{semester}")
        print()
        cont = input("Do you want to add a new student?y(yes)/n(no) \n").strip().lower()
        if cont not in ("y", "yes"):
            break

def run_search(students):
    while True:
        print()
        print("Enter the id of the student. Enter -1 to return to the previous menu")
        id_ = input().strip()
        if id_ == "-1":
            break
        found = search(students, id_)
        if found:
            print()
            print("Student found")
            # sample shows id name gpa (no semester)
            print()
            print(f"{found['id']:<8}{found['name']:<16}{found['gpa']}")
        else:
            print()
            print("Student not found")

def run_edit(students):
    while True:
        print()
        print("Enter the id of the student. Enter -1 to return to the previous menu")
        id_ = input().strip()
        if id_ == "-1":
            break
        if search(students, id_):
            print()
            print("Enter the new name of the student")
            new_name = input().strip()
            edit_name(students, id_, new_name)
            print()
            # Note: sample text contains two spaces before id number
            print(f"Student name modified for the student with id  {id_}")
            print()
            print(f"Student's new name is  {new_name}")
        else:
            print()
            print("Student not found")

def run_remove(students):
    while True:
        print()
        print("Enter id of the student that you want to remove from the students' registry.")
        id_ = input("id: \n").strip()
        removed = remove(students, id_)
        if removed:
            print()
            print("Student removed")
        else:
            print()
            print("Student not found")
        print()
        cont = input("Do you want to remove more students?y(yes)/n(no)").strip().lower()
        if cont not in ("y", "yes"):
            break

def main():
    students = []
    print("Welcome to the students record program")
    while True:
        selection = show_menu()
        if selection == "1":
            run_search(students)
        elif selection == "2":
            run_edit(students)
        elif selection == "3":
            run_add(students)
        elif selection == "4":
            run_remove(students)
        else:
            # if user enters something else, just loop back to menu
            continue

        cont = input()
        # The test plan shows after finishing a task the program asks:
        # "What you like to continue(y/yes), or exit the program(n/no)?"
        # But some sample output places this prompt on its own line. Reproduce it exactly here:
        print()
        decision = input("What you like to continue(y/yes), or exit the program(n/no)? \n").strip().lower()
        if decision in ("n", "no"):
            break

if __name__ == "__main__":
    main()
