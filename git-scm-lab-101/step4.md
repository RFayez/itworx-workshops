Step 4 - Git Commit

Once a file has been added to the staging area it needs to be committed to the repository. The command git commit -m "commit message" moves files from staging to the repository and records the time/date, author and a commit message that can be used to add additional context and reasoning to the changes such as a bug report number.

Only changes added to the staging area will be committed, any files in the working directory that have not been staged will not be included.
Task

Use git commit -m "<commit message>" to commit the staged file.
Protip

Each commit is assigned a SHA-1 hash which enables you to refer back to the commit in other commands.