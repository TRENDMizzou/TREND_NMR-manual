### Initial uses of TREND without internet connection

`trendmain` and `trendreconstruct` depend upon `moviepy` and `imageio` to read, process, and write movies. During first uses with a fully functional internet connection, imageio automatically downloads and installs `ffmpeg` and
`freeimage` to the appdata directory. However, absence of a stable internet connection may prevent these downloads and prevent TREND from processing and exporting movies. Running TREND later with an internet connection should rectify this. Alternatively, `ffmpeg` and `freeimage` should be downloaded manually and placed in the `appdata` directory.

### Windows (both 32 and 64-bit)
- Download and unzip [no_internet_patch_Windows.7z](https://www.dropbox.com/s/j6qokat4g8ynn5h/no_internet_patch_Windows.7z?dl=0). 
If dropbox is blocked in your country, please use the [alternative download
link](http://courses.biochem.missouri.edu/trend/no_internet/no_internet_patch_Windows.7z)
- Run `install_imageio_thirdparty.bat` or manually copy imageio folder to the `appdata` directory: `C:\Users\your_user_name\AppData\Local`  


### OS X 10.7, 10.8
- Download and unzip [no_internet_patch_OSX_10.7_10.8.tar.gz](https://www.dropbox.com/s/pn0u0eysn7cfzwb/no_internet_patch_OSX_10.7_10.8.tar.gz?dl=0)  
If dropbox is blocked in your country, please use the [alternative download
link](http://courses.biochem.missouri.edu/trend/no_internet/no_internet_patch_OSX_10.7_10.8.tar.gz)


### OS X 10.9 or later  
- Download and unzip [no_internet_patch_OSX.tar.gz](https://www.dropbox.com/s/f4lxfdnp7w71rnl/no_internet_patch_OSX.tar.gz?dl=0)  
If dropbox is blocked in your country, please use the [alternative download
link](http://courses.biochem.missouri.edu/trend/no_internet/no_internet_patch_OSX.tar.gz)  
- Run `./install_imageio_thirdparty.script` in a terminal or copy the `imageio` folder to the `appdata` directory by typing this command in a terminal:   
  `cp -r imageio /Users/your_user_name/Library/Application Support/`
- Note the `appdata` directory `/Users/your_user_name/Library/Application Support/` is hidden in Finder.  

### Linux  
- Download and unzip [no_internet_patch_Linux.tar.gz](https://www.dropbox.com/s/s5gqpghy8id6q2u/no_internet_patch_Linux.tar.gz?dl=0)  
If dropbox is blocked in your country, please use the [alternative download
link](http://courses.biochem.missouri.edu/trend/no_internet/no_internet_patch_Linux.tar.gz)  
- Run `./install_imageio_thirdparty.script` in a terminal or copy `imageio` folder to the `appdata` directory by typng command within terminal shell:   
`cp -r imageio ~/.imageio`  
- Note the `appdata` directory `~/.imagio` is hidden in either desktop or terminal shell except using command `ls -a .imageio`  



**Please note:** All versions are 64-bit unless otherwise noted. 







