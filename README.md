# 🚀 **CLI Directory Ranking Tool** 📁

---

## 🔍 **Overview**

The **CLI Directory Ranking Tool** is a powerful Python-based utility that allows you to **manage and track directories** accessed on your system. With this tool, you can effortlessly **navigate, query, and organize directories** based on their usage frequency, giving you an efficient way to manage your workflow. By utilizing **SQLite** for persistent storage and **rapidfuzz** for fuzzy search, this tool provides an intuitive way to access your most used directories with ease. 

> **Features include**: adding, removing, searching, ranking, and viewing directory visit counts!

---

## ✨ **Features**

### 1. **Add Directories**
   - Easily add directories to the database for quick access.
   - Each added directory gets initialized with a **visit count of 0**.

### 2. **Remove Directories**
   - Remove any directory from the system database with a single command.
   - Ensure only relevant directories are stored.

### 3. **Query Stored Directories**
   - View a complete list of all directories stored in the database.
   - Perfect for quickly checking and managing your directory records.

### 4. **Jump to Directory**
   - **Search for a directory** using a keyword.
   - The system will find the **best match** based on its usage and **jump** to it, increasing its ranking.
   - Fast, efficient, and powered by **fuzzy search**.

### 5. **List Rankings**
   - Display all directories sorted by their **visit count**.
   - Easily identify the most frequently used directories and stay productive.

### 6. **Automatic Ranking System**
   - Every time you access a directory, its **visit count is incremented**.
   - The system **automatically ranks** directories based on the frequency of visits.

### 7. **Persistent SQLite Database**
   - All directory paths and their visit counts are stored in an **SQLite database**.
   - Your data is **persisted** across sessions, ensuring continuity.

---

## ⚙️ **How It Works**

The CLI Directory Ranking Tool relies on Python and SQLite to manage directories effectively. Here's how the system works:

### **Utility Functions**

- **`is_valid_directory(path)`**:
   - Verifies if the given path is a valid directory.

---

### **Database Functions**

- **`init_db()`**:
   - Initializes the SQLite database and creates the `directories` table (if not already exists).

- **`get_connection()`**:
   - Opens and returns a connection to the SQLite database.

- **`update_rank(directory)`**:
   - Increases the visit count for a given directory.
   - If the directory does not exist, it is added to the database with a visit count of **1**.

- **`get_top_directory(search_term)`**:
   - Searches for the directory that best matches the provided term and is ranked the highest in terms of visits.

- **`list_rankings()`**:
   - Lists all directories sorted by their visit counts, starting with the most frequently accessed.

- **`get_all_directories()`**:
   - Retrieves all stored directories sorted by rank.

---

### **Core Functions**

- **`change_directory(target_directory)`**:
   - Changes to the specified directory if it is valid.

- **`add_directory(directory)`**:
   - Adds a new directory to the database, initializing its rank.

- **`remove_directory(directory)`**:
   - Removes the specified directory from the database.

- **`query_directories()`**:
   - Displays all stored directories for easy review.

- **`jump_to_directory(keyword)`**:
   - Finds the best matching directory based on a search keyword, ranks it, and "jumps" to it.

---

## 🎮 **Usage Guide**

### **Command Line Usage**

The tool supports the following commands, each performing a specific action:

#### 1. **Add a Directory**  
```bash
python clitools.py add /path/to/directory
