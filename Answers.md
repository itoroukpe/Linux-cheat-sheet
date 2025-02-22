Here are the answers for all the **Linux command practice questions** on an **Ubuntu distribution**:

---

### **🔹 File Management (Creating, Deleting, Moving, Copying, Renaming)**  
1. `touch example.txt`  
2. `cp file1.txt backup/`  
3. `mv document.txt /home/user/Documents/`  
4. `mv oldfile.txt newfile.txt`  
5. `rm -r old_folder/`  
6. `ls -la /home/user/`  
7. `mkdir projects && touch projects/notes.txt`  
8. `find /home/user/Documents -name "report.pdf"`  
9. `tail -n 10 log.txt`  
10. `head -n 5 data.csv`  

---

### **🔹 File Permissions**  
11. `ls -l test.sh`  
12. `chmod 777 script.sh`  
13. `chmod -x run.sh`  
14. `rwxr-xr--` means:  
    - Owner has **read, write, execute**  
    - Group has **read, execute**  
    - Others have **read**  
15. `chown john document.txt`  
16. `chmod +x backup.sh`  
17. `chmod 644 notes.txt`  
18. `754`  
19. `chmod 700 directory_name/`  
20.  
    - `chmod 777 file.txt` → Full permissions for everyone  
    - `chmod 755 file.txt` → Only the owner can write, others can only read and execute  

---

### **🔹 File Viewing & Searching**  
21. `cat log.txt`  
22. `grep "error" server.log`  
23. `wc -l report.txt`  
24. `less bigfile.txt`  
25. `grep "failed" auth.log`  
26. `sort names.txt`  
27. `sort data.txt | uniq`  
28. `head -n 10 file.txt`  
29.  
    - `cat` displays the entire file at once  
    - `less` allows scrolling through the file  
30. `awk -F ',' '{print $2}' data.csv`  

---

### **🔹 User Management**  
31. `sudo adduser student1`  
32. `sudo deluser guest`  
33. `sudo passwd john`  
34. `groups developer`  
35. `su - admin`  
36. `sudo groupadd staff`  
37. `sudo passwd -l employee1`  
38. `last`  
39. `sudo usermod -g managers username`  
40. `sudo groupdel tempusers`  

---

### **🔹 Process Management**  
41. `ps aux`  
42. `pidof apache2` or `ps aux | grep apache2`  
43. `kill 5678`  
44. `killall firefox`  
45. `command &`  
46. `fg`  
47. `sudo systemctl restart nginx`  
48.  
    - `kill` terminates a process using its **PID**  
    - `killall` terminates all processes matching the **name**  
49. `top` or `htop`  
50. `crontab -e` → Add `0 2 * * * command_to_run`  

---

### **🔹 Package Management**  
51. `sudo apt install vim`  
52. `sudo apt remove nginx`  
53. `dpkg --get-selections` or `apt list --installed`  
54. `sudo apt update && sudo apt upgrade -y`  
55. `sudo dpkg -i package.deb`  
56. `apt show htop`  
57. `sudo apt install apache2` (equivalent of `httpd` in Ubuntu)  
58. `sudo apt autoremove`  
59. `apt search docker`  
60. `sudo apt install package_name`  

---

### **🔹 Disk Usage & Filesystem Management**  
61. `df -h`  
62. `du -sh /home`  
63. `du -sh *`  
64. `du -h data.txt`  
65. `df -T`  
66. `sudo mount /dev/sdb1 /mnt/data`  
67. `sudo umount /mnt/data`  
68. `df -h`  
69. `sudo fsck /dev/sda1`  
70. `fallocate -l 1M logfile.log`  

---

### **🔹 Bonus Questions**  
71. `systemctl list-units --type=service`  
72. `uptime`  
73. `ping google.com`  
74. `hostname`  
75. `history | tail -50`  

---

### **Using the awk command**
### **Demonstration of `awk -F ',' '{print $2}' data.csv` in Linux**
The `awk` command is a powerful text-processing tool used in Linux to extract and manipulate text from structured data files such as CSV (Comma-Separated Values) files.

---

### **Example Use Case**
Let's assume you have a CSV file called `data.csv` with the following content:

```csv
ID,Name,Age,City
1,John,25,New York
2,Alice,30,Los Angeles
3,Bob,28,Chicago
4,Eve,35,Houston
```

The **goal** is to extract the **second column (`Name`)** from this CSV file.

---

### **Command Breakdown**
```bash
awk -F ',' '{print $2}' data.csv
```
- **`awk`** → Calls the `awk` command.
- **`-F ','`** → Specifies the delimiter (field separator) as a comma (`,`).
- **`{print $2}`** → Prints the second column (`$2` refers to the second field in each row).
- **`data.csv`** → The input file to process.

---

### **Command Execution**
Run the command in the terminal:
```bash
awk -F ',' '{print $2}' data.csv
```

### **Output**
```bash
Name
John
Alice
Bob
Eve
```
---
### **Explanation**
1. **`-F ','`** tells `awk` that the input fields are separated by commas.
2. **`$2`** represents the second column in each row.
3. The command prints only the **second column**, which contains the names.

---

### **Modifications and Enhancements**
- **Skipping the header row**:
  ```bash
  awk -F ',' 'NR>1 {print $2}' data.csv
  ```
  - **`NR>1`** skips the first row (header).
  - **Output**:
    ```bash
    John
    Alice
    Bob
    Eve
    ```

- **Displaying names and ages**:
  ```bash
  awk -F ',' '{print "Name:", $2, "- Age:", $3}' data.csv
  ```
  - **Output**:
    ```bash
    Name: Name - Age: Age
    Name: John - Age: 25
    Name: Alice - Age: 30
    Name: Bob - Age: 28
    Name: Eve - Age: 35
    ```

- **Filtering only people older than 28**:
  ```bash
  awk -F ',' '$3 > 28 {print $2, $3}' data.csv
  ```
  - **Output**:
    ```bash
    Alice 30
    Eve 35
    ```

---

### **Conclusion**
This `awk` command efficiently extracts the **second column** from a **comma-separated values (CSV) file**. It can be customized further to **filter, format, and process** data dynamically.


