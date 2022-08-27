1)Line of code: from friend import Friend
* Restarting with stat
Traceback (most recent call last):
  File "/Users/eric/Desktop/CodingDojo/Assignments/Python/flask_mysql/first_flask_mysql/server.py", line 4, in <module>
    from friend import Friend
ModuleNotFoundError: No module named 'friend'
<!-- friend is nested inside more folders using modularization correct path should read:
from flask_app.models.friend import Friend -->

2)line of code: from mysqlconnection import connectToMySQL
Traceback (most recent call last):
  File "/Users/eric/Desktop/CodingDojo/Assignments/Python/flask_mysql/first_flask_mysql/server.py", line 4, in <module>
    from flask_app.models.friend import Friend
  File "/Users/eric/Desktop/CodingDojo/Assignments/Python/flask_mysql/first_flask_mysql/flask_app/models/friend.py", line 2, in <module>
    from mysqlconnection import connectToMySQL
ModuleNotFoundError: No module named 'mysqlconnection'
<!-- mysqlconnection is nested inside more folders using modularization correct path should read:
from flask_app.config.mysqlconnection import connectToMySQL -->

3)Error:
connection = pymysql.connect(host = 'localhost',
File "/Users/eric/.local/share/virtualenvs/first_flask_mysql-nIHEQXrl/lib/python3.10/site-packages/pymysql/connections.py", line 353, in __init__
self.connect()
File "/Users/eric/.local/share/virtualenvs/first_flask_mysql-nIHEQXrl/lib/python3.10/site-packages/pymysql/connections.py", line 633, in connect
self._request_authentication()
File "/Users/eric/.local/share/virtualenvs/first_flask_mysql-nIHEQXrl/lib/python3.10/site-packages/pymysql/connections.py", line 907, in _request_authentication
auth_packet = self._read_packet()
File "/Users/eric/.local/share/virtualenvs/first_flask_mysql-nIHEQXrl/lib/python3.10/site-packages/pymysql/connections.py", line 725, in _read_packet
packet.raise_for_error()
File "/Users/eric/.local/share/virtualenvs/first_flask_mysql-nIHEQXrl/lib/python3.10/site-packages/pymysql/protocol.py", line 221, in raise_for_error
err.raise_mysql_exception(self._data)
File "/Users/eric/.local/share/virtualenvs/first_flask_mysql-nIHEQXrl/lib/python3.10/site-packages/pymysql/err.py", line 143, in raise_mysql_exception
raise errorclass(errno, errval)
pymysql.err.OperationalError: (1045, "Access denied for user 'root'@'localhost' (using password: YES)")
<!-- update password to match server password in MySQL Workbench -->