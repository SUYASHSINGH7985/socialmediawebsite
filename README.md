# CLI Directory Ranking Tool

This project is a command-line tool that manages directories and ranks them based on how frequently they are accessed. The tool uses an SQLite database to store directories and their visit counts, allowing users to add, remove, query, jump to, and list directories with a ranking system.

## Features

- **Add Directories**: Add a directory to the database for future access.
- **Remove Directories**: Remove a directory from the database.
- **Query Directories**: List all directories stored in the database.
- **Jump to Directory**: Search for a directory based on a keyword and jump to the best match, increasing its rank.
- **List Rankings**: List all directories sorted by the number of visits (ranking).
- **Ranking**: The tool keeps track of visit counts (ranks) for each directory, increasing the rank when accessed.

## Functions

### Utility Functions

- `is_valid_directory(path)`: Checks if the provided path is a valid directory.

### Database Functions

- `init_db()`: Initializes the SQLite database and creates a table to store directory paths and their visit counts.
- `get_connection()`: Returns a connection to the SQLite database.
- `update_rank(directory)`: Updates the rank (visit count) of a directory in the database.
- `get_top_directory(search_term)`: Returns the most visited directory matching a search term.
- `list_rankings()`: Lists all directories sorted by their visit counts.
- `get_all_directories()`: Retrieves all stored directories, sorted by the most visited.

### Core Functions

- `change_directory(target_directory)`: Changes to a specified directory if it's valid.
- `add_directory(directory)`: Adds a valid directory to the database.
- `remove_directory(directory)`: Removes a directory from the database.
- `query_directories()`: Lists all stored directories.
- `jump_to_directory(keyword)`: Finds and returns the best matching directory based on a keyword.

### Main CLI Function

- `main()`: The entry point of the CLI tool, which accepts commands such as `add`, `remove`, `query`, `jump`, and `list-rankings`.

## Usage

### Command-Line Usage

The tool accepts the following commands:

- **add**: Add a directory to the database.
    ```bash
    python clitools.py add /path/to/directory/
    ```

- **remove**: Remove a directory from the database.
    ```bash
    python clitools.py remove /path/to/directory/
    ```

- **query**: List all stored directories.
    ```bash
    python clitools.py query
    ```

- **jump**: Search for a directory and jump to the best match.
    ```bash
    python clitools.py jump keyword
    ```

- **list-rankings**: List all directories sorted by the number of visits.
    ```bash
    python clitools.py list-rankings
    ```

### Example Commands

```bash
# Add a directory
python clitools.py add "C:\\Users\\Suyash"

# Remove a directory
python clitools.py remove "C:\\Users\\Suyash"

# List all directories
python clitools.py query

# Jump to a directory based on a keyword
python clitools.py jump "Suyash"

# List all rankings (sorted by visits)
python clitools.py list-rankings
