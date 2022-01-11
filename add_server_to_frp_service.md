#

# What is frp
## official repository
https://github.com/fatedier/frp

## the frp architecture we adopt
public IP (provided by Dr. Dingkang Liang)-----transfer-----servers

+ The transfer must be able to access the servers
+ the public IP doesn't have to be able to access the transfer
<br></br>

# Add new services to frp's configure file
## public IP
nothing to do

## transfer
Find the config file add the new service. 
The format is simple

```
[ssh_name_here]
type = stcp
local_ip = ip_of_server
local_port = port_of_server
sk = special_key
```

## servers
nothing to do

## Your PC
modify your config as the instructions in Wechat group 
<br></br>

# start the frp in transfer
## If you just don't want to read
In fact, 
```
pm2 restart all 
```
shall work

## more about how to use pm2 to manage a service
### write your command to a bash file
write your commands to a bash file, for example
```
$PATH/frpc -c $PATH/frpc.ini
```

### run the bash with pm2
pm2 start **.sh --interpreter bash

### save the service 
pm2 save all # so that your can just restart it next time

### read logs of the service if necessary
use pm2 info {id_of_service} to find the path of log file (ok, I think you have noticed .pm2 in the home directory)
