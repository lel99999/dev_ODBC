# dev_ODBC
Deployment and Configuration of ODBC in RH7.x

#### Set Environment Variables for SAS
`$export ODBCSYSINI=/etc`<br/>
##### FreeTDS Config in ODBC.ini
```
[wdcsqlaw02]
Description=/usr/lib64/libtdsodbc.so
Language=us_english
Database=ODBCDefaultDB
#Encryption=False
Driver = FreeTDS
#Driver=/usr/lib64/libtdsodbc.so
Servername=<Hostname>
Trace=True
TDS_Version=7.1
UseNTLMv2=True
#Port=1433
Client Charset = UTF-8
```

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

#### Set Configurations for PostgreSQLin ODBC.ini (SAS Driver)
```
[postgresdb01]
Protocol=8.4
Description=/usr/pgsql/lib/sas_psqlodbc.so
Database=cfpb
Servername=wdcctspml01
Driver=/usr/pgsql/lib/sas_psqlodbc.so
SSLmode=require
Port=5432

```
