# How to connect datacube folder with your github account
note: replace everything in {this breackets} to your own credential/file names

## To download course notebooks:
1. Create an empty folder "WS21_Datacube_course"
2. Open Terminal (File->New->Terminal)
3. Navigate to the folder

```
cd work/data/{github_account_name}/WS21_Datacube_course
```

4. Initiate a git repository
```
git init
git clone https://github.com/eo2cube/datacube_eagles.git
```

## To connect a private repository with your own project:
1. Create a new folder "my_project" 
2. Open Terminal (File->New->Terminal)
3. Navigate to the folder

```
cd work/data/{github_account_name}/my_project
```

4. Initiate git repository 

```
git init
```

5. Generate ssh-keys

```
git config user.name "{your_username}"
git config user.email "{your_email_address_on_github}"
ssh-keygen -t ed25519 -C "{again-your-email@email.com}"
```

- Enter file in which to save the key (/home/datacube/.ssh/id_ed25519)":
```
/home/datacube/.ssh/id_ed25519_{your_name}
```
- Enter passphrase (empty for no passphrase): "Press Enter"

6. Navigate to your ssh-key

- Open new Terminal

```
cd /home/datacube/.ssh/
cat id_ed25519_{your_name}
```
- Copy this key

7. Add ssh-key to your github account

- Go to github.com/{your_account_name}
- Log into your github account , navigate to "Settings":
- On your left menu find "SSH and GPG keys"
- Press "New SSH key" on the top right
- Paste your ssh-key

8. Create github repository

- Navigate to "Your Repositories" in your account
- Create the new repository "WS21_DataCube_project"

9. Add your github repository

- Go back to Terminal, where you initiated your github repository and run:

```
ssh-add /home/datacube/.ssh/id_ed25519_{your-name}
git remote set-url origin git@github.com:{your_github_name}/WS21_DataCube_project.git
```

10. Basic git commands

- git add
- git commit -m "first commit"<br/>
- git push