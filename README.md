# ansible_create_user-account_with_ssh-key

```
# ls -l
total 16
-rw-r--r-- 1 root root  141 Jan  2 07:16 main.yml
-rw------- 1 root root 1679 Jan  2 06:10 mykey
-rw-r--r-- 1 root root  430 Jan  2 06:10 mykey.pub
-rw-r--r-- 1 root root  245 Jan  2 07:18 task.yml
```

# Result

```yml
# ansible-playbook -i ./inventory main.yml

PLAY [setup lunux user account] ******************************************************************************************************************************************

TASK [Gathering Facts] ***************************************************************************************************************************************************
ok: [172.31.35.155]

TASK [include_tasks] *****************************************************************************************************************************************************
included: /home/ec2-user/day-3/task2/task.yml for 172.31.35.155

TASK [creat user john] ***************************************************************************************************************************************************
ok: [172.31.35.155]

TASK [Set authorized key took from file] *********************************************************************************************************************************
changed: [172.31.35.155]

PLAY RECAP ***************************************************************************************************************************************************************
172.31.35.155              : ok=4    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   

```



```
# ssh -i mykey john@172.31.35.155

       __|  __|_  )
       _|  (     /   Amazon Linux 2 AMI
      ___|\___|___|

https://aws.amazon.com/amazon-linux-2/
6 package(s) needed for security, out of 16 available
Run "sudo yum update" to apply all updates.

[john@ip-172-31-35-155 ~]$ logout
Connection to 172.31.35.155 closed.
```
