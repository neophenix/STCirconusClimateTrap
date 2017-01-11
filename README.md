# STCirconusClimateTrap
Sends climate data (Temp, UV, Humidity, Lux) from SmartThings sensors to Circonus

## Usage

1. First, you will need a Circonus account, and and HTTPTrap check setup to collect the data.  See here: https://login.circonus.com/user/docs/Data/CheckTypes/HTTPTrap
2. Open your smartthings web portal here: https://graph.api.smartthings.com
3. Go to the My SmartApps tabs, then click + New SmartApp in the upper right
4. Select the From Code tab
5. Open CirconusClimateTrap.groovy and copy the contents into the form, click Create, this will open the code in an editor, leave that open for step 7
6. Open your Circonus UI, and to the HTTPTrap check you've created, the path will be /check/ID, on this page you will find the "Data Submission URL" near the status and details about the check, copy that URL
7. Back in the smartthigns editor, go to line 16, paste the URL you copeid in the last step in there, then change https to http (we do this because smartthings can not currently deal with self signed certs)
8. Click Save
9. Click Publish -> For Me
10. Now that your app is published for yourself, you can find it in your smartthings app, go to the app -> Marketplace -> SmartApps -> scroll to the bottom to find My Apps, click that and select the CirconusClimateTrap app
11. Select the sensors you wish to send data for, Assign any name and mode you wish (optional) and then click Done

The app will now be running in the smartthigns cloud, and push data to Circonus once a minute, after a few minutes you should start seeing your graphs populate with data, and you are on you way to using that data how you see fit in Circonus.
