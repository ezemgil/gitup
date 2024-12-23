# Gitup
GitUp is a simple Bash script to streamline common Git operations: `status`, `add`, `commit`, and `push`.
If a `git push` operation fails, the script includes a rollback mechanism to safely revert the repository to its previous state.

## Features
- Automates the process of adding, committing, and pushing changes.
- Displays the current repository status in a concise format.
- Automatically generates a default commit message when none is provided.
- Includes a rollback mechanism to undo commits and staging if the push operation fails.
- Designed to work securely, without exposing sensitive credentials.

## Usage
### Prerequisites
- Ensure Git is installed on your system.
- Configure your remote repository and credentials (e.g., using SSH keys or a credential helper).

### Installation
1. Clone this repository or download the `gitup` script.
2. Make the script executable:
    ```bash
    chmod +x gitup
    ```
### Run the Script
To use Gitup, navigate to the root directory of your Git repository and run:
```bash
./gitup "Your commit message here"
```
- If you omit the commit message, the script will generate a timestamped default message.
- The script will execute the following steps in sequence:
    1. Display the repository status.
    2. Stage all changes.
    3. Commit the changes.
    4. Push the changes to the remote repository.

## Rollback Mechanism
If `git push` fails, the script automatically:
1. Undoes the last commit, keeping the changes staged.
2. Unstages all changes to return them to their original state.

Your data is safe, and you can reattempt the push after resolving any issues.

## Credits
The idea for this script was inspired by a TikTok video from [@sec2john](https://www.tiktok.com/@sec2john/video/7434185994594684193).
