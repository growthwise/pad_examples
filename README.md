# Power Automate Exmaples #

This repository is for sharing Power Automate flows designed for Xero Accounting

# Super Overall Liabilty #

*Getting Started*

To setup this flow you need the following:

A CSV file with two headers, organisation_name and shortcode

Then for each row add the data for each Xero organisation

When you login to Xero, the shortcode is this part of the URL https://go.xero.com/app/[THISBIT]/dashboard it will look like !wr1224 this is what you want in the shortcode column

The organisation name should just be the organisation name you wish to use. 

Save this file somewhere as you will need it later

*Set up the flow*

Open power automate and create a new flow - make sure you **toggle PowerFX to be on** when you create the flow.

Go to this page https://github.com/growthwise/pad_examples/blob/main/super_overall_liability 

Copy and paste the data from it into your new flow and save. 

Remember the CSV file from earlier? Update step 4 to reference wherever you stored that file

*Running the Flow*

You will be asked to select a date, this has been entered to allow you to further iterate on this script later, you can select any date

Upon the first run, its best to login to Xero and then stop the flow and re-run it. This ensures you are already logged in to Xero

The flow will then go to autosuper and extract the overall super liability shown on the page. 

## How you could extend the flow ##

Since we have the date already defined, experiment with things like entering a due date end and extracting not just overall liability, but the liability for a selected date

Also look at doing things like saving the values to a spreadhseet.

Enjoy!

*If this repo has been helpful go check out our Youtube channel www.youtube.com/@growthwise or connect with me on Linkedin https://www.linkedin.com/in/beaugaudron/*
