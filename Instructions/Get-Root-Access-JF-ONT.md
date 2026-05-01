# Get Root Access (via Telnet)

*Disclaimer: - This is Only for educational purposes, No one is responsible for any type of damage. Any wrong step might brick your router. So be aware.*

1. First of all, follow [this guide](https://github.com/Naitik1208/JF-ROUTER/blob/main/Instructions/Get%20Router%20Configuration.md) to get the router decrypted configuration file `RSTXXXXXXX_JCXXXXX.txt`

2. Open `RSTXXXXXXX_JCXXXXX.txt` with Notepad or other Text Editor.

3. The first line of the file should look like : `config.userdb = {}`.

4. Change the first line to :

  ```
config.userdb = {} os.execute("/usr/sbin/telnetd"); os.execute("/pfrm2.0/bin/iptables -I fwInBypass -p tcp --dport 23 -m ifgroup --ifgroup-in 0x1/0x1 -j ACCEPT"); os.execute("echo -e \"password\npassword\" | passwd root");
  ```
FOR NEW FIRMWARES LIKE JCOW404 3.10 OR 3.10.2 Try below command if above doesn't work
 ```
config.userdb = {} os.execute("/usr/sbin/utelnetd"); os.execute("/pfrm2.0/bin/iptables -I fwInBypass -p tcp --dport 23 -m ifgroup --ifgroup-in 0x1/0x1 -j ACCEPT"); os.execute("echo -e \"password\npassword\" | passwd root");
  ```

5. Ensure there is no line break in the line you just pasted. The whole content should be in a single line and the line should start with `config` otherwise this isn't gonna work.

6. Follow [this guide](https://github.com/Naitik1208/JF-ROUTER/blob/main/Instructions/Encrypt-Router-Configuration-File.md) to re-encrypt the configuration file and restore it via the router admin panel.

7. Connect your router via Telnet at port 23 with `root` as user name and `password` as password.

8. For newer firmwares, use command `rm /flash/telnetDisable` to keep Telnet enabled. (Otherwise it will be disabled after some time).
Otherwise, on older firmwares use command `touch /tmp/DEBUG_IMAGE` to keep Telnet enabled. (Otherwise it will be disabled after some time).

9.Bonus Tip: To keep telnet enabled use [this script](https://github.com/Naitik1208/JF-ROUTER/blob/main/Scripts/service.sh#L20) Store it on your router and add it to the rcS file as mentioned in [this guide](https://github.com/Naitik1208/JF-ROUTER/blob/main/Instructions/Run%20Custom%20Scripts%20On%20Your%20Router.md).
**Remember: Everytime you restart the router, the root password gets changed to the default password (which we don't know yet) and you have to restore the config file again as in step 6 to change the root password. Step 8 will keep your telnet enabled across router restarts.**
