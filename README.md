#  Railway Management System & 🎓 Student Record Management System

Two console-based C applications demonstrating structured programming, modular design, and file handling. Both systems use a clean menu-driven interface and simulate real-world record management with text-file persistence.

---

##  Overview

This repository contains two independent C projects:

- **Railway Management System (RMS)** – manages trains, stations, routes, stops, and passengers.  
- **Student Record Management System (SRMS)** – manages student details, authentication, backup, and CSV export.

Both projects are fully compatible with **VS Code + GCC** and auto-create required text files on first run.

---

#  Railway Management System (RMS)

A console-based application simulating basic railway operations.

##  Features
- Add/Delete Trains  
- Add/Delete Stations  
- Add Stops to Train Routes  
- Add/Remove Passengers  
- Train Journey Simulation  
- List Trains & Stations  

## 📂 Folder Structure
```
railway/
│── railway.c
│── data/
│    ├── trains.txt
│    ├── stations.txt
│    ├── passengers.txt
│    └── stops.txt
│── screenshots/
│── README.md
```

## 🧾 Code Snippet (Structs)
```c
typedef struct Passenger {
    int ticket_id;
    struct Passenger *next;
} Passenger;

typedef struct Station {
    char name[32];
    struct Station *next;
} Station;

typedef struct Stop {
    Station *station;
    struct Stop *next;
} Stop;

typedef struct Train {
    char name[32];
    Stop *stops;
    Passenger *passengers;
    struct Train *next;
} Train;
```

## 🧾 Code Snippet (Add Train)
```c
void add_train() {
    char name[32];
    printf("Enter Train Name: ");
    scanf("%s", name);
    Train *t = create_train(name);
    t->next = train_head;
    train_head = t;
    printf("Train '%s' added.\n", name);
}
```



# Student Record Management System (SRMS)

A file-based C application for managing student information.

##  Features
- Add Student  
- Display Students  
- Search by Name/Roll  
- Update Records  
- Delete Records  
- CSV Export  
- Backup Creation  
- Login Authentication  

## 📂 Folder Structure
```
srms/
│── srms.c
│── data/
│    ├── students.txt
│    ├── credentials.txt
│    ├── students_backup.txt
│    ├── report.txt
│    └── students.csv
│── screenshots/
│── README.md
```

## 🧾 Code Snippet (Student Struct)
```c
struct Student {
    int roll;
    char name[50];
    float marks;
};
```

## 🧾 Code Snippet (Add Student)
```c
void addStudent() {
    struct Student s;
    FILE *fp = fopen("students.txt", "a");

    printf("Enter Roll No: ");
    scanf("%d", &s.roll);
    printf("Enter Name: ");
    scanf("%s", s.name);
    printf("Enter Marks: ");
    scanf("%f", &s.marks);

    fprintf(fp, "%d %s %.2f\n", s.roll, s.name, s.marks);
    fclose(fp);

    printf("Student added successfully.\n");
}
```

---

# 🛠️ How to Compile & Run

### Compile
```
gcc railway.c -o railway
gcc srms.c -o srms
```

### Run
```
./railway
./srms
```

Windows:
```
railway.exe
srms.exe
```

---

# 📄 Required Text Files

Created automatically if missing:

### SRMS
```
students.txt
credentials.txt
students_backup.txt
students.csv
report.txt
```

### RMS
```
trains.txt
stations.txt
passengers.txt
stops.txt
```

---

# Example Menus

### Railway Menu
```
---- Railway Management Menu ----
1. Add Train
2. Delete Train
3. Add Station
4. Delete Station
5. Add Stop to Train
6. Run Train
7. Add Passenger
8. Remove Passenger
9. List Trains
10. List Stations
11. Exit
```

### SRMS Menu
```
------ Student Record Management System ------
1. Add Student
2. Display Students
3. Search Student
4. Update Record
5. Delete Student
6. Backup Data
7. Export CSV
8. Generate Report
9. Logout
```

---

#  Learning Outcomes
- File Handling in C  
- Structured & Modular Programming  
- Linked List Operations  
- Real-World System Simulation  
- Menu-Driven Program Design  
- Persistent Data Management  

---

# Notes
- Works on Linux, Windows, and macOS.  
- Files auto-create on first run.  
- You may add screenshots to the `screenshots/` folder.  

---

# End of README
