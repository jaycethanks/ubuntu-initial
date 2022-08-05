如果没有设置密码先设置密码：

```bash
$ sudo mysql_secure_installation
```

根据提示，如果是首次操作，会询问密码设定规则：

```bash
Output
Securing the MySQL server deployment.

Connecting to MySQL using a blank password.

VALIDATE PASSWORD COMPONENT can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD component?

Press y|Y for Yes, any other key for No: Y

There are three levels of password validation policy:

LOW    Length >= 8
MEDIUM Length >= 8, numeric, mixed case, and special characters
STRONG Length >= 8, numeric, mixed case, special characters and dictionary                  file

Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG:
 2
```





修改为简单密码：

先查看密码验证规则：

```bash
#登入 mysql
$ mysql -u root -p

mysql> SHOW VARIABLES LIKE '%validate%';
+--------------------------------------+-------+
| Variable_name                        | Value |
+--------------------------------------+-------+
| innodb_validate_tablespace_paths     | ON    |
| validate_password.check_user_name    | ON    |
| validate_password.dictionary_file    |       |
| validate_password.length             | 8     |
| validate_password.mixed_case_count   | 1     |
| validate_password.number_count       | 1     |
| validate_password.policy             | LOW   |
| validate_password.special_char_count | 1     |
+--------------------------------------+-------+
```

然后通过 `SET GLOBAL` 修改这些规则

```bash
# mysql>
SET GLOBAL validate_password.LENGTH = 4;
SET GLOBAL validate_password.policy = 0;
SET GLOBAL validate_password.mixed_case_count = 0;
SET GLOBAL validate_password.number_count = 0;
SET GLOBAL validate_password.special_char_count = 0;
SET GLOBAL validate_password.check_user_name = 0;
ALTER USER 'user'@'localhost' IDENTIFIED BY 'pass';
FLUSH PRIVILEGES;
```

> ALTER USER 'root'@'localhost' IDENTIFIED BY '1234';