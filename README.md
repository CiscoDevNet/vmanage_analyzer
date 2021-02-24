# vmanage Analyzer Express

## ++++BETA++++

### Questions: [wcae@cisco.com](mailto:wcae@cisco.com)

Admin Tech data summarisation

```
usage: vma [-h] [-i INPUT_FILE] [-v] [-ev] [-ea] [-er] [-em] [-ek] [-ie]
           [-d DAYS_TO_PARSE]

vManage Analyzer - vMA. Provides XLS summarization of logs, auth errors  
Usage: vma -i yourfile.tar.gz 
Version 0.2


optional arguments:
  -h, --help            show this help message and exit
  -i INPUT_FILE, --input-file INPUT_FILE
                        Tar.gz admin tech file to be processed
  -v, --verbose         Include warn, info, debug, trace, message levels. Default is exceptions, error and fatal only
  -ev, --exclude_vmserver_logs
                        Tool will not process vmserver logs (speeds up file processing, less information)
  -ea, --exclude_auth_logs
                        Tool will not process auth logs (speeds up file processing, less information)
  -er, --exclude_rest_logs
                        Tool will not process REST logs (speeds up file processing, less information)
  -em, --exclude_message_logs
                        Tool will not process message logs (speeds up file processing, less information)
  -ek, --exclude_kernel_logs
                        Tool will not process kernel logs (speeds up file processing, less information)
  -ie, --include_rest_address_errors
                        Tool will generate list of IP addresses that generated 403 or 408 REST errors, disabled by default
  -d DAYS_TO_PARSE, --days-to-parse DAYS_TO_PARSE
                        How many days to process from the file, default =2, start is last day seen in file
```

Provides analysis of vManage Admin tech, with simplified log processing

## Features:
* Groups similar errors and exceptions, replacing common values like IP addresses, SN, user names, to reduce the total number of different messages to evaluate. it can drive 30.000 messages into around 150
* Detailed report available, with all logs suitable for filtering 
* Graph reports for user API activity
* REST, auth and vManage server logs summarisation
* Possibility to filter for only FATAL, ERROR, EXCEPTION message types, or to collect all levels if required
* You can select how many days to process. By default, it will take 2 days of logs (last log line - 2 days)
* Local authentication summary per users
* Local auth detailed view with sucess/failure attempts
* Checks to detect server compliance with best practices
* Version validation
* List all high memory usage alerts


Log aggregation takes a "simplistic" approach,  for speed optimisation, if you see something that should be grouped, please report it

## Output
* Results exported to XLS file
* File will be located on same folder as the admin tech input file (same name, terminated in xls)


## Compatibility
* Windows and Mac OS versions available
* File is packaged python application, just unzip
* Works with admin-techs captured from vManage servers, any version. For best results do not exclude tech information
