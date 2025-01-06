# Note on File Permissions

If you are using devcontainers, please note that you have root access while inside container. Hence, for example, when you create a folder, it will require root permissions to change. This can be a problem when you want to do operations like `scp` to it. To explain why so, when you `scp`, you wil run a command like:

```bash
scp -r data aditya_sit@172.28.70.244:/home/aditya_sit/<repo>/data
```

Here, you will be asked to SSH (which will only give you user access and not root). So, this will lead to an error where folder will not be visible as a target. To solve this, SSH as user to the same folder as workspace (in my case `/home/aditya_sit/<repo>)` and create a folder like `data` here. After doing this, you can run `ls -la .` to check perms. 

![](<media/file-perms.png>)

As you can see, `data` folder has user perms, and `scp` will now work. 
