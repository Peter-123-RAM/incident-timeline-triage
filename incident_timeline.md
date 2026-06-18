Chronological Timeline

UTC Time| Source| Event| Classification| Evidence
08:15:04| auth.log| Failed SSH login for invalid user admin| Suspicious| auth.log line 1
08:15:10| auth.log| Additional failed SSH login| Suspicious| auth.log line 2
08:15:15| auth.log| Third failed SSH login| Suspicious| auth.log line 3
08:16:02| auth.log| Successful SSH login for ubuntu| Suspicious| auth.log line 4
08:18:40| sysmon.log| PowerShell executed with EncodedCommand| Suspicious| sysmon.log line 1
08:18:50| sysmon.log| whoami command executed| Suspicious| sysmon.log line 2
08:19:10| sysmon.log| New user account created| Suspicious| sysmon.log line 3
08:19:30| sysmon.log| User added to Administrators group| Suspicious| sysmon.log line 4
08:20:10| access.log| Request to /admin.php| Suspicious| access.log line 1
08:20:18| access.log| Request to /phpmyadmin| Suspicious| access.log line 2
08:20:31| access.log| Request to /wp-admin| Suspicious| access.log line 3
09:00:00| auth.log| Backup account login| Benign| auth.log line 5
09:00:00| sysmon.log| Nightly backup process executed| Benign| sysmon.log line 5
