# Image and content of the **bash script**

![bash script image](/image%20space/bash%20script%20pic.jpg)


#!/bin/bash

log file path
LOGFILE=/home/vagrant/logs/ram.log

Email recepient
EMAIL="nwokoloebuka84@gmail.com"

format date
SENDTIME=$(date +%H%M)     

create log file  
>function createLog() {  
       if test -f $LOGFILE; then    
                 rm -rf $LOGFILE  
       else  
               touch $LOGFILE  
               date >> $LOGFILE  
               free -h >> $LOGFILE  
       fi  
}
  

set the time for the log file to execute
>if [[ $SENDTIME == 0132 ]]; then   
       createLog    
       echo "hey ebuka, this is your attached memory log for today" | mail -s "RAM USAGE" -A $LOGFILE $EMAIL  
fi

