# Weather-Audio-
This is bash script to pull json formatted data from the OpenWeatherMap.org API and read data out though espeak text to voice on #Linux. #raspi, #OpenWeatherMap, #espeak, #IoT.  

After Wunderground.com changed availability of API keys I needed another weather source to draw data from for a home and garden automation project.  Noticing a lack of example scripts using Linux native bash commands, I wrote this to share.  The idea was to supply an example which could work well on low powered raspi or other devices often used for IoT. 

There are two files. One is the script which pulls the data and reads out to espeak, the other is cacert.pem to allow for a HTTPS:// connection.  Placed in the same directory, the scrip will auto update the cacert.pem.

You will need to sign up at https://openweathermap.org/price for a free account.  I find their ToS mostly friendly. 

Once you obtain the free API key: add API key to line 4  be tween the “ “. 

To look up the location ID for the area you desire data for, go to openweathermap.org and search for your area.  From the resulting list select the reporting station you intend to pull data from.  In the address bar at the end of the URL will be a seven digit number.  This is the ID# to enter on line 5 between the “ “. 

On line six, enter either metric or imperial for the type of data output you seek. 

To make the file executable:

In the terminal, in the directory you placed the files, execute the following
>chmod 755 weather_git

to run the script execute
>./weather_git

A good source for a walk though on how to set up an openweathermap.org is https://youtu.be/53AoDB7vcbU	   
.
Espeak is not required if you would like to test the script.  Editing the last line at the last pipe as shown below will print data out to the terminal.

"sets at: $sset" | espeak --stdin -ven-sc+f4 -l 3"

edit with a # as such

"sets at: $sset" #| espeak --stdin -ven-sc+f4 -l 3" 

In this script the voice of espeak is set to be a Scottish woman who pauses at the end of each line. 
I find it listenable.
