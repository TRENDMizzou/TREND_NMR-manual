# Known limitations by operating system

## macOS 10.12 (Sierra)
- macOS Sierra is very strict in its safety policy. It does not provide 
`Allow app downloaded from anywhere` option anymore. Therefore TREND may 
fail to launch because of the following problem  
<img src="../png/Sierra1.png" alt="error" width="300px">   
- You can override the security settings as described by
  [https://support.apple.com/kb/PH25088?viewlocale=en_US&locale=en_US](https://support.apple.com/kb/PH25088?viewlocale=en_US&locale=en_US)  

	- To override your security settings and open the app anyway:
		- In the Finder, locate the app you want to open.
		- Don’t use Launchpad to do this. Launchpad doesn’t allow you to access the shortcut menu.
		- Control-click the app icon, then choose Open from the shortcut menu.
		- Click Open.  
<img src="../png/Sierra2.png" alt="override" width="400px">  

- Or the gatekeeper of Sierra could be disabled by running the following commands, 
see [https://www.tekrevue.com/tip/gatekeeper-macos-sierra/](https://www.tekrevue.com/tip/gatekeeper-macos-sierra/)  
```bash
sudo spctl --master-disable  
```  

## OS X 10.11 (El Capitan)
- The strict safety precautions of El Capitan prevent double clicking or 
use of the open command in terminal from launching TREND apps. The TREND 
apps may nonetheless be launched in a terminal (text) window. To enable 
opening of the apps by double clicking, enter the system preferences menu 
and go to `Security & Privacy` and select `Allow app downloaded from anywhere`, 
at least temporarily until you have run each of the apps.

## OS X 10.7 to 10.8  
- `GIF movie` option of `trendreconstruct` is not supported  

## Fedora 23 and Ubuntu 16.04  
- `trendmain` and `trendreport` are not able to launch web browser to 
open `-report.html` automatically  

## RedHat/CentOS 7.x (7.1 and later), CentOS 6.x (6.5 and later)  
`libxcb` must be `1.11` or newer. If your have an older `libxcb` library 
(use `rpm -q libxcb` command to check), please upgrade it. You can do 
this using the command 
```bash
yum update libxcb
``` as root   
or 
```bash
sudo yum update lixcb
``` if you have `sudo` privilege.  



## Linux distributions  
- `trendmaingui` may hang when browser launches to show HTML report (if 
`report` option is turned on). If this happens just close the browser and 
GUI of `trendmaingui` will recover.  

If you have any question, please contact <trendmizzou@gmail.com>
