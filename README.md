# Prepping a Windows 10 Machine to Run an Art Installation 24/7

This document is inspired by Blair Neal's (@laserpilot) [*Installation up 4evr*](https://github.com/laserpilot/Installation_Up_4evr) guide.

1. ~~Create auto launch/relaunch scripts~~ (coming soon)
2. ~~Make these scripts run at startup~~ (coming soon)
3. Configure Task Scheduler to reboot the machine daily
4. Set the time to the correct timezone for the installation location
5. Configure auto login
6. Disable screen lock and snooze
7. Disable automatic software updates
8. Disable notifications
9. Install TeamViewer for remote monitoring and access
10. Protect your personal privacy

Several of these actions require you to open the *Windows Settings* application. To do this, click the Windows icon on the bottom left of the screen, and then select *Settings* (the cog icon).

## 1. ~~Create auto launch/relaunch scripts~~

Coming soon!

## 2. ~~Make these scripts run at startup~~

Coming soon!

## 3. Configure Task Scheduler to reboot the machine daily

**Note**: This is not a necessary task, but can be helpful if you are worried about memory leaks or undefined behavior if your machine runs for long periods of time (days, months, years...) without rebooting.

Open Notepad and save the following contents as a Batch file named `reboot.bat`.

```
shutdown.exe /r /t 00 /f
```

When run, this script will immediately force reboot the machine. Next, configure it to run once per day using "Task Scheduler".

*Task Scheduler > Create Basic Task*

Enter a name and description, like "Reboot", "Reboot the machine daily." Click *Next* and select *Daily*. Click *Next* and select the time you would like the machine to be rebooted. Click *Next* and select "Start a program" when prompted for what kind of action you want the task to perform. Click *Next* and then click *Browse* at the program/script input field. Select your `reboot.bat` script in the file browser and click *Open*. Click *Next* and finish creating your scheduled task.

## 4. Set the correct time

*Windows Settings > Time & Language > Time zone*

Change this value to the appropriate time zone.

## 4. Configure auto login

Press the Windows key + r to open the *Run* program. Type "Netplwiz" and press *Enter*. Select the user you would like to auto login and then uncheck "Users must enter a user name and password to use this computer". Select *Apply* and enter your password (twice). Finally press *Ok*.

For more detailed instructions, or if that didn't work, see [this tutorial](http://www.intowindows.com/how-to-automatically-login-in-windows-10/).

## 5. Disable screen lock and snooze

*Windows Settings > System > Power & sleep*

- When plugged in, turn off after: Never

**Note**: This assumes you are using a desktop computer. If you are using a laptop, there may be other power settings you need to change.

## 6. Disable automatic software updates

**Note**: Disabling updates can make your computer vulnerable to malware and other security vulnerabilities, especially if it is connected to a network. Do so at your own risk.

**Note**: Make sure Windows and all hardware drivers are up to date before following the steps below. 

In Windows 10, users have almost no control over updates. You can choose only how updates are installed, but you cannot turn off or disable Windows updates via the Control Panel or Settings apps. You can, however, disable the service that manages the checking and downloading of updates.

Open the *Services* application (type "Services" into the Cortana search bar). Select the *Windows Update* service, right-click it, and select *properties*. Change *Startup type* to "Disabled". Click *Apply* and restart for the changes to take effect.

For alternative methods of disabling Windows 10 updates, see [this tutorial](http://www.intowindows.com/how-to-disable-windows-update-in-windows-10/).

## 7. Disable notifications

*Windows Settings > System > Notifications & actions*

Turn off:
- Get notifications from apps and other senders
- Show me the Windows welcome experience after updates...
- Get tips, tricks, and suggestions as you use Windows

## 8. Install TeamViewer for remote monitoring and access

Download and install TeamViewer for Windows. When setting up TeamViewer for the first time, select "Installation to access this computer remotely" when prompted with "How do you want to proceed." If you miss this, you can always grant remote access by selecting *Easy Access* on the main TeamViewer window.

 **Note**: Add the machine to your contacts list but **do not** stay signed in (otherwise anyone with access to the machine can login to all of your computers).

## 9. Protect your personal privacy

### Windows privacy settings

*Windows Settings > Privacy > General*

Turn off:

- Let apps use advertising ID to make ads more interesting...
- Let Windows track app launches to improve Start and search results

*Windows Settings > Privacy > Location*

Turn off location services.

*Windows Settings > Privacy > Notifications*

- Let apps access my notifications: Off

*Windows Settings > Privacy > Speech, inking, & typing*.

This is a Windows keylogger and handwriting recognition spyware. Turn that sh!t off...

### Browser Login Sessions and History

The exact method for doing this depends on the browser, but usually there is a history tab in the nav bar. Be sure to delete all history from the beginning of time, including:

- Browsing and download history
- Forms and search history
- Cookies
- Cache
- Active Logins
