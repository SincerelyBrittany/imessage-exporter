# imessage-exporter

This crate provides both a library to interact with iMessage data as well as a binary that can perform some useful read-only operations using that data. The aim of this project is to provide the most comprehensive and accurate representation of iMessage data available.

This software can:

- Save, export, backup, and archive iMessage data to open, portable formats
- Preserve multimedia content (images, videos, audio) from conversations
- Facilitate easy migration of message history between devices and platforms
- Run diagnostics on the iMessage database
- Give you full ownership and control over your communication history
- Support compliance with data retention policies or legal requirements
- Run on macOS, Linux, and Windows

## Example Export

![HTML Export Sample](/docs/hero.png)

## Binary

The `imessage-exporter` binary exports iMessage data to `txt` or `html` formats. It can also run diagnostics to find problems with the iMessage database.

Installation instructions for the binary are located [here](imessage-exporter/README.md).

## Library

The `imessage_database` library provides models that allow us to access iMessage information as native data structures.

Documentation for the library is located [here](imessage-database/README.md).

### Supported Features

This crate supports every iMessage feature as of macOS 15.0.1 (24A348) and iOS 18.0.1 (22A3370):

- Multi-part messages
- Replies/Threads
- Formatted text
- Attachments
- Expressives
- Tapbacks
- Stickers
- Apple Pay
- URL Previews
- App Integrations
- Edited messages
- Handwritten messages

See more detail about supported features [here](docs/features.md).

## Frequently Asked Questions

The FAQ document is located [here](/docs/faq.md).

# Notes for beginners
To save your long iMessage thread as a PDF using the imessage-exporter, you'll first need to export the messages in HTML format, as the tool does not directly support PDF exports. Here’s a step-by-step guide to accomplish this:

Step 1: Install imessage-exporter
You can install the imessage-exporter using Cargo (recommended):

Open your terminal.
Run the following command:
bash
Copy code
cargo install imessage-exporter
Step 2: Export iMessage Data
Next, you'll need to export your iMessage data in HTML format. Use the command below, adjusting the start and end dates as necessary to cover the 10 years of your messages:

bash
Copy code
imessage-exporter -f html -s YYYY-MM-DD -e YYYY-MM-DD -o ~/exported_imessages
Replace YYYY-MM-DD with the appropriate start and end dates for your messages. If you want to export all messages, you can omit the -s and -e flags:

bash
Copy code
imessage-exporter -f html -o ~/exported_imessages
Step 3: Convert HTML to PDF
After exporting your messages as HTML, you’ll need to convert the HTML files to PDF. Here’s how you can do that:

Option 1: Using a Web Browser
Open the HTML file in a web browser (e.g., Safari or Chrome).
Print the page (Cmd + P).
In the print dialog, select "Save as PDF" from the PDF dropdown in the lower-left corner.
Option 2: Using Command Line Tools
If you prefer a command line approach, you can use a tool like wkhtmltopdf:

Install wkhtmltopdf using Homebrew:

bash
Copy code
brew install wkhtmltopdf
Convert the HTML file to PDF with the following command:

bash
Copy code
wkhtmltopdf ~/exported_imessages/your_exported_file.html ~/exported_imessages/output.pdf
Notes
Make sure to check the permissions for your browser or any tools you use, especially for accessing local files.
If you have many HTML files, you may need to run the wkhtmltopdf command for each file or use a script to batch process them.
By following these steps, you should be able to successfully export your iMessage thread to a PDF! Let me know if you need any more help.



------

Instructions for Installing imessage-exporter
Step 1: Install Rust (which includes Cargo)
Open Terminal:

Go to Finder.
Click on Utilities.
Open Terminal.
Install Rust:

In the Terminal, type the following command and hit Enter:
bash
Copy code
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
When prompted, hit Enter again to proceed with the standard installation.
Close Terminal:

Close the Terminal window by clicking the X at the top left. This ensures Rust is properly set up.
Step 2: Install imessage-exporter
Reopen Terminal:

Open Terminal again as you did before.
Install imessage-exporter:

Type the following command and hit Enter:
bash
Copy code
cargo install imessage-exporter
This may take a few moments and could result in an error.
Install Command Line Developer Tools:

If prompted to install command line developer tools, click on Install.
Agree to the terms and conditions. This installation may take a few minutes, so be patient.
Rerun the Installation:

Once the developer tools are installed, go back to the Terminal.
Use the up arrow key on your keyboard to bring back the last command (cargo install imessage-exporter) and hit Enter again to run it.
Step 3: Run imessage-exporter
Run the Export Command:
Type the following command into the Terminal, replacing XXXXXX with your Mac username:
bash
Copy code
/Users/XXXXXX/.cargo/bin/imessage-exporter -f html -c compatible
This process may take some time depending on how many messages you have.
Step 4: Find Your Exported Files
Open Finder:

Go to Finder.
Navigate to Exported Files:

Go to the following path:
bash
Copy code
/Users/XXXXXX/imessage_export
Replace XXXXXX with your Mac username.
The exported files will be in HTML format and named after the phone numbers of your contacts. You can sort them by size to locate your top contacts more easily.


-----------

ou can find your MacBook username in several ways:

Method 1: Using Terminal
Open Terminal:

Go to Finder > Utilities > Terminal.
Check Username:

Type the following command and hit Enter:
bash
Copy code
whoami
Your username will be displayed in the Terminal.
Method 2: Using System Preferences
Open System Preferences:

Click on the Apple logo in the top-left corner of your screen and select System Preferences.
Select Users & Groups:

Click on Users & Groups.
Your username will be listed on the left side. It may show as "Admin" or "Standard" under your name.
Method 3: Check Home Folder
Open Finder:

Click on Finder.
Go to Home Folder:

In the sidebar, click on Home (it may be represented by a little house icon).
The name of the folder is your username.


-------
https://www.reddit.com/r/MacOS/comments/14jy8h7/comment/lbsmks9/


Instructions for installing iMessage-exporter for people who don't code:

1.      First install Rust which contains Cargo:
a.      Open Terminal by going to Finder, Utilities, Terminal
b.      Type this: curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
c.      Hit enter
d.      Hit enter again when it prompts you if you want to customize or proceed with standard installation
e.      Close the Terminal window by hitting X (this makes Rust take effect)

2.      Now install the iMesssage-exporter tool
a.      Reopen Terminal by going to Finder, Utilities, Terminal
b.      Type this: cargo install imessage-exporter. This will run for a bit and then throw an error.
c.      You will be asked to install command line developer tools. 
d.      Tap on “install”.
e.      Tap on “Agree” to the terms and conditions. This install takes a good few minutes so be patient.
f.       Now go back to that Terminal window and rerun the cargo install:
g.      Tap on the Terminal, arrow up to bring back the last command, then hit enter.

3.      You are ready to run iMessage-exporter. Note that this will run for a while, depending on how many text messages you have downloaded in the Messages app. In your Terminal window, type this command (where XXXXXX is your Mac username): /Users/XXXXXX/.cargo/bin/imessage-exporter -f html -c compatible 

4.      To find the exported files, open Finder and navigate to /Users/XXXXXX/imessage_export. They are html files and named after the phone number. Sort them by size to easily locate your top contacts.


## Special Thanks

- All of my friends, for putting up with me sending them random messages to test things
- [SQLiteFlow](https://www.sqliteflow.com), the SQL viewer I used to explore and reverse engineer the iMessage database
- [Xplist](https://github.com/ic005k/Xplist), an invaluable tool for reverse engineering the `payload_data` plist format
- [Compart](https://www.compart.com/en/unicode/), an amazing resource for looking up esoteric unicode details
- [Archive.org](https://archive.org/details/darwin_0.1), for hosting the Darwin source referenced in reverse engineering the `typedstream` format
