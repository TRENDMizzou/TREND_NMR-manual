### Installing the TREND package under Windows, OS X or Linux

To obtain access to TREND, go to [http://biochem.missouri.edu/trend/](http://biochem.missouri.edu/trend/)

Submit either an academic license agreement or request for commercial 
licensing, as well as the contact information for you and your laboratory.
Await approval and an email message providing download access to the TREND 
distributions.

Though written in Python, TREND does not depend on a Python environment. The 
simple installation process merely creates shortcuts on the desktop and helps 
set environment variables of for the text shell window that will make TREND 
easy to use. The installation script places on the Desktop a directory 
containing symbolic links to the executable files with GUI.  

The OS X and Linux installation script change the PATH environment variable. 
The Windows script `TRENDterminal.bat` opens a command shell in which all 
executable files of TREND (with suffix of `.exe`) can be invoked, both the 
versions operated by GUI and at the command line. 
Note that the installation process is not completed until the first 
calculations using `trendmain` and `trendreconstruct` trigger the download 
and installation of two pieces of software from the public domain for 
handling movies and images. This download requires both a reliable internet 
connection and access to github. If this access is lacking upon initial 
usage, please see the document [`no_internet_connection.pdf`](../manual/no_internet_connection.md)

#### Windows 7 or above

* Unzip the `TREND-1.0-Win.7z` by [7zip](http://www.7-zip.org).  
* In the unzipped folder, double clicking `install.bat` will create a file
  named `TRENDterminal` and a folder on the desktop and start menu named 
  `TREND-GUI` containing `trendmaingui.exe`, `trendplotgui.exe`, and 
  `trendreconstructgui.exe`. Refresh the desktop by right-clicking in an 
  open area and select `Refresh`.  
* Invoke any of these GUI versions of the executable files by double-clicking
  on them within the `TREND-GUI` folder. If TREND was previously installed, 
  the old version will be uninstalled before new version is installed.   
* An alternative way to run either the GUI or command-line versions of the
  executable files involves first double clicking on `TRENDterminal.bat`.
  This will open a Windows command shell in which you can `cd` to your data 
  folder and invoke the TREND executable files. This does not change your 
  path environment permanently and should be run every time you need a 
  command shell window for TREND.  
* Note the `.7z` tarball can be deleted but the unzipped folder should not
  be removed or deleted, since the installation step just creates shortcuts.  

#### Mac OS X 10.7.5 and later

* Unzip the `TREND-1.0-macOS.tar.gz` by double clicking the file 
  displayed in the OS X GUI. Alternatively, run the command 
  `tar -xzvf TREND-1.0-macOS.tar.gz` within a terminal shell.  
* Open a terminal shell and `cd` to the unzipped folder named 
  `TREND-0.7.8.3-OSX`, enter the command `./install.script` to create a 
  `TREND-GUI` folder on the desktop, which contains `trendmaingui.app`, 
  `trendplotgui.app`, and `trendreconstructgui.app`. 
  The installation scripts can only be executed within the terminal shell.
  (Do not run this script directly from OS X desktop GUI by clicking 
  because the installation script will not work properly).  
* Three icons, `trendmaingui.app`, `trendplotgui.app`, and `trendreconstructgui.app`
  will also be added to `/Applications/TREND`. These icons should be visible 
  in Launchpad and the Applications folder in Finder. (Refreshing Launchpad 
  may be needed).  
* The current TREND directory is also added to the `PATH` environment 
  variable. Three lines will be added to the file `~/.bash_profile`. The 
  lines begin with `#TREND path environment`  
* Open a new terminal or type and enter the command source `~/.bash_profile` 
  within a terminal shell. Now all TREND commands can be launched in a terminal.  
* If TREND was previously installed,  the old version will be uninstalled 
  before the new installation.  
* `sudo` may be necessary if permission is required.  
  An example: Download `TREND-1.0-macOS.tar.gz` to `~/Downloads/`  
* If you are comfortable with shell terminal, you can just enter 
  `./change_path_env.script` to add the current TREND directory to `PATH` 
  environment variable. No permission is required.  
  ```bash
  tar -xzvf TREND-1.0-macOS.tar.gz
  cd ~/Downloads/TREND-1.0-macOS
  ./install.script 
  (or sudo ./install.script if permission is required)
  ```


#### Linux 64-bit, including Ubuntu 14.04, 16.04, Fedora 23 and later, 
RedHat/CentOS 7.x (7.1 and later), CentOS 6.x (6.5 and later)  
* Unzip the `TREND-1.0-Ubuntu14.04.tar.gz` (The string `Ubuntu14.04` 
can be any 
other Linux distribution such as `RHEL7.1` or `Ubuntu16.04`) by 
entering the command 
  `tar -xzvf TREND-1.0-Ubuntu14.04.tar.gz` within a terminal shell.  
* Enter `./install.script` within the terminal shell to add the current 
  TREND directory to the `PATH` environment variable. Three lines will be 
  added to `~/.bashrc`, starting with `#TREND path environment`.   
* Open a new terminal or type `source ~/.bashrc`. Now all TREND commands
  can be launched in terminal.  
* Installation in Linux is similar to OS X, as the `install.script` is 
  written for `bash`, a shell that is the default in Mac OS X and many Linux 
  distributions. 
* However, a Linux computer may run without a desktop and may
  use a shell other than `bash`. In this case, you need to set the path 
  environment variables yourself. e.g., modifying a shell configuration 
  file such as `.bashrc`, `.cshrc`, `.tcshrc`....  
  For example, if you want to install TREND on a CentOS 6.5 platform with 
  `tcsh` or `csh` environment, just add the following 
  lines to your `.cshrc` or `.tcshrc` files:  
  ```bash
  set path = ($path ~/your_directory/TREND-1.0-CentOS6.5/GUI)
  set path = ($path ~/your_directory/TREND-1.0-CentOS6.5/GUI)
  ```   
  Replace `your_directory` with the paretn directory name of the 
  TREND folder.  
  
#### Uninstalling or Moving

* Run `uninstall.bat` in Windows or `uninstall.script` in OS X and Linux.    
* Then delete the `TREND-1.0-Win` ,`TREND-1.0-macOS`, or 
  `TREND-1.0-Ubuntu14.04` folder.  
* To move the TREND folder to a new location, first uninstall it, move 
  the TREND foler to the new location, and install it again, thereby 
  overwriting the previously installed TREND executable files.  

