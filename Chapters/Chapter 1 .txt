# 📘 Chapter 1: Introduction to Databases and Oracle 19c

## 🎯 Objective:
Understand what a database is, what Oracle is, and how Oracle 19c fits into the world of enterprise systems.

---


## ✅ 1. What is a Database?

A database is a structured collection of data that can be easily accessed, managed, and updated.

### Example:
Think of a school register:
- Student ID
- Name
- Class
- Marks

This data is stored in a table, which is part of a database.

There are two main types of databases:

----------------------------------------------------------------------------------------------------
| Type | Description                                                                               |
|------|-------------------------------------------------------------------------------------------|
| **Relational (RDBMS)** | Data organized in tables with relationships (Oracle, MySQL, SQL Server) |
| **Non-relational (NoSQL)** | Flexible schema (MongoDB, Cassandra)                                |
----------------------------------------------------------------------------------------------------

---


## ✅ 2. What is Oracle?

Oracle Database is one of the most popular relational database management systems (RDBMS) in the world.

Used by large enterprises globally for mission-critical applications like banking, healthcare, telecoms, and more.

### Why Learn Oracle?
- High demand in job market
- Powerful features (security, scalability, performance)
- Used in production environments worldwide

---

## ✅ 3. Oracle Instance vs Database

Understanding the difference between these two is crucial.

-----------------------------------------------------------------------------------
| Term         | Meaning                                                           |
|--------------|-------------------------------------------------------------------|
| **Instance** | Memory structures + background processes that access the database |
| **Database** | Physical files on disk (datafiles, control files, redo logs)      |
------------------------------------------------------------------------------------


Think of it like:
- The instance is the engine of the car.
- The database is the car itself.

An instance can only mount or open one database at a time.

---


## ✅ 4. Oracle Architecture Overview

Oracle uses a complex but efficient architecture designed for high availability and performance.

### Key Components:

#### 🧠 Memory Structures:
- **SGA (System Global Area)** – Shared memory area used by Oracle instance
  - Contains buffer cache, shared pool, redo log buffer, etc.
- **PGA (Program Global Area)** – Private memory allocated per session/process

#### ⚙️ Background Processes:
- **SMON**: System Monitor (performs crash recovery)
- **PMON**: Process Monitor (cleans up failed processes)
- **DBWn**: Database Writer (writes dirty buffers to disk)
- **LGWR**: Log Writer (writes redo entries to redo log files)
- **CKPT**: Checkpoint process (updates headers when checkpoint occurs)
- **ARCn**: Archiver (copies online redo logs to archive logs)

We'll explore these in detail later.

---

## ✅ 5. Basic Oracle Terminology

----------------------------------------------------------------------
| Term | Description                                                 |
|------|-------------------------------------------------------------|
| **Tablespace** | Logical storage unit; contains datafiles          |
| **Schema** | Collection of database objects owned by a user        |
| **Segments** | Allocated space for objects like tables and indexes |
| **Extents** | Contiguous data blocks allocated to segments         |
| **Blocks** | Smallest unit of storage in Oracle (default = 8KB)    |
----------------------------------------------------------------------

We’ll use these terms often as we move forward.

---

## 🔧 Hands-On Setup: Install Oracle 19c XE on Windows

Let’s start instaling Oracle 19c XE on your Windows laptop.
 PS: we are instaling19c as it is a stable version and gives you  a better grasp on being an Oracle DBA

### Step 1: Download Oracle 19c XE

👉 [Download Oracle Database XE 19c](https://www.oracle.com/database/technologies/oracle-database-software-downloads.html#XE)

Choose:
- Oracle Database Express Edition 19c
File will be something like: `oracle-database-xe-19c-windows.zip`

---

### Step 2: Extract and Run Installer

- Extract the ZIP file
- Double-click `setup.exe`
- Follow the steps:
  - Accept license agreement
  - Choose installation directory (e.g., `C:\oraclexe`)
  - Set password for SYS and SYSTEM users (remember this!)

✅ Wait until installation finishes (~10–15 mins depending on machine speed)

---


### Step 3: Start Oracle Services

Open Services app (`services.msc`) and ensure these services are running:

- `OracleXETNSListener`
- `OracleServiceXE`

If not running:
- Right-click → Start

---

### Step 4: Connect Using SQL*Plus

Open Command Prompt and type:

```cmd
sqlplus / as sysdba

```
sysdba means the SYStem DataBase administrator
This connects you as the SYS user (super admin).


Run a basic query:

```sql
SELECT * FROM v$instance;
```

You should see output like:

```
INSTANCE_NAME    STATUS       DATABASE_STATUS
---------------- ------------ -----------------
XE               OPEN         ACTIVE
```

---

## 📝 Summary of Chapter 1

--------------------------------------------------
| Topics Covered                                 |
|-------|--------------------------------------- |
| What is a database?                      | ✅ |
| What is Oracle?                          | ✅ |
| Instance vs Database                     | ✅ |
| Oracle architecture overview             | ✅ |
| Basic terminology                        | ✅ |
| Installed Oracle 19c XE                  | ✅ |
| Connected via SQL*Plus                   | ✅ |
-------------------------------------------------
