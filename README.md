# dev_ODBC
Deployment and Configuration of ODBC in RH7.x

#### Set Environment Variables for SAS
`$export ODBCSYSINI=/etc`<br/>

##### Using FreeTDS for SQL Server Connectivity - add to /etc/freetds.conf
```
[wdcsqlaw02]
host = 10.X.x.x
port = 1433
tds Version = 7.1
try domain login = yes
use ntlmv2 = yes
debug flags = 0x80
#dump file = /tmp/tdsdump_wdcsqlaw02.txt
client charset = UTF-8
```

#### Set Configurations for PostgreSQL
