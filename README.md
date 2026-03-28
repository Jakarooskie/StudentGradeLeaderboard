# 🏆 Student Leaderboard

A terminal-based leaderboard system written in **C** that sorts and displays students by grade — either highest to lowest or lowest to highest.

---

## 📋 Description

This program allows users to input up to 100 students (name + grade), then displays a sorted leaderboard based on their preference. Built using structs, bubble sort, validated input handling, and a reusable sort function.

---

## ✨ Features

- Input up to **100 students** with names and grades
- Supports **names with spaces** (via `fgets`)
- **Grade validation** with retry loop — rejects anything outside 0–100
- Choose **sort direction**: Highest → Lowest or Lowest → Highest
- **Fallback default** if sort choice is invalid
- Clean ranked leaderboard output
- Reusable `leaderboardSort()` function (DRY principle)

---

## 🚀 Getting Started

### Prerequisites

- A C compiler (e.g., `gcc`)

### Compilation

```bash
gcc leaderboard.c -o leaderboard
```

### Run

```bash
./leaderboard
```

---

## 🖥️ Usage Example

```
How many students? 3
Student 1's name is: Jacob Vescio
Student 1's grade: 95
Student 2's name is: Alex Smith
Student 2's grade: 82
Student 3's name is: Jordan Lee
Student 3's grade: 90

How do you want the Leaderboard Displayed?
1 = Highest to Lowest, 0 = Lowest to Highest: 1

---Leaderboard---
1 - Jacob Vescio - 95
2 - Jordan Lee - 90
3 - Alex Smith - 82
```

### Grade Validation Example

```
Student 1's grade: -5
INVALID! Enter a grade between 0 and 100
Student 1's grade: 150
INVALID! Enter a grade between 0 and 100
Student 1's grade: 87
```

---

## 🗂️ Project Structure

```
leaderboard/
├── leaderboard.c   # Main source file
└── README.md       # Project documentation
```

---

## ⚙️ How It Works

1. **Input** — User enters the number of students, then each student's name and grade
2. **Validation** — Grades are checked against a 0–100 range with a retry loop
3. **Sort** — `leaderboardSort()` uses bubble sort to arrange students based on selected direction
4. **Display** — Ranked leaderboard is printed to the terminal

### Data Structure

```c
typedef struct {
    char name[20];  // Student's name (max 19 characters + null terminator)
    int grade;      // Student's grade (0 - 100)
} Player;
```

### Sort Function

```c
void leaderboardSort(Player players[], int n, int descending);
```

| Parameter | Type | Description |
|---|---|---|
| `players[]` | `Player[]` | Array of student structs |
| `n` | `int` | Number of students |
| `descending` | `int` | `1` = High → Low, `0` = Low → High |

Uses a **ternary operator** to select comparison direction, keeping the sort logic in one reusable function instead of duplicating it across multiple branches.

---

## 📈 Version History

| Version | Changes |
|---|---|
| v1 | Core struct, input, bubble sort, sort direction |
| v2 | Grade validation with `exit(1)` |
| v3 | Replaced `exit(1)` with `do-while` retry loop |
| v4 | Extracted sort into `leaderboardSort()` function — DRY principle applied |

---

## 🛣️ Planned Improvements

- [ ] Save leaderboard to a `.txt` file
- [ ] Load previous leaderboard data on startup
- [ ] Display class average grade
- [ ] Search for a student by name

---

## 💡 Concepts Used

- Structs (`typedef struct`)
- Functions and parameters (pass by value)
- Bubble sort algorithm
- Do-while loops
- Ternary operator
- Input buffer flushing
- `fgets` for string input with spaces
- `#define` constants

---

## 👤 Author

**Jacob Vescio**  
Aspiring game developer & software engineer  
📅 March 28, 2026
