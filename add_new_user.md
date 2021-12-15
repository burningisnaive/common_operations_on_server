# add new user to a server
If you find errors or better ways, I would appreciate your feedback.

## check information about servers 
You can find the documents in our Wechat group. 

## login server and start shell with root's right
```
ssh -i private_key -p port admin@ip
sudo -s
```
## add user & set pwd
```
useradd new_user -m # use -m to add /home/new_user
passwd new_user
```

## add public key for ssh
+ add corresponding file as you like
+ copy from admin's file and set owner, right (recommended)
    ```
    cp -r /home/mclab/.ssh /home/new_user/
    chown -R new_user:new_user /home/new_user/.ssh #as the files are copied, the owner is still root
    chmod 700 /home/new_user/.ssh 
    chmod 600 /home/new_user/.ssh/id_rsa # this step is not necessary, and id_rsa may not exist 
    chmod 600 /home/new_user/.ssh/authorized_keys
    chmod 644 /home/new_user/.ssh/known_hosts
    ```
# add new admin (if it is necessary)
```
sudo usermod -G sudo new_user
```

# about the private key
Ask administrators for the key if you do not have the file, the project must not provide it for safety.