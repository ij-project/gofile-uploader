# GoFile Uploader
A Simple Script to upload Files to https://gofile.io via Terminal (CLI). Written in Bash.

To install it you can execute this command:

    sudo wget https://raw.githubusercontent.com/ij-project/gofile-uploader/refs/heads/bard/gofile -O "/usr/local/bin/gofile"; sudo chmod +x "/usr/local/bin/gofile"

Explanation: The wget command downloads the script from github and saves it to /usr/local/bin/gofile so you can run it from the terminal. Then chmod makes it executable

Then you can upload files from anywhere in the system using

    gofile file.txt

If you want to uninstall pdup you can run

    sudo rm "/usr/local/bin/gofile"

## Features:
- Upload Files to https://gofile.io Using own account API
- No File Size Limit
- No Limit on Number of Files
- Fast Servers
- Free of Cost

### Credits:
- https://gofile.io - For the Amazing Website to upload Unlimited files with Unlimited filesize to fast servers, for free!
