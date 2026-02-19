# Student Attendance Tracker - Setup Script

## Overview

This script automates the creation of a project workspace for the Student Attendance Tracker. It sets up the required directory structure, copies essential project files into their respective locations, and allows optional configuration of attendance thresholds.

Additionally, the script is designed to handle unexpected interruptions by archiving incomplete setups before exiting.


## Prerequisites

Ensure the following required files are present in the same directory as the script before execution:

* attendance_checker.py
* assets.csv
* config.json
* reports.log

Also confirm that Python 3 is installed on your system.



## Running the Script

1. Make the script executable:

chmod +x setup.sh

2. Run the script:

./setup.sh

3. When prompted, enter a name for your project directory.
   The script will automatically create a directory in the format:

attendance_tracker_<your_input>

4. You will then be asked if you want to update attendance thresholds.
   Enter `yes` to provide custom warning and failure thresholds, or `no` to use the default values.


## Directory Structure Created

attendance_tracker_<your_input>/
├── attendance_checker.py
├── Helpers/
│   ├── assets.csv
│   └── config.json
└── reports/
    └── reports.log

## Triggering the Archive Feature

The archive feature is activated when the script is interrupted during execution.

To trigger this manually:

Press:
Ctrl + C

While the script is running.

When interrupted:

* The current project directory will be compressed into a `.tar.gz` archive.
* The incomplete project setup will be removed.
* The archive will be saved as:

attendance_tracker_<your_input>_archive.tar.gz

This ensures that partially completed setups are preserved before cleanup.


## Notes

* The archive feature only activates if the script is interrupted before completion.
* If execution completes successfully, no archive will be created.

