# Setting Up GitHub SSH Keys and Access

- ## Step 1: Generate an SSH Key
For both Ubuntu and Windows, you can use the same command to generate an SSH key:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
### Explanation:
**```-t ed25519```: Specifies the key type (Ed25519 is preferred for better security).**

**```-C``` ```"your_email@example.com"```: Adds a comment (usually your email) to help identify the key.**

**Follow the prompts to save the key. ```Press Enter to accept the default location (~/.ssh/id_ed25519)```.**

- ## Step 2: Copy the Public Key
### __For Ubuntu:__
```bash
cat ~/.ssh/id_ed25519.pub | xclip -selection clipboard
````
### __For Windows (PowerShell):__

```bash
Get-Content C:\Users\Acer\.ssh\id_ed25519.pub | Set-Clipboard
```

#### This copies the public key (id_ed25519.pub) to your clipboard so you can paste it into GitHub.


- ## Step 3: Add the SSH Key to GitHub
  
Log in to your **GitHub** account.

Navigate to ```Settings``` > ```SSH and GPG keys``` > ```New SSH key```.

Paste your ```public key``` from the clipboard.

Give the key a meaningful title and save it.

- ## Step 4: Configure Your SSH Config File
To create the config file in the .ssh directory without any extension (e.g., .txt), you can use the following commands:

### __For Ubuntu/Linux:__

```bash

touch ~/.ssh/config
```

##### This creates an empty file named config in the .ssh directory.

### __For Windows (PowerShell):__

```bash
New-Item -Path $HOME\.ssh\config -ItemType File -Force
```

### Edit the ~/.ssh/config file to simplify SSH usage for multiple GitHub accounts. 
  Add the following:

```bash
Host github.com
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519
  IdentitiesOnly yes

## You can add as many as profiles , just rename the file name of SSH key everytime you create a new one
Host github-spam
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_ed25519_spam
  IdentitiesOnly yes

```
- #### Explanation:
- 
Each Host block defines how SSH connects to a specific service.

The IdentityFile specifies which private key to use for authentication.

For ```Ubuntu```: The file is located at ```~/.ssh/config```.
For ```Windows```: It's located at ```C:\Users\<YourUsername>\.ssh\config```.

- ## Step 5: Test Your Connection
  
### To check How many profiles are there

```bash
notepad $HOME\.ssh\config
```
OR

```bash
nano ~/.ssh/config
```

#### Test the SSH connection for each profile using the following command:

```bash

ssh -T github.com
```
OR
```bash
shh -T github-spam

## use As per the name given in the config file for the host
```

#### Expected Output:

```bash
Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.
```

- ## Step 6: Set Up a Git Repository
  
#### Initialize Git:

```bash
git init
```
**Add Remote Repository:**

Using a Custom Profile Alias (from SSH Config File):

If you’ve set up an alias in your ```~/.ssh/config``` file (e.g., ```github-spam```), which represents a specific GitHub account, use the following command:

```bash
git remote add origin git@github-spam:<username>/<repository>.git
```

Here, github-spam is the profile alias you defined for that specific account in your SSH config file. 

Replace <username> and <repository> with the actual GitHub username and repository name.

EXAMPLE:

```bash
git remote add origin git@github-spam:apsitv27/testing.git
```

- ## Set Local User Config: Set the repository-specific username and email to ensure commits are attributed correctly:

```bash
git config --local user.name "Your_UserName"
git config --local user.email "your_email@example.com"
```

- ## Step 7: Push Code to GitHub
  
Add and commit changes:

``` bash
git add .
git commit -m "Initial commit"
```
Push the changes:

```bash
git push -u origin main
```

IF you still face any errors refer to [official docs](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) or [Chat-gpt](https://chat.com) 🤟

