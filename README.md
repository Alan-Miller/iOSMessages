iOSMessageExport
================

Notes

* Emojis would only show up when viewing the pages in Safari.
* Images and videos are visible within the message threads, but all other content is linked.
* Files are overwritten without checking to see if one already exists.
* If you get an error about the DateTime module, please see this CPAN article on installing modules: http://www.cpan.org/modules/INSTALL.html
* If you're getting an "file is encrypted or is not a database" error, make sure you've disabled the "Encrypt iPhone backup" checkbox under the "Backup" settings panel in iTunes.

Basic steps:

1. Make a directory somewhere
    ```
    mkdir ~/Desktop/iOSBackup
    ```
2. Add this repository to your ~/Desktop/iOSBackup directory
    ```
    cd ~/Desktop/iOSBackup

    git clone git@github.com:junkblocker/iOSMessageExport.git
    ```
3. I recommend copying your iTunes backup into your ~/Desktop/iOSBackup folder, just in case something bad happens (as I am not responsible for your misfortunes). Run backup.pl passing the backup directory.
    ```
    perl iOSMessageExport/backup.pl --directory_path 9b9f73759fad7b31e330dd26bf7f745acccf1869/
    ```
    If you see an error that iOSSMSBackup cannot be found, you may need to run
    ```
    export PERL5LIB=iOSMessageExport/
    ```

4. An _export folder will be created in your working directory with all of your files!
