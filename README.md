##What is preheat?
Preheat allows you to pull down python scripts from your Dropbox account on the Raspberry Pi at runtime. I was tired of using the Nano text editor or Vim to edit my files directly on the Raspberry Pi. Preheat allows you to make changes in your favorite IDE on your development machine and will pull down your script when you want to run it on your Pi.

##Usage
```shell
[sudo] python preheat [python file]
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

###Local Files
If ```preheat``` is unabled to find the requested file in your Dropbox it will check your local directory and, if it finds the file, prompt you to run it.

###Features
  * No special folders needed in your Dropbox. Store your code anywhere
  * Write code from anywhere and run it from your Raspberry Pi
  * Saves Dropbox access token so you only authenticate on the first run
  * Handles multiple instances of a script
  * Easier than setting up an automatic synching network share