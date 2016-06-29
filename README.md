#Learning PowerShell basic commands

##Secure copy from local to remote machine and connect to remote machine using ssh(secure shell) 
* `scp -r /c:\temp\myapp mymachine@aftabansari.cloudapp.net:~/myapp`

* `ssh aftabansari.cloudapp.net`


##Get stopped services and export to CSV files.
* `ise`
* `get-service`
* `get-service | where-object status -eq 'stopped'`
* `get-service | where-object status -eq 'stopped' | export-csv c:\scripts\service-stopped.csv`
* `get-service | where-object status -eq 'stopped' |select-object Status,Name,DisplayName| export-csv c:\scripts\service-stopped.csv`



