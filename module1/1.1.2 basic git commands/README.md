# Basic Git Commands

## Hands-on Git Project: Collaborative Website Development with Git and GitHub

In this mini project, we'll create a step by step project to simulate the workflow of Tom and Jerry using Git and Github. This hands-on project will include installation of Git setting up a GitHub repository, creating branches, making and merging those changes back into the main branch.

## part 1: Setup and Initial Configuration
1. **Install Git**: Download and install Git from [git-scm.com](https://git-scm.com/).
![Git Installation](assets/image1.png)
2. Create a GitHub repository:
    - Sign up or log in to **GitHub**.
    - Click on the **New** button to create a new repository.
  ![Create Repository](assets/image2.png)
    - Name  your repository (e.g., `tom-and-jerry-website`) and initialize it with a README file.
    - Click on **Create repository**.
  ![Repository Created](assets/image3.png) 
3. **Clone the repository**
   - Open your repository on GitHub.
   - Click on the **Code** button and copy the HTPPS URL.
  ![Clone Repository](assets/image4.png)
    - Open your terminal or command prompt - Create a folder named **git-project** in the folder where you are storing all **DAREY.IO** realted work. For example in the Desktop folder on your laptop, you may create called **darey-training**
  ![Create Folder](assets/image5.png)
    - clone (Download) the repository from GitHub using the command:
      ```bash
      git clone https://github.com/ifobook/ai_startup_website.git
        ```
    ![Cloned Repository](assets/image6.png)
    - Navigate into the repository you cloned:
      ```bashd
      cd ai_startup_website
      ```
      - Create an empty file **"index.html"** in the repository folder:
      ```bash
      vim index.html
      ```
        - Add the following content to the file: "This is the Admin creating an index.html file for Tom and Jerry."
  ![Edit Index File](assets/image8.png)
  ![Save and Exit](assets/image7.png)

     - Check changes has not been staged yet:
    ```bash
    git status
    ```
     - Stage the changes:
    ```bash
    git add index.html
    ```
    - Check the status again to confirm the changes are staged:
    ```bash
    git status
    ```
  ![Stage Changes](assets/image9.png)
    - Commit the changes with a message:
    ```bash
    git commit -m "Add index.html file"
    ```
    - Push the changes to GitHub:
    ```bash
    git push origin main
    ```
    ![Push Changes](assets/image10.png)
    ![Push Confirmation](assets/image11.png)

  This sends commits from your man branch on your laptop to GitHub (remote repository).


  ## Part2: Simulating Tom and Jerry's Work 
  To simulate both Tom and Jerry working on the same laptop, you'll switch between two branches, making changes as each character.
  1. Tom's work:
   - Navigate to the project directory you just cloned.
```bash
  cd ai_startup_website
  ```
  This moves you into the folder containing the cloned GitHub repository on your local machine. It's like stepping into the project's workspace.
  ![Create Tom's Branch](assets/image12.png)
  - Check the current branch: THis shows you a list of all branches in the repository, with an asterisk (*) next to the current branch.
```bash
  git branch
```
![Current Branch](assets/image13.png)

    - Create a new branch for Tom's work:
```bash
    git checkout -b update-navigation
``` 
![Create Tom's Branch](assets/image14.png)
  This command creates a new branch called `update-navigation` and switches to it. 
  
  - Check the branch again to confirm you are on the new branch:
```bash
    git branch
```
![Check Branch](assets/image15.png)
Running git branch again shows that you are now on the `update-navigation` branch, indicated by the asterisk (*).

Add content to the `index.html` file:
```bash
    vim index.html
```
![Edit Index File](assets/image16.png)
![Save and Exit](assets/image17.png)
This simulates Tom's contribution to the project. This text represents the work he's doing on the navigation bar. In the real world, this will be an actual software code.
- Check changes has not been staged yet:
```bash
    git status
```
![Check Status](assets/image18.png)
At this point, Git informs you that the `index.html` file has been modified but not yet staged for commit.
- Stage the changes:
```bash
    git add index.html
```
This tells Git to prepare the changes in `index.html` for committing. It's like saying, "I'm ready to save my work."

- Check the status again to confirm the changes are staged:
```bash
    git status
```
![Check Staged Changes](assets/image19.png)

- Commit the changes with a message:
```bash
    git commit -m "Tom: Update navigation bar"
```

Now, after staging changes and records them in the repository's history with a message describing what was done. This commit is a milestone, making a specific point in the project's development.
![Commit Changes](assets/image20.png)

- Push the changes to GitHub:
```bash
    git push origin update-navigation
```
![Push Changes](assets/image21.png)
This sends Tom's changes from the `update-navigation` branch on your laptop to the remote repository on GitHub. It's like sending a letter to the project's central hub, where everyone can see it.
After completing Tom's work, you can switch back to the main branch:
- switch back to the main branch,
- Create a new branch for Jerry's work,
- make changes, and then 
- Stage, commit, and push those changes.
```bash
    git checkout main
```
This command switches you back to the main branch, where you can start Jerry's work.
![Switch to Main Branch](assets/image26.png)

![Create Jerry's Branch](assets/image23.png)

![Check Current Branch](assets/image25.png)
![image](ssets/image27.png)
![Edit Index File for Jerry](assets/image24.png)

Open the `index.html` file in your text editor:
```bash
    vim index.html
```
![Edit Index File](assets/image28.png)
stage Jerry's changes:
```bash
    git add index.html
```
Commit Jerry's changes with a message:
```bash
    git commit -m "Jerry: Add footer section"
```
Push Jerry's changes to GitHub:
```bash
    git push origin update-footer
```
![Push Jerry's Changes](assets/image29.png)
This command sends Jerry's changes from the `update-footer` branch on your laptop to the remote repository on GitHub. It's like sending a letter to the project's central hub, where everyone can see it.
