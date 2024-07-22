# Build Site Using al-folio

## Steps

1. Get the code
  
    ```bash
    git remote add upstream https://github.com/alshedivat/al-folio.git
    git fetch upstream
    git merge v0.12.0
    git branch -m old
    git checkout --orphan=main
    git branch -D old
    ```
