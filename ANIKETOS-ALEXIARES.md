The "god" script: Herakles
The script prompts for the protected DIR(s) and zips them into a TZ. TZ will be named based on TBD. TZ will be copied to TBD. Creates "child" or "demigod" scripts that do the continuous file checking. 


Two bash scripts:
 - Aware of each other's PID<br> - If other is killed -> Death alert
 - Input the dir(s) that should be protected<br> - Tar ball the files and store in multiple different locations (locations could be stored in comments of etc conf files)<br> - Checks that the protected dirs have not been altered using MD5 -> Severe Alert<br> - Check if tar is still there -> Death alert<br> - Users have not been added or changed

How do we "converge" the protection service on startup?
Have a "god" file. Asks for protected DIR(s), backs up DIR(s). Starts the two scripts at (close enough to) the same time. In the first thirty seconds all the scripts will do is get their PIDs and write to a file that is named based on the nearest 5 min\*. After 30 seconds, check to see if other's PID is in, if so, enter main loop. 

Once Brothers are go:
Main loop will constantly check for:
 1. Brother's PID has not been killed
 2. DIRs are unaltered
 3. Users have not been changed
 4. TAR is still safe



\* If started at 9:33, file will be `9-35`. If 9:31, file will be `9-30`.

Death Alert:
This assumes that the entire system has been compromised by means of user login or web based attack and that they are aware of the security measures we have implemented to prevent them. The objective of this alert is to preserve: log files, back-ups, and services, and to sever the connection to the hackers by all means.
Procedure:
  1. log "w" command
  2. log ssh connections
  3. Down **ALL** internet interfaces
  4. Close **ALL** UFW ports
  5. Kill SSH client
  6. Kill protected service
  7. Copy logs out to secure dir
  8. Display pop-up to sysadmin

Severe Alert:
This is a (semi) expected alert that indicates that the server has been altered by someone on the system. 

Naming convention:
ANIKETOS & ALEXIARES were two Olympian demigods who presided over the defence and fortification of towns and citadels. Their names mean "the unconquerable one" from the Greek anikêtos and "he who wards off war" from alexis and arês. They were sons of Herakles (Heracles)
