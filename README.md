1) Download Events as CSV

```bash
gem install badslava2csv
badslava2csv --city "San Francisco" --output-dir $(pwd)
```

2) Import Events to Google Calendar

* Open Google Calendar on a computer. Note: You can only import from a computer, not a phone or tablet.
* In the top right, click Settings Settings > Settings.
* Open the Calendars tab.
* Click Import calendars between the "My calendars" and "Other Calendars" sections.
* Click Choose File and select the file you exported. Upload the file from Step 1

3) Optional: Install a cronjob

```bash
crontab -e

0 11 * * 1 badslava2csv -p -o $(pwd)/data -c "San Francisco" && terminal-notifier -message "import $(pwd)/data/google.csv"
```
