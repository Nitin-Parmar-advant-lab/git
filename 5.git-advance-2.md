## git commit --amend
- this is very importand to adding file to the last commit or modify the message of last commit
- remamer that after modificaion it will rewrite the hash, (don't use in public branch)

Changing the Last Commit Message (inline)
```
git commit --amend -m "Your new corrected commit message"
```
Adding Forgotten Files to the Last Commit
```
git add forgotten_file.txt
```
then this if don't want to edit message 
```
git commit --amend --no-edit
```
If you want to update the message as well
```
git commit --amend -m "New message including the added file"
```

---

Eddit message or commit by vim editor (Hard and long way)
```
git commit --amend
```
this will open vim editor
1. Start Typing: Press i on your keyboard (this enters "Insert Mode"). You can now type and edit the text.
2. Stop Typing: Press Esc (this goes back to "Normal Mode").
3. Save and Quit: Type :wq and press Enter.
    - : starts a command.
    - w stands for "write" (save).
    - q stands for "quit".

## squash
merging multiple commits into one commit.
it is also very important one

- it use Interactive Rebase to merge commits into one commit 

how many commits back you want to squash. If you want to combine the last 3 commits, run this command in PowerShell:
```
git rebase -i HEAD~3
```
(-i stands for interactive. HEAD~3 means "the last 3 commits".)

this will open vim editor  
To squash them, you leave the top one as pick and change the others to squash (or just s).  
or you can delete whole line by this: first esc from insert and the click two time d (dd) to the line that you want to delete  

then save the changes by `:wq`, press enter and this will open new vim editor for editing message 

reamamber all the line which `#` infront will be commented and not visible, so make changes according to your required message 

and then save the changes by `:wq`

# SSH
### Phase 1: Generate the Key Pair
Open PowerShell.
Run the generator:
PowerShell
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```
Action: Press Enter to all prompts (Save location and Passphrase) to keep it simple.

Result: Two files are created in C:\Users\YourName\.ssh\.

*id_ed25519 (Your Private Key — Keep this secret).*

*id_ed25519.pub (Your Public Key — This goes to GitHub).*

### Phase 2: Start the SSH Agent
Windows has a built-in "manager" (the Agent) that holds your keys so you don't have to type passwords every time.

Open PowerShell as Administrator.
Enable and start the service:
```
Set-Service ssh-agent -StartupType Automatic 
```
```
Start-Service ssh-agent  
```
### Phase 3: Add Your Key to the Agent
This tells your computer to actually use the key you generated.
In your normal PowerShell terminal, run:

```
ssh-add "$HOME\.ssh\id_ed25519"
```
### Phase 4: Add the Key to GitHub
Now you give GitHub the "lock" (Public Key) that matches your "key" (Private Key).

Copy the public key text to your clipboard:

```
cat $HOME\.ssh\id_ed25519.pub | clip  
```
Go to GitHub Settings → SSH and GPG keys → New SSH Key.

Paste the text and save.

### Phase 5: Testing the Connection
This confirms that the "lock" on GitHub and the "key" on your PC work together.

Run the test command:
```
ssh -T git@github.com
```
Expected result: "Hi [Username]! You've successfully authenticated..."