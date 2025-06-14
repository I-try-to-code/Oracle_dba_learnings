📘 Chapter 0: Windows CMD & Terminal Basics for Oracle DBA

## 🎯 Objective:
Learn Windows Command Prompt and basic navigation to confidently run Oracle tools and scripts.

---

## ✅ Chapter 01: Understanding the Windows Command Prompt

The Command Prompt (often called CMD) is a powerful tool in Windows used to execute commands and automate tasks.

It's where you'll interact with Oracle tools daily as a DBA.

---

### 🔍 1. How to Open Command Prompt

#### Method 1:
- Press `Windows Key + R`
- Type `cmd`
- Press Enter

#### Method 2:
- Search for “Command Prompt” in Start menu
- Right-click → Run as Administrator (important for Oracle tasks)

---

### 🔍 2. Basic Navigation Commands

---------------------------------------------------------
| Command | Description                                 |
|---------|---------------------------------------------|
| `dir`   | List files and folders in current directory |
| `cd`    | Change directory (`cd foldername`)          |
| `cd ..` | Go back one level                           |
| `cd \`  | Go to root of current drive                 |
| `cls`   | Clear screen                                |
| `exit`  | Close command prompt                        |
---------------------------------------------------------

#### Example:

```cmd
C:\Users\YourName> cd \
C:\> dir
C:\> cd oraclexe
C:\oraclexe> dir
```

---

### 🔍 3. Working with Drives

To switch drives, just type the drive letter:

```cmd
C:\> D:
D:\>
```

---

## ✅ Chapter B2: Creating and Running Batch Files (.bat)

Batch files let you automate repetitive tasks — very useful for DBAs.

### Example: Create a batch file to launch SQL*Plus

#### Step 1: Open Notepad

Type:

```batch
@echo off
echo Starting SQL*Plus...
sqlplus / as sysdba /* This logs you in as the SYStem Database Administrator
```

#### Step 2: Save As

File name:
```
start_sqlplus.bat
```

Save location:
```
C:\oracle_scripts\start_sqlplus.bat
```

(You can create this folder if it doesn't exist.)

#### Step 3: Run It

Double-click the `.bat` file, or run from CMD:

```cmd
C:\oracle_scripts\start_sqlplus.bat
```

Boom! SQL*Plus starts.

---

## ✅ Chapter B4: Practice Time – Let’s Try Real Oracle Commands

After running your `set_oracle_env.bat`, try these:

### 1. Start/Stop Database

```cmd
sqlplus / as sysdba
SQL> SHUTDOWN IMMEDIATE
SQL> STARTUP
```

### 2. Check Listener Status

```cmd
lsnrctl status
```

### 3. Start DBCA

```cmd
dbca
```

(Useful if you ever need to create another database)

---

## 📝 Summary Table

--------------------------------------
| Skill   Covered                     |
|-------|-----------------------------|
| Opening CMD                   | ✅ |
| Navigating folders            | ✅ |
| Switching drives              | ✅ |
| Using batch files             | ✅ |
| Setting environment variables | ✅ |
--------------------------------------
