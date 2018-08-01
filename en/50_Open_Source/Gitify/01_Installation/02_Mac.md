On MacOS, there's a version of PHP and MySQL installed by default. However if you use MAMP/MAMP Pro or a similar tool, it's possible that you get unexpected results trying to run Gitify from the terminal.

This might include errors about missing sockets, no access to the database and stuff like that.

There are two solutions to this problem. 

## 1. Add a mysql socket symlink

By symlinking the mysql socket in `/var/mysql/`, you will be able to communicate with the right database server. This link can sometimes get lost when the socket is closed so you might need to run this from time to time. 

````
cd /var/mysql/
sudo ln -s /Applications/MAMP/tmp/mysql/mysql.sock
````

If the `/var/mysql/` folder doesn't exist yet, you can create it like this:
```
sudo mkdir /var/mysql/
```

## 2. Use the right PHP binary

The recommended approach would be to make sure that you're using the right PHP binary in the first place. This can be done by editing your `.bash_profile` or `.zshrc` file in your user directory, and adding the following line:

````
export PATH=/Applications/MAMP/bin/php/php5.6.7/bin:$PATH
````

replacing the path with the right path for your PHP install. 

## 3. Use the right mysqldump and mysql binaries

If you'd like to use the [backup] and [restore] commands, you'll also need to add the mysqldump and mysql binaries to your PATH. 

````
export PATH=/Applications/MAMP/Library/bin:$PATH
````
