# dyTextEditor
A command-line based lightweight text editor written in C, focusing on system-level file handling and memory management.
Initially inspired by the core behavior of editors like vim, this project aims to implement a functional text editing tool from scratch.

## Current Features Implemented (as of 2025. 06)


### ✅ File Handling


  - editorOpen()

    - Opens an existing file in read/write mode(r+)
    - If the file doesn't exist, prompts the user to create a new one
    - Handles file creating safely with user confirmation
   
  - loadFile()

    - Read the file line by line using a custom myFgets() function (based on fread())
    - Each line is stored as a dynamically allocated string
    - The text buffer is a dynamically growing array of char*
    - Efficient memory allocation with doubling strategy for buffer resizing
   
  - viewFile()

    - Displays all loaded lines in the terminal
    - Shows current cursor line separately at the end

  - initEditor()

    - Initializes editor configuration values
    - Resets cursor position, row count, and screen size, and etc.
   
  - getCommand()

    - captures user input (arrow keys, editing commands, and line numbers) and parses in into a COMMAND struct.
   
      - Line Navigation
          - Arrow Keys: ↑ (Up), ↓ (Down)
          - Page Navigation: PgUp, PgDn
          - Line Number input
      - Editing Commands
          - A: Append a new line
          - I: Insert a line
          - D: Delete a line
          - E: Edit a line
          - Q: Quit editor (case-insensitive)

🛠 The command handling logic is central to user interaction in the CLI version. It will be expanded in GUI version logic later.

---


### ✅ Text Editing


  - appendLine()

    - Appends a new line to the end of the text buffer stored in the editor
    - Handles memory allocation and checks if capacity to be expanded


---


### ✅ Navigation


  - moveLine()

    - Move the cursor to a specific line or navigate up/down by line or page


  ### ⏩ Next Steps (will be continuously updated)
  - Implement insert/edit/delete line functionality
  - save changes to disk
  - navigation via arrow keys (CLI interaction)
  - Eventually consider a move toward GUI
