iOSMessageExport
================

Notes

* Emojis only show up when viewing pages in Safari.
* Images and videos are visible within the message threads, but all other content is linked.
* Files are overwritten without checking to see if one already exists.
* If you get an error about the DateTime module, see this CPAN article on installing modules: http://www.cpan.org/modules/INSTALL.html
* If you're getting a `file is encrypted or is not a database` error, make sure you've disabled the "Encrypt iPhone backup" checkbox under the "Backup" settings panel in iTunes.

Basic steps:

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
    

> After finishing these steps, an `_export` folder with all your files will be created in the iOSBackup folder.

> My thanks to [Chelsey Baker](https://github.com/chelseybaker) for [her original repo](https://github.com/chelseybaker/iOSMessageExport).