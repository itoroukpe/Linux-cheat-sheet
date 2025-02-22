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
18. `755`  
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

These answers are all **Ubuntu-specific**, but most work on other **Debian-based Linux distributions** too. Let me know if you want any modifications or explanations! 🚀
