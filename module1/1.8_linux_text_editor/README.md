# linux Text Editor
A linux text editor is a software application specifically designed for creating, modifying, and managing text files on a linux-based operating system. Text editors play a crucial role in the linux environment, providing a means for users to interact with and manipulate plain text files, configuration files, scripts, and other text-based documents.

There are various text editors available in the linux ecosystem, each with its own set of features and user interface, let's dive in to the use of some text editors.

# VIM Text Editor
The linux Vim text editor, short for "Vi improved," is a powerful and versatile text editing tool deeply ingrained in the Unix and Linux ecosystems. Vim builds upon the foundation of the original Vi editor, offering an extensive set of features, modes, and commands that empower users to manipulate text efficiently. While Vim has a steeper learning curve compared to simpler editor like nano, its capabilities make it a favourite among tech professionals and everyone working extensively with text files.

## Working With VIM Editor
``` bash
vim exercise.txt
```
The command above created and opened the exercise.txt file even when it does not exist. Then it opens the file up so that i can start writing into it. It is just like opening up Notepad file on Windows.

![vim editor](assets/vim.png)

- **Enter Insert Mode** to edit the file.
    - Press `i` to enter Insert mode.
    - Type the following text into the file: "Hello, this is a vim hands-on project. Welcome to Darey.io."
  ![vim hello](assets/vimhello.png)

- **Moving Around:** Navigate through the text using the arrow keys or h (left), j (down), k (up), and l (right).
- **Deleting a Character:** Press `esc` on your keyboard to exit the `insert mode`. Position the cursor on a charcter you want to delete and press x.
  ![vim delete character](assets/deletecharacter.png)
  
- **Deleting a Line:** To delete an entire line in the file, ensure that you are not in the `insert mode`. If you are in the insert mode, simply press the `esc` key as above. Then, place the cursor on a line, and press **d** twice on your keyboard to delete the entire line.
  ![vim delete line](assets/deleteline.png)
  
- **Undoing Changes:** Make a change (add or delete text) in insert or normal mode, then press Esc to enter Normal Mode and press **u** to undo the last change
  ![vim undo](assets/undo.png)
  
- **Saving Changes:** After you have finished writing into the file, press `esc`, then type **:wq** and press Enter. This will save the file. `w` means **write** and `:q` means **quit** which basically quits the vim mode and returns back to the terminal.
- **Quitting Without Saving:** Incase you do not intend to save the file, simply pre `esc`, then type **:q!** and press Enter to quit without saving changes.
  ![vim quit](assets/quit.png)

# Nano Text Editor
Among linux text editors, Nano stands out as a user-friendly and straightforward tool, making it an excellent choice for users who are new to the command line or those who prefer a more intuitive  editing experience. Nano serves as a versatile and lightweight text editor, ideal for performing quick edits, writing scripts, or making configuration changes directly from the command line. Its intuitive command set simplifies text manipulation tasks, allowing users to navigate through files, insert or delete text, and save changes effortlessly. Nano's ease of use extends to its keyboard shortcuts, making it accessible even to those unfamiliar with intricate command sequeences. With Nano, user can focus on the content of their text files without the distraction of a complex interface, making it a go-to choice for a wide range of users, from biginners to experienced Linux enthusiasts.

## Working With Nano Editor
- **Opening a File:** named "nano_project.txt" using the following command
```bash
nano nano_file.txt
```
The above command will enter into the Nano editor interface
![nano text editor](assets/nano.png)
- **Entering and Editing Text:** Type a few lines of text into the file. Nano has a simple interface, and you can start typing immediately.
![nano text editor](assets/nanotext.png)
  
- **Saving Changes:** Save your changes by pressing `ctrl` + `o`. Nano will prompt you to confirm the filesname; press `Enter` to confirm.
  ![nano confirm saving](assets/nanoconfirm.png)
- **Exiting Nano:** If you wish to exit nano without saving the file, simply press `ctrl` + `x`. If you have unsaved changes, Nano will prompt you to save before exiting.
  ![exit nano editor ](assets/nanoexit.png)
- **Opening an Existing File:** Open an existing file (if available) using the following command:
  ```bash
  nano existing_file.txt
  ```
  Navigate through the file using arrow keys. Write data, then save the file content.
  ![nano file open](assets/nanoupdate.png)
  