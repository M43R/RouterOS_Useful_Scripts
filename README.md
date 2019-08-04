# RouterOS_Useful_Scripts
> MikroTik RouterOS Scripts for various use and shared among different projects. Repository contains ready to use scripts as well functions ready to use in larger projects. 

![](https://img.shields.io/badge/scripting-routeros-important.svg)
![](https://img.shields.io/badge/mikrotik-routerBOARD-yellow)
![](https://img.shields.io/badge/network-automation-informational)

## Change log 

   - 8/3/2019
      - RouterOS_String_Generator.rsc
        - Generates 6 char string based on dictionary 
      - RouterOS_Reset_Interface.rsc
        - Resets interface if particular IP does not respond 

   - 7/29/2019 
      - RouterOS_Modulo.rsc
        - Modulo operation
      - RouterOS_Load_Script.rsc
        - Loads RouterOS script to environment. If file is missing adds log entry 

   - 7/19/2019 
      - FTP_Backup_Template.rsc
        - Schedules generation of *.backup* and *.rsc* file on RouterOS. Create FTP user dedicated for automatic backups. More on automatic RouterOS
      backups can be found under dedicated project: :link: [Backup_mt by gbudny93](https://github.com/gbudny93/Backup_mt)
     - RouterOS_Auto_Upgrade.rsc
       - in progress
     - RouterOS_Create_Directory.rsc
       - Creates directory with specific name in RouterOS
     - RouterOS_Log_Filtering.rsc
       - Filters logs based on specified criteria: time or message and put in desired output
     - RouterOS_Log_To_Alert.rsc
       - Sends an email alert based on log message match
     - RouterOS_Send_Email.rsc
       - Sends email via SMTP server with common email parameters as function parameters
     - RouterOS_File_Logging.rsc
       - Adds log entry if file was added or removed 
     - RouterOS_LCD_Change.rsc (Applies only to physical devices with LCD)
       - Changes LCD mode from dark to light and vice versa based on schedule set up
     - RouterOS_Low_Disk_Space.rsc
       - Sends email alert if disk space is under specified treshhold
     - RouterOS_File_Screening.rsc
       - in progress
     - RouterOS_Eth_Errors_Handling.rsc
       - in progress
     - RouterOS_Config_Check.rsc
       - in progress

  - 6/14/2019 first release
    - FTP_Backup_Template.rsc
      - Schedules generation of *.backup* and *.rsc* file on RouterOS. Create FTP user dedicated for automatic backups. More on automatic RouterOS
      backups can be found under dedicated project: :link: [Backup_mt by gbudny93](https://github.com/gbudny93/Backup_mt)
    - RouterOS_Auto_Upgrade.rsc
      - in progress
    - RouterOS_Create_Directory.rsc
      - Function that creates directory with specific name in RouterOS
    - RouterOS_Log_Filtering.rsc
      - in progress
    - RouterOS_Log_To_Alert.rsc
      - in progress
    - RouterOS_Send_Email.rsc
      - Fucntion sending email via SMTP server with common email parameters as function parameters
    
## Prerequisites

  -  :white_check_mark: RouterOS v6.40 or higher
  -  :white_check_mark: MikroTik CRS or CCR with LCD for RouterOS_LCD_Change.rsc
  
## Usage

> Use the following scripts to make your RouterOS management easier or use them in various larger scripts or projects 
:+1: 

### FTP_Backup_Template.rsc

> This script creates two files via RouterOS scheduler as well creates FTP user and group: 
  - *.backup* file 
  - *.rsc* file 
  
Script is a part of  :link: [Backup_mt by gbudny93](https://github.com/gbudny93/Backup_mt) project.

### RouterOS_Auto_Upgrade.rsc

 :soon:

### RouterOS_Create_Directory.rsc

> RouterOS function that creates directory with defined name in the system. Can be used just to create directory or be a part of larger project. 

**Example**
 ```rascal
 $CreateDirecotry userName=UserName password=Password directoryName=DirectoryName
```

### RouterOS_Log_Filtering.rsc

> RouterOS function for log messages filtering based on message or time match stored in chosed output. 

```
$LogFilter;
```

### RouterOS_Log_To_Alert.rsc

 > RouterOS function sending mail alert if log entry matches message criteria.

 ```
 $LogToAlert message="message" fileName="fileName" smtpServer=smtpServer smtpPort=smtpPort domain="@example.com" \ 
recipient="recipient@example.com";
 ```

### RouterOS_Send_Email.rsc

> RouterOS function to send email via SMTP server. Function contains all common email fields like *to*, *cc*, *subject*, *body* and more. Function can be called itself in RouterOS or by other script.

**Example**
```
$SendEmail smtpServer=SMTPServer smtpPort=SMTPPort from=From to=To subject=Subject body=Body
```

### RouterOS_File_logging.rsc

> RouterOS function adding log entry if file was added or removed.

```
$FileToLog;
```

### RouterOS_LCD_Change.rsc

> RouterOS function changing LCD mode from dark to light and vice versa based on schedule setup.

```
$ChangeLcd lightModeStartTime="08:00:00" darkModeStartTime="17:00:00";
```

### RouterOS_Low_Disk_Space.rsc

> RouterOS function generating mail alert if disk space is below defined treshhold.

```
$LowDiskSpace treshhold=free_disk_space_in_%;
```

### RouterOS_File_Screening.rsc

:soon: 

### RouterOS_Eth_Errors_Handling.rsc

:soon:

### RouterOS_Config_Check.rsc

:soon: 

### RouterOS_Modulo.rsc

>Modulo function.

```
$Modulo number=number_to_be_devided modulo=modulo_value;
```

### RouterOS_Load_Script.rsc

```
$LoadScript scriptName=scriptName.rsc;
```

### RouterOS_String_Generator.rsc

> Generates 6 char string based on dictionary 

```
$GenerateString;
```

### RouterOS_Reset_Interface.rsc

> Resets interface if particular IP does not respond 

```
$ResetInterface ipAddress=ipAddress_To_Monitor interfaceName=interface_name;
```

## Authors

  - Grzegorz Budny




  
  

