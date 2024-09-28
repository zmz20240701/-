1. `sudo apt install mysql-server`
2. `sudo systemctl start mysql`
3. `sudo systemctl enable mysql`
4. 验证服务状态`sudo systemctl status mysql`
  <img width="816" alt="image" src="https://github.com/user-attachments/assets/41cf0b83-2d34-4978-bad9-0744a7a8c944">
  
5. `sudo mysql`
   
7. `CREATE USER 'newuser'@'%' IDENTIFIED BY 'password';`

9. GRANT ALL PRIVILEGES ON *.* TO 'newuser'@'%' WITH GRANT OPTION;

    
11. `FLUSH PRIVILEGES;`
    
13. `EXIT;`
    
15. 允许远程连接 `sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf`
    
17. 找到以下一行，并注释掉`bind-address = 127.0.0.1`
    <img width="663" alt="image" src="https://github.com/user-attachments/assets/eb814e9e-34f1-4b30-b4f0-ea1d5b78c884">

18. `sudo systemctl restart mysql`

19. 设置成功
