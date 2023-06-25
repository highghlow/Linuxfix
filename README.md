# Linuxfix
Documenting my linux issues
# Login loop
When logging into the system, get sent back to the login screen without any errors
### Possible causes
 - /home not mounted:
   - Solution unknown
 - Not enough space in /home
   - Get into the terminal from the login screen using Ctrl+Alt+F2
   - Log in using user credentials
   - Use `du -a /dir/ | sort -n -r | head -n 20` to find largest files
   - Remove useless lagre files
   - Get back to login screen using Ctrl+Alt+F1
   - Reboot
### Other solutions that worked
 - Reinstall the desktop enviroment

# User not in sudoers file
Other name: Linux requiring log in with `Administrator`, which does not exist

When running sudo it results in `<username> not in sudoers file`

When making system changes through GUI, Linux says: type a password for Administrator, which does not exist

### Possible causes
 - Accidental removal of the user from the group after mistyping `usermod -aG` as `usermod -G`
   - Boot from a live USB (For example Ubuntu)
   - Install git and python3 onto the live USB (If not installed)
   - Run
```
git clone https://github.com/highghlow/IAmRoot
cd IAmRoot
sudo python3 main.py
```
 - .
   - Select Linux -> All Users
   - Boot back into the main system
   - Run `/usr/share/iamroot`
   - In the elevated shell run `nano /etc/sudoers`
   - Add `<username> ALL=(ALL:ALL) ALL` at the end
   - Save using Ctrl+X
   - In the elevated shell run `usermod -aG wheel <username>`
   - In the elevated shell run `rm /usr/share/iamroot`
# VSCode fails to open any links
Visual Studio Code is unable to directly open links
### Possible causes
 - Unknown
   - Remove visual studio code
   - Install from the official website (https://code.visualstudio.com/)
# Video in the browser fails to run
 - Unknown
   - Please submit a pull request if you know the solution