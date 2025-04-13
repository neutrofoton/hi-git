# Remote
``` bash
git remote
git remote -v # show git remote url

git remote add origin "url://...." # add remote origin url
git remote rm origin # remove remote origin

# show all detail info for origin: url, branches etc
git remote show origin
```

- **Question :** 
    how to push a cloned git repository to another empty git repository 
    <br/>
    
  **Answer :**  
  
    - Clone the source repository (if not already cloned)
        ```bash
        git clone https://github.com/source-user/source-repo.git
        cd source-repo
        ```
    - Add the new remote (empty repository)
        ```bash
        git remote add new-origin https://github.com/your-user/target-repo.git
        ```

    - Push all branches to the new repository
        ```bash
        git push new-origin --all
        ```

    - Push tags (if needed)
        ```bash
        git push new-origin --tags
        ```

    - (Optional) Set the new remote as default origin
        ```bash
        git remote remove origin
        git remote rename new-origin origin
        ```