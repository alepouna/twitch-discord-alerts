## ⚠️⚠️⚠️ As of 29/02/2024 this repo has been moved to GitLab at https://gitlab.com/alepouna.dev/twitch-discord-alerts

# twitch-discord-alerts

A simple tool to send announcements to your Discord server whenever you go live!
Supports ANY platform as long as Streamer.bot supports it. 

Like this tool? [![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/Y8Y1ACFQW)

# Video Tutorial

[![Video Tutorial](http://img.youtube.com/vi/t8_6bj4dZ50/0.jpg)](https://www.youtube.com/embed/t8_6bj4dZ50 "Video Tutorial")


# Text tutorial 

### A) Requirements 
  - Streamer.Bot
  - NodeJS v16.15.1
  
  
### B) Setting up Streamer.bot
  
  1. Create an action on Streamer.bot, I will name "Discord Webhook Notification" and tick the "Always run" 
  2. Create a Subaction > Network > Fetch URL 
  3. Set the target as `http://localhost:9080/stream/start`
  4. Set the Variable name as `success`
  5. Go to "Stream Apps" select your streaming app and click on a connection (if you don't have one, create one)
  6. Create a new event (on the bottom) for whenever you start the stream to trigger an action [In obs this is "StreamStarted"]
  7. Save 
  
### C) Setting up the app

  1. Clone the files of this app (e.g. by using the green code button > Download Zip)
  2. Extract the files and open a terminal on the folder 
    [In Windows, SHIFT Right click inside the empty space of the folder and select either "Open PowerShell Window here" or "Open Command Prompt window here"
  3. Type in `npm install` 
  4. Copy the file `config.example.json` and rename the copy to `config.json` 
  5. Edit the newly made config.json file as you wish - **MAKE SURE YOU DO NOT REMOVE ANY VARIABLES. IF YOU WISH A FIELD TO BE OPTIONAL, SIMPLY LEAVE IT EMTPY.**
  6. Save the file 
  7. Run the command `node index.mjs`
  
### Voila 

Now anytime Streamer.bot receives an event that you have started streaming by your streaming app, its going to post a discord notification :D 
  

# Running this app forever

Its recommended to run this app once and forget about it. On Windows this is hard, you can use the Task Scheduler to run the node file or create a batch script to do the same thing.

I recommend grabbing an old laptop or another pc or even a Raspberry Pi and run Linux on it. Inside the Linux OS you can then install nodejs and a tool called "pm2" (`npm install pm2 -g`) which allows you to run this app (and any node app) forever. You can read the manual for pm2 for more details. 

