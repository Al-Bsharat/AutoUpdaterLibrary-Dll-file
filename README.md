# AutoUpdaterLibrary-Dll-file

## Getting Started
```AutoUpdaterLibrary : it's a library to make your Auto Updater like what you want .```
```Every new version will post here in the same Directory like this name ```AutoUpdaterLibraryV1.0``` , etc..```
This Library for free for ```lifetime``` :)
Every Method on the class have a Description just ```hover it on your mouse!```
Any questions and Tips & Problems contact me at this email ```c3dc8b8d@opayq.com  ``` 
## Prerequisites
```
1- Make a json file to use it with the library .
2- your updates link must be a mediafire -> www.mediafire.com
```
That's all :)
## Installing
Add the library as a ```reference``` and use it!


```
 string jsonParameter = "version";      
                                                                    // Your Json file                    //the current version  //the Json property
            if (AutoUpdaterLibrary.AutoUpdaterLibrary.Check4Update("https://pastebin.com/raw/ZvF73qhu",  1.0                    , ref jsonParameter))
            {
                AutoUpdaterLibrary.AutoUpdaterLibrary
                    .StartUpdateAsync("Your Mediafire URL", null, WhenDownloadIsFinished, WhenDownloadingIsRunning).Wait();
                /* 
                  *  When you want to download more files use this method .
                  *  This method take 2 overload ( for sigle link and multi link -> shoud send a string array
                */
                AutoUpdaterLibrary.AutoUpdaterLibrary.
                    InstallAdditionalFileAsync("Your Url").Wait();
            }

            // This method will be call when file  finished download
            void WhenDownloadIsFinished()
            {
                Console.WriteLine("Download  finished");
                // here the progress logic ... like delete first version and restart application etc ...
            }

            // This method called every byte downloaded.
            void WhenDownloadingIsRunning()
            {
                // Return the file progress percentage 
                Console.WriteLine(AutoUpdaterLibrary.AutoUpdaterLibrary.ProgressPercentage);

                // Or
                // Return total file size In(MB)
                Console.WriteLine(AutoUpdaterLibrary.AutoUpdaterLibrary.TotalFileSize);

                //Or
                // Return total file size In(MB)
                Console.WriteLine(AutoUpdaterLibrary.AutoUpdaterLibrary.TotalFileRecevied);
            }
```
