# Bash script and systemd service to send IP address on boot

The goal of this script is to have a headless Linux server send its local IP address to a non-technical user.

## IFTT and script setup

* Copy the bash script somewhere that is accessible during boot.
* Use the user's IFTT account to create a Webhook event that sends a notification when triggered
* Use Value1 as one of the ingredients.
* Go to the IFTT Webhook documentation and copy the provided curl command.
* Paste the IFTT curl command to the alarm-online bash script
* Execute alarm-online (make it executable) and ensure it works correctly

## Configure to run when network is available

* Copy the provided systemd service to /etc/systemd/system
* Update the service file to point to the bash script.
* Run (sudo) systemd start alarm-online and ensure it works correctly.
* Run (sudo) systemd enable alarm-online
* Reboot and wait for the notification.
