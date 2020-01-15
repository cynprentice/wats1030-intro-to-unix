# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here: 
    ```
     /c/Users/cynprentice/Projects/3030/wats1030-intro-to-unix
* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`? 
    ```
    challenge_files  LICENSE  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md  README.md  super_scavengers.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?
    ```
     I see metadata such as a permissions, date, and size for each file and folder. I also see hidden files and folders such as . and ..

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?
```
    -a: --all do not ignore entries starting with . 
    -l: --use long listing format, which includes permissions, number of linked hard-links, owner of the file, group this file belongs to, size, modification/creation date and time, file/directory name
    -h: --human-readable print human readable sizes (such as 1L 234M 5G)

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed? 
   ```
     bin  cmd  dev  etc  git-bash.exe  git-cmd.exe  LICENSE.txt  mingw64  proc  ReleaseNotes.html  tmp  unins001.dat  unins001.exe  unins001.msg  usr

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here: 
    ```
     /

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here: 
    ```
     /c/Users/cynprentice

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find
    ```
     3 files: 
        * 2015_special_stuff.demo
        * cloaked-wookie.demo
        * scooter-double-mamba.demo

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now? 
    ```
    /c/Users/cynprentice/Projects/3030/wats1030-intro-to-unix

* Press the up arrow on your keyboard. *What just happened?* The command line is prefilled with my previous command 
    ```
     (pwd)
* Press the up arrow a few more times. *What do you see?
    ```
    I see it cycling through the previous commands that I've run

* Run the `history` command. *What do you see?
    ```
     I see a list of all the commands I've run since opening this command line window, plus some that I assume were run on my behalf because I didn't type in the first 17 commands

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?
    ```
     cynprentice

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:
    ```
    no

* How long has your system been running? Use `uptime` to see, and *paste the result here:
    ```
    this command wasn't found. I'm running windows. By running this command "wmic path Win32_OperatingSystem get LastBootUpTime", I got the following result
        * LastBootUpTime 20200110114953.465439-480

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?
    ```
    This lists 2 processes running on my computer. One was run by the command bash and the other ps. I seem to get the same result by running ps aux and ps -aucynprentice. If I run the windows command tasklist I seem to get a more complete list of the processes running on my computer, similar to what I would see in the task manager gui

        
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?
    ```
     command not found. I couldn't easily find an windows equivalent for this one.

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?
    ```
    2 files
        * credit_cards.txt
        * credit_cards2.txt

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?
    ```
    last_updated: 01-15-2015   but I couldn't run the command in VS. I got the error bash: more: command not found. When I googled the windows equivalent for more, I found that more is a windows command so I opened a command prompt window outside of VS to test the command and view the date

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?
    ```
     in the tmp folder
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?
    ```
     2 files: 
        * challenge_files/Britt-Erdman.user:O'Harachester, WA 37261
        * challenge_files/Lissie-Strosin.user:Jewessfurt, WA 00816-7241

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.
    ```
    challenge_files/serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?
    ```
    I see the results of the ls command, a list of files and folders

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.
    ```
    I couldn't get this command to run. I expect that I would see the list of files one screen at a time

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:
    ```
    I couldn't get this to run on my windows machine again, but using the command prompt and the command <i>tasklist /fi "username eq cynprentice" </i> When filtering the 268 processes to the ones run by my username, there were 142.
    
     sihost.exe                    5088 Console                    1     19,468 K
     svchost.exe                   4396 Console                    1     17,444 K
     nis.exe                       5144 Console                    1      5,856 K
     NAT.exe                       5156 Console                    1      8,172 K
     svchost.exe                   5336 Console                    1     25,484 K
     MotoHelperAgent.exe           5408 Console                    1      2,536 K
     taskhostw.exe                 5684 Console                    1     11,760 K
     igfxEM.exe                    6084 Console                    1      5,312 K
     igfxHK.exe                     712 Console                    1      2,276 K
     igfxTray.exe                  6048 Console                    1      3,732 K
     rundll32.exe                  6528 Console                    1      2,284 K
     explorer.exe                  6608 Console                    1    105,000 K
     SynTPEnh.exe                  7052 Console                    1      8,768 K
     svchost.exe                   7072 Console                    1      7,244 K
     svchost.exe                   5480 Console                    1     17,468 K
     SynTPHelper.exe               3340 Console                    1      1,116 K
     ShellExperienceHost.exe       7428 Console                    1     19,684 K
     SearchUI.exe                  7824 Console                    1     64,704 K
     RuntimeBroker.exe             7656 Console                    1     18,852 K
     RuntimeBroker.exe             8292 Console                    1     18,448 K
     ctfmon.exe                    8480 Console                    1     11,560 K
     TabTip.exe                    8508 Console                    1      5,508 K
     LockApp.exe                   8912 Console                    1     24,696 K
     SettingSyncHost.exe           8936 Console                    1      6,676 K
     RuntimeBroker.exe             9100 Console                    1     20,444 K
     scrncap.exe                   9108 Console                    1      1,724 K
     SkypeApp.exe                 10028 Console                    1     37,756 K
     SkypeBackgroundHost.exe      10056 Console                    1      2,104 K
     YourPhone.exe                10104 Console                    1     17,996 K
     RuntimeBroker.exe             8276 Console                    1      6,820 K
     RuntimeBroker.exe            10328 Console                    1     14,856 K
     SkypeBridge.exe              10468 Console                    1     36,320 K
     SecurityHealthSystray.exe    11080 Console                    1      2,816 K
     CAudioFilterAgent64.exe      11248 Console                    1      3,056 K
     TssSrv.exe                    3484 Console                    1      2,520 K
     TCrdMain_Win8.exe            10132 Console                    1      4,320 K
     TCrdKBB.exe                  10588 Console                    1      1,420 K
     TecoResident.exe              8756 Console                    1      4,264 K
     ScanToPCActivationApp.exe    11664 Console                    1      7,684 K
     AppleMobileDeviceProcess.    12040 Console                    1      3,024 K
     SSScheduler.exe              12144 Console                    1      1,592 K
     Lightshot.exe                12196 Console                    1      6,456 K
     Video.UI.exe                 12256 Console                    1      6,932 K
     RuntimeBroker.exe            11580 Console                    1      4,136 K
     opera.exe                     7972 Console                    1    114,340 K
     opera_crashreporter.exe       7584 Console                    1      2,328 K
     chrome.exe                    7784 Console                    1    173,060 K
     chrome.exe                   11000 Console                    1      2,044 K
     opera.exe                     6940 Console                    1    247,232 K
     pera.exe                    10020 Console                    1     34,352 K
     chrome.exe                    2340 Console                    1      2,176 K
     chrome.exe                    6636 Console                    1    256,420 K
     chrome.exe                   12076 Console                    1     37,476 K
     chrome.exe                    3744 Console                    1     49,704 K
     chrome.exe                    4068 Console                    1     77,744 K
     opera.exe                    11768 Console                    1      4,996 K
     chrome.exe                   11528 Console                    1      6,996 K
     Code.exe                     10676 Console                    1     76,080 K
     opera.exe                    10816 Console                    1      5,524 K
     opera.exe                     7780 Console                    1      6,460 K
     opera.exe                    11092 Console                    1      7,432 K
     opera.exe                    11256 Console                    1     28,084 K
     opera.exe                     1784 Console                    1      6,684 K
     opera.exe                     8236 Console                    1      8,908 K
     opera.exe                     1064 Console                    1      8,652 K
     opera.exe                     7736 Console                    1     20,304 K
     opera.exe                    11432 Console                    1      6,784 K
     opera.exe                     6708 Console                    1     16,792 K
     opera.exe                     2884 Console                    1     35,116 K
     Code.exe                      5860 Console                    1    160,324 K
     Code.exe                     12724 Console                    1     29,544 K
     opera.exe                    12852 Console                    1     14,372 K
     Code.exe                     12908 Console                    1      2,848 K
     chrome.exe                   13292 Console                    1     33,404 K
     opera.exe                     7192 Console                    1     20,056 K
     firefox.exe                   7604 Console                    1    231,032 K
     firefox.exe                   4748 Console                    1     56,708 K
     firefox.exe                  12504 Console                    1     41,592 K
     firefox.exe                  11388 Console                    1     15,712 K
     CompPkgSrv.exe               13668 Console                    1      3,872 K
     RuntimeBroker.exe            13788 Console                    1      4,260 K
     opera.exe                    14188 Console                    1     83,504 K
     HPNETW~1.EXE                  2920 Console                    1      6,520 K
     WindowsInternal.Composabl    11384 Console                    1        700 K
     opera.exe                     9952 Console                    1      6,884 K
     smartscreen.exe               8680 Console                    1     19,064 K
     WINWORD.EXE                  14792 Console                    1     86,676 K
     dllhost.exe                  14496 Console                    1      6,196 K
     opera.exe                    14772 Console                    1     72,856 K
     Microsoft.Photos.exe          7124 Console                    1        108 K
     RuntimeBroker.exe            13572 Console                    1     19,616 K
     opera.exe                     7020 Console                    1     16,676 K
     opera.exe                     8628 Console                    1      7,356 K
     chrome.exe                    1808 Console                    1      7,208 K
     chrome.exe                    4292 Console                    1    266,028 K
     firefox.exe                   9128 Console                    1     56,680 K
     firefox.exe                  15972 Console                    1    250,760 K
     chrome.exe                    3980 Console                    1     34,696 K
     chrome.exe                    1512 Console                    1    118,768 K
     firefox.exe                   5504 Console                    1     52,148 K
     firefox.exe                   3460 Console                    1    198,448 K
     firefox.exe                   1356 Console                    1     46,980 K
     opera.exe                     6300 Console                    1     32,668 K
     chrome.exe                    2032 Console                    1     57,884 K
     firefox.exe                   6924 Console                    1    182,652 K
     opera.exe                    14104 Console                    1     93,528 K
     opera.exe                      768 Console                    1     39,952 K
     opera.exe                     6228 Console                    1    111,704 K
     Code.exe                     15612 Console                    1    181,516 K
     CodeHelper.exe               13764 Console                    1     13,948 K
     conhost.exe                  18148 Console                    1      5,440 K
     Code.exe                     14244 Console                    1     77,728 K
     Code.exe                      9700 Console                    1     83,680 K
     opera.exe                     6852 Console                    1     88,720 K
     opera.exe                     6356 Console                    1     91,268 K
     opera.exe                     5176 Console                    1    125,128 K
     winpty-agent.exe             15032 Console                    1      5,880 K
     conhost.exe                   6908 Console                    1      8,760 K
     bash.exe                     14808 Console                    1      4,716 K
     bash.exe                     11552 Console                    1      9,436 K
     firefox.exe                  12736 Console                    1     82,848 K
     chrome.exe                   17072 Console                    1     54,792 K
     opera.exe                    15540 Console                    1     98,060 K
     opera.exe                    11628 Console                    1     49,060 K
     opera.exe                     3416 Console                    1     49,284 K
     opera.exe                      432 Console                    1     47,680 K
     opera.exe                    17252 Console                    1     21,856 K
     Taskmgr.exe                  17184 Console                    1     50,592 K
     chrome.exe                   12684 Console                    1     59,984 K
     chrome.exe                    4568 Console                    1    151,172 K
     chrome.exe                    7880 Console                    1     72,244 K
     chrome.exe                    7844 Console                    1     46,484 K
     chrome.exe                   15776 Console                    1     28,744 K
     chrome.exe                   15536 Console                    1     70,596 K
     chrome.exe                    9836 Console                    1     28,012 K
     cmd.exe                      15748 Console                    1      4,172 K
     conhost.exe                  15752 Console                    1     14,076 K
     opera.exe                    17280 Console                    1    122,976 K
     opera.exe                     2672 Console                    1     40,264 K
     chrome.exe                   16304 Console                    1     77,732 K
     chrome.exe                   16288 Console                    1     20,992 K
     tasklist.exe                 11692 Console                    1      8,260 K
