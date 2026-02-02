## Creating a Main Vault

### Objective

- **1 single global Obsidian vault**
- organized by folders (projects, training, personal…)
- synchronized via **Git**
- usable on **multiple computers**
- with **ONE unique configuration** (theme, plugins, shortcuts…)

### Cleanup

To start fresh:

- Close Obsidian
- Delete or set aside old vaults
- Choose **ONE root folder**, for example:

```
Documents/Obsidian
```

### Create the global vault structure

In the file explorer, create:

```
Documents/Obsidian/Second-Brain
```

Inside:

```
Second-Brain/
├── Projects/
├── Training/
├── Resources/
├── Journal/
```

In each folder, create a .placeholder file that will allow preserving the architecture when cloning the Git repo. The **Second-Brain** folder will be the unique vault that will serve as the Git repo and knowledge base.

### Create the Obsidian vault

- Open Obsidian
- Open folder as vault
- Select:

```
Documents/Obsidian/Second-Brain
```

### Basic Obsidian configuration

Configure now:

- theme
- language
- native plugins
- community plugins (Git, Template, Dataview later)
- shortcuts
- CSS snippets if needed Everything will be stored in:

```
Second-Brain/.obsidian/
```

### Initialize Git (**IN THE RIGHT PLACE**)

Open a terminal **in the Second-Brain folder**:

```
cd "Documents/Obsidian/Second-Brain"
git init
```

Verify there are no errors:

```
git status
```

### Create the .gitignore (essential)

At the root of the vault, create the file:

```
.gitignore
```

Recommended content:

```
.obsidian/cache
.obsidian/workspace.json
.obsidian/workspace-mobile.json
```

### First commit

Still in ==Second-Brain==:

```
git add .
git commit -m "Initialize global Obsidian vault"
```

### Remote repository (GitHub)

- Create a private repo on GitHub For example:

```
second-brain-obsidian
```

⚠️ Don't initialize anything on the GitHub side

- Then in the terminal:

```
git remote add origin git@github.com:YOUR-ACCOUNT/second-brain-obsidian.git
git branch -M main
git push -u origin main
```

### Install and configure Obsidian Git

In Obsidian:

- Settings -> Community plugins
- Install **Obsidian Git**
- Recommended configuration:
    - Auto commit: ON
    - Interval: 10 min
    - Auto pull on startup
    - Autopush on commit
    - Message: ==Auto-save Obsidian==

### Using on another computer

On another computer:

- Create a folder (Obsidian for example) on the computer
- Open a Git Bash in this folder
- Clone the GitHub repo

```
git clone git@github.com:YOUR-ACCOUNT/second-brain-obsidian.git
```

Then:

- Open Obsidian
- Open folder as vault
- Select the cloned folder

### Golden rules (to respect)

- Only one vault open at a time
- No simultaneous modifications on 2 machines
- Let Obsidian Git finish its commits
- Private repo if personal notes
