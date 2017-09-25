# AutoUpdaterLibrary-Dll-file
## Every new version will post here in the same Directory like this name ```AutoUpdaterLibraryV1.0``` , etc..
## This project for free for ```lifetime``` :)
## Any questions and Tips & Problems contact me at this email ```c3dc8b8d@opayq.com  ```  
## Every Method on the class have a Description just ```hover it on your mouse!```
## Add the library as a refernce and use it!


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
