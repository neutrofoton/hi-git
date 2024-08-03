#   CASES 

### Steps excluding files and adding to gitignore for the files that already in git

 
1. tambahkan file atau folder atau extension ke .gitignore
2. jalankan 
    ```bash 
    git rm --cached XXXX. 
    ```

   Contoh :
   ```bash 
   git rm --cached src/directories/Database/*
   git rm --cached -rf src/directories/.idea
    ```

3. maka file2 tsb akan masuk ke untracked. 
4. jalankan git add .
5. commit changes pada .gitignore
6. push
7. coba edit file yg diexclude
8. <code> git status </code>
9. seharusnya file yg diexclude tsb tidak masuk dalam stage area

```