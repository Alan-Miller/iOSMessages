iOSMessageExport
================

### Introduction
> This project reads an iOS backup folder and outputs a folder of HTML files for all Messages conversations, making it easy to read these files in a browser. It is an update of [Chelsey Baker's project](https://github.com/chelseybaker/iOSMessageExport). Nearly all of the code, and much of this readme, comes from her repo. Here are some changes I made:
1. It adds an edit to a file path to account for a small change Apple made to the folder structure.
1. It edits the date logic. All dates were appearing as 20001231. I suspect the necessary date logic might be different for different computers. Mine is an Apple Macbook.
1. It adds CSS styles to mimic iOS styles, so conversations appear as they do on iPhones.

### Basic steps

1. Make an iOSBackup directory on the Desktop
    ```
    mkdir ~/Desktop/iOSBackup
    ```
1. Move or copy your iTunes backup folder into this new folder. 

1. Clone iOSMessageExport repository to the new folder.
    ```
    cd ~/Desktop/iOSBackup

    git clone git@github.com:junkblocker/iOSMessageExport.git
    ```

1. This step may not be needed, but if you skip it and try the final step and you see an error that `iOSSMSBackup` cannot be found, you may need to run the command below. 
    ```
    export PERL5LIB=iOSMessageExport/
    ```
1. Run `backup.pl`, passing in the name of your iTunes backup folder (it will be a long string of letters and numbers such as `9b9f73759fad7b31e330dd26bf7f745acccf1869`). Make sure to include the forward slash (`/`) after the folder name.
    ```
    perl iOSMessageExport/backup.pl --directory_path <your_ios_backup_folder_name_here>/
    ```
    

### Result
After finishing these steps, an `_export` folder with all your files will be created in the iOSBackup folder.

### Other notes

* Files are overwritten without checking to see if one already exists.
* If you get an error about the DateTime module, see this CPAN article on installing modules: http://www.cpan.org/modules/INSTALL.html
* If you're getting a `file is encrypted or is not a database` error, make sure you have disabled the "Encrypt iPhone backup" checkbox under the "Backup" settings panel in iTunes.

