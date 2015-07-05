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

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:*
/home/cabox/workspace

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?*
LICENSE  README.md  challenge_files  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
It shows total size and more details like permissions, owner and dates.
total 36K                                                                                                                                  
drwxrwxr-x 4 cabox cabox 4.0K Jul  5 15:53 .                                                                                               
drwxr-xr-x 9 cabox cabox 4.0K Jul  5 15:53 ..                                                                                              
drwxrwxr-x 8 cabox cabox 4.0K Jul  5 15:53 .git                                                                                            
-rw-rw-r-- 1 cabox cabox 1.1K Jul  5 15:53 LICENSE                                                                                         
-rw-rw-r-- 1 cabox cabox 1.4K Jul  5 15:53 README.md                                                                                       
drwxrwxr-x 7 cabox cabox 4.0K Jul  5 15:53 challenge_files                                                                                 
-rw-rw-r-- 1 cabox cabox 5.4K Jul  5 16:02 nix_scavenger_hunt.md                                                                           
-rw-rw-r-- 1 cabox cabox  317 Jul  5 15:53 nix_scavenger_hunt_stretch.md

* The `man` ("manual") command tells you more about how any given command works. Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
 -a      Include directory entries whose names begin with a dot (.).
 -l      (The lowercase letter ``ell''.)  List in long format.  (See below.)  If the output is to a terminal, a total sum for all the file sizes is output on a line before the long listing.
 s-h      When used with the -l option, use unit suffixes: Byte, Kilobyte, Megabyte, Gigabyte, Terabyte and Petabyte in order to reduce the number of digits to three or less using base 2 for sizes.

* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
cabox

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
/home

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
/home/cabox

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
Only 1 : cloaked-wookie.demo 

* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
/home/cabox/workspace 

* Press the up arrow on your keyboard. *What just happened?*
Repeated the last command line.

* Press the up arrow a few more times. *What do you see?*
Went back to several previous command lines.

* Run the `history` command. *What do you see?*
Listed all the command lines I used during the session.

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
cabox

* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
cabox    pts/0        Jul  5 15:54 (54.69.152.243)

* How long has your system been running? Use `uptime` to see, and *paste the result here:*
41 mins
16:35:27 up 41 min,  1 user,  load average: 0.00, 0.00, 0.00

* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
 The ps utility displays a header line, followed by lines containing information about all of your processes that have controlling terminals.
 
 %cpu       percentage CPU usage (alias pcpu)
 %mem       percentage memory usage (alias pmem)
 command    command and arguments
 pid        process ID
 rss        resident set size        sleep time (in seconds; 127 = infinity)
 start      time started
 state      symbolic process state (alias stat)
 time       accumulated CPU time, user + system (alias cputime)
 tty        full name of control terminal
 user       user name (from UID)
 vsz        virtual size in Kbytes (alias vsize)

* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
  top - display and update sorted information about processes
   The first several lines of the top display show various global state.  All of the information is labeled.  Following is an alphabetical list of global state fields and their descriptions.

   CPU         Percentage of processor usage, broken into user, system, and idle components.  The time period for which these percentages are calculated depends on the event counting mode.

   Disks       Number and total size of disk reads and writes.

   LoadAvg     Load average over 1, 5, and 15 minutes.  The load average is the average number of jobs in the run queue.

   MemRegions  Number and total size of memory regions, and total size of memory regions broken into private (broken into non-library and library) and shared components.

   Networks    Number and total size of input and output network packets.

   PhysMem     Physical memory usage, broken into wired, active, inactive, used, and free components.

   Procs       Total number of processes and number of processes in each process state.

   SharedLibs  Resident sizes of code and data segments, and link editor memory usage.

   Threads     Number of threads.

   Time        Time,  in  H:MM:SS  format.   When running in logging mode Time is in YYYY/MM/DD HH:MM:SS format by default, but may be overridden with accumulative mode.  When running in accumulative
			   event counting mode, the Time is in HH:MM:SS since the beginning of the top process.

   VirtMem     Total virtual memory, virtual memory consumed by shared libraries, and number of pageins and pageouts.

   Swap        Swap usage: total size of swap areas, amount of swap space in use and amount of swap space available.

   Purgeable   Number of pages purged and number of pages currently purgeable.

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
Using command: ls *credit*
Found 2 : credit_cards.txt credit_cards2.txt 

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
01-15-2015

* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
./tmp/modi_laboriosam.txt

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
FOUND 2 :
Britt-Erdman.user:O'Harachester, WA 37261 
Lissie-Strosin.user:Jewessfurt, WA 00816-7241

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidu
nt. Explicabo vel esse blanditiis dolorem culpa non quia.

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
01                                                                                                                                                                  
2015_special_stuff.demo                                                                                                                                             
Afton-Jast.user                                                                                                                                                     
Aimee-Maggio.user                                                                                                                                                   
Alfonso-Gottlieb.user                                                                                                                                               
Allen-Kemmer.user                                                                                                                                                   
Almina-Cormier.user                                                                                                                                                 
Alta-Lemke.user                                                                                                                                                     
Amina-McGlynn.user                                                                                                                                                  
Anabel-Hammes.user                                                                                                                                                  
Ancel-Conn.user                                                                                                                                                     
Anjali-Halvorson.user                                                                                                                                               
Ardath-Kuvalis.user                                                                                                                                                 
Avah-Dickinson.user                                                                                                                                                 
Ayaan-Stiedemann.user                                                                                                                                               
Aylin-Grant.user                                                                                                                                                    
Bedford-Sipes.user                                                                                                                                                  
Benita-King.user                                                                                                                                                    
Benito-Stoltenberg.user                                                                                                                                             
Beverlee-Moen.user                                                                                                                                                  
Brad-Thiel.user                                                                                                                                                     
Brayan-Douglas.user                                                                                                                                                 
Bria-Satterfield.user                                                                                                                                               
Bridgette-Reichel.user                                                                                                                                              
Britt-Erdman.user                                                                                                                                                   
Britta-Hammes.user                                                                                                                                                  
Bryant-Kuhic.user                                                                                                                                                   
Bryton-Aufderhar.user                                                                                                                                               
Caitlin-Grady.user                                                                                                                                                  
Carroll-Hartmann.user                                                                                                                                               
Claudie-McClure.user
Clemente-Haley.user                                                                                                                                                 
Cleo-VonRueden.user                                                                                                                                                 
Codie-Romaguera.user                                                                                                                                                
Cooper-Reynolds.user                                                                                                                                                
Corrie-Bogisich.user                                                                                                                                                
Dannielle-Green.user                                                                                                                                                
Deedee-Jacobson.user                                                                                                                                                
Desiree-Marks.user                                                                                                                                                  
Deven-Rutherford.user                                                                                                                                               
Doyle-Jones.user                                                                                                                                                    
Dustyn-O'Connell.user                                                                                                                                               
Elza-Mraz.user                                                                                                                                                      
Emory-Crona.user                                                                                                                                                    
Erin-Walker.user                                                                                                                                                    
Estela-Schultz.user                                                                                                                                                 
Fernanda-Tromp.user                                                                                                                                                 
Fletcher-Rice.user                                                                                                                                                  
Fred-Ryan.user                                                                                                                                                      
Genie-Abshire.user                                                                                                                                                  
Grace-Tromp.user                                                                                                                                                    
Grant-Cronin.user                                                                                                                                                   
Hali-Roob.user                                                                                                                                                      
Harland-Schoen.user                                                                                                                                                 
Harrell-Quitzon.user                                                                                                                                                
Hillard-Ziemann.user                                                                                                                                                
Isadora-Leffler.user                                                                                                                                                
Jaxen-Gleichner.user                                                                                                                                                
Jayme-Rodriguez.user                                                                                                                                                
Jenni-O'Connell.user                                                                                                                                                
Johny-Borer.user                                                                                                                                                    
Kassandra-Barrows.user
Keely-Hilpert.user                                                                                                                                                  
Kenyatta-Hickle.user                                                                                                                                                
Kiana-Kulas.user                                                                                                                                                    
Kirstin-Hoppe.user                                                                                                                                                  
Kwame-Schmitt.user                                                                                                                                                  
Ladonna-Lueilwitz.user                                                                                                                                              
Lala-Will.user                                                                                                                                                      
Leia-Hudson.user                                                                                                                                                    
Leia-Ziemann.user                                                                                                                                                   
Lillard-Purdy.user                                                                                                                                                  
Lilly-Kohler.user                                                                                                                                                   
Lissie-Strosin.user                                                                                                                                                 
Mannie-Ritchie.user                                                                                                                                                 
Masako-Lind.user                                                                                                                                                    
Melisa-Yundt.user                                                                                                                                                   
Michelina-Kuphal.user                                                                                                                                               
Minnie-Jacobi.user                                                                                                                                                  
Murdock-Leffler.user                                                                                                                                                
Mychal-Corkery.user                                                                                                                                                 
Nakita-Nader.user                                                                                                                                                   
Nayely-Dare.user                                                                                                                                                    
Nicholas-Strosin.user                                                                                                                                               
Niles-Runte.user                                                                                                                                                    
Nina-Sporer.user                                                                                                                                                    
Noreta-Steuber.user                                                                                                                                                 
Ovid-Bogan.user                                                                                                                                                     
Randell-Sauer.user                                                                                                                                                  
Remy-Renner.user                                                                                                                                                    
Ronna-Hermann.user                                                                                                                                                  
Rosalind-Wisozk.user                                                                                                                                                
Rosena-Simonis.user 
Mychal-Corkery.user                                                                                                                                                 
Nakita-Nader.user                                                                                                                                                   
Nayely-Dare.user                                                                                                                                                    
Nicholas-Strosin.user                                                                                                                                               
Niles-Runte.user                                                                                                                                                    
Nina-Sporer.user                                                                                                                                                    
Noreta-Steuber.user                                                                                                                                                 
Ovid-Bogan.user                                                                                                                                                     
Randell-Sauer.user                                                                                                                                                  
Remy-Renner.user                                                                                                                                                    
Ronna-Hermann.user                                                                                                                                                  
Rosalind-Wisozk.user                                                                                                                                                
Rosena-Simonis.user                                                                                                                                                 
Sandie-Balistreri.user                                                                                                                                              
Sharen-Hansen.user                                                                                                                                                  
Sherrill-Russel.user                                                                                                                                                
Sherwin-Kovacek.user                                                                                                                                                
Sherwood-Rath.user                                                                                                                                                  
Shyheim-Murazik.user                                                                                                                                                
Siobhan-Kirlin.user                                                                                                                                                 
Tomas-Kutch.user                                                                                                                                                    
cloaked-wookie.demo                                                                                                                                                 
credit_cards.txt                                                                                                                                                    
credit_cards2.txt                                                                                                                                                   
files.text                                                                                                                                                          
files.txt                                                                                                                                                           
scooter-double-mamba.demo                                                                                                                                           
serial-numbers                                                                                                                                                      
test2                                                                                                                                                               
tmp                                                                                                                                                                 
wow

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
Shows only a viewable portion and everytime I hit spacebar ut show more.

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
root       557  0.0  1.3  63876  3480 ?        Ss   15:53   0:00 sshd: cabox [priv]                                                                                 
cabox      559  0.0  0.5  64012  1488 ?        S    15:53   0:00 sshd: cabox@pts/0                                                                                  
cabox      560  0.0  0.7  18148  2064 pts/0    Ss   15:53   0:00 -bash                                                                                              
root       603  0.0  1.2  63876  3332 ?        Ss   17:40   0:00 sshd: cabox [priv]                                                                                 
cabox      605  0.0  0.5  64008  1552 ?        S    17:40   0:00 sshd: cabox@notty                                                                                  
cabox      606  0.0  0.5  13528  1436 ?        Ss   17:40   0:00 /usr/lib/openssh/sftp-server                                                                       
cabox      639  0.0  0.4  15520  1136 pts/0    R+   18:32   0:00 ps aux                                                                                             
cabox      640  0.0  0.2   8816   760 pts/0    S+   18:32   0:00 grep --color=auto cabox 