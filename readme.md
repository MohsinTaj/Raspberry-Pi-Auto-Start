# Raspberry Pi Auto-Start Scripts with Flask and Chromium

This guide shows how to auto-start a Flask app inside a Python virtual environment on your Raspberry Pi and open Chromium in kiosk mode.

---

## Step 1: Create a Shell Script for Your Project

1. Open a terminal on your Raspberry Pi.
2. Create the script:

```bash
nano ~/myscript.sh

#!/bin/bash
# Navigate to your project directory
cd /home/pi/your_project
# Start your Python server or application
python3 server.py

chmod +x ~/myscript.sh