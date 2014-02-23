##What is preheat?
Preheat is a very simple, light-weight Dropbox client built for the Raspberry Pi. I was tired of using the Nano text editor or Vim to edit my files directly on the Raspberry Pi. Preheat allows you to make changes in your favorite IDE on your development machine and will pull down your script when you want to run it on your Pi.

##Usage
```shell
[sudo] python preheat [python file]  [options]
```

##Dependencies
  * Python 2.7.3 or greater
  * Dropbox python module

##Getting Started
To use ```preheat``` on your Raspberry Pi you will need to create a Dropbox app. You only have to set this up once and it is very easy. Once your app is created you need to modify preheat to contain your App key and App secret. Change the following lines of code to contain your app data:

```python
app_key = "APP_KEY"
app_secret = "APP_SECRET"
```

The first time you use ```preheat``` it will ask you to authorize your newly created Dropbox app. Once authorized it will store an access token so you don't have to provide credentials on subsequent runs. The script you want to execute can be located anywhere in your Dropbox. If you have multiple files with the same name like **app.py** preheat will prompt you to choose which file to pull down and execute.

###Options
The following are the available options when running the ```preheat``` script.
| Option          | Purpose        |
| :-------------: | :------------- |
| -d | Download the target file only. Do not attempt to run it.  |
| -f | Download the entire contents of the Dropbox folder that contains the target file (including subfolders).  |

###Local Files
If ```preheat``` is unabled to find the requested file in your Dropbox it will check your local directory and, if it finds the file, prompt you to run it.

###Features
  * No special folders needed in your Dropbox. Store your code anywhere
  * Write code from anywhere and run it from your Raspberry Pi
  * Saves Dropbox access token so you only authenticate on the first run
  * Handles multiple instances of a script
  * Easier than setting up an automatic synching network share

###Wish List
The following are features I plan to implement at some point. If you are interested in helping please feel free to submit a pull request.
  * Tracking of file version. Currently all files are downloaded whether the version has changed or not.
  * Move the app_key and app_secret into a separate config file so users don't have to modify the source file
  * Send an email with approval link instead of having to enter the authorization code on the command line

###Version History
**0.1.2** (February 13, 2014)
  * Add download-only option
  * Add option to download entire folder and subfolders

**0.1.1** (January 25, 2014)
  * Support both Windows and Linux environments

**0.1.0** (January 25, 2014)
  * Initial Release
