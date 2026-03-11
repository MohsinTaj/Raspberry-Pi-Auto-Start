Step 1: Create a shell script

Open a terminal on your Raspberry Pi.

Create a new .sh file:

nano ~/myscript.sh

Inside the file, write your commands. For example:

#!/bin/bash

cd /home/pi/your_project

python3 server.py


Save the file with Ctrl + O and exit with Ctrl + X.

chmod +x ~/myscript.sh

Step 3: Add the script to autostart

You can use crontab for auto-start:
crontab -e

Add this line at the end:

@reboot /home/pi/myscript.sh


For Flask

nano ~/start-flask.sh

#!/bin/bash

sleep 10

cd /home/pi/your_project

source venv/bin/activate

export FLASK_APP=server.py

export FLASK_ENV=production   # or development

flask run --host=0.0.0.0 --port=5000

chmod +x ~/start-flask.sh

for browser to open auto (chromium is taken here you can take any browser of your choice)
For Chromium (Auto-start in Kiosk Mode)

Create a script:
nano ~/chromium-start.sh


Add the following commands:

#!/bin/bash

sleep 10

chromium-browser --app=http://localhost:5173 --start-fullscreen --noerrdialogs 
--disable-infobars

Make it executable:

chmod +x ~/chromium-start.sh

Add to autostart via crontab:
@reboot /home/pi/chromium-start.sh