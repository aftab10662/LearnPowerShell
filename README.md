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


##Delete old log files which is specific day old.
$Now = Get-Date
$Days = "15" 
$Targetfolder = "C:\Log"
$Extension = "*.log"
$Lastwrite = $Now.AddDays(-$Days)
write-host "Last Write $Lastwrite"
Get-ChildItem $TargetFolder -include $Extension -Recurse | where { $_.LastWriteTime -gt "$LastWrite" } | Remove-Item -Force -Recurse



