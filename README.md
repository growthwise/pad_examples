# Power Automate Exmaples #

This repository is for sharing Power Automate flows designed for Xero Accounting

# Superannuation Check Bot #

## Getting Started ##

To setup this flow you need the following:

A CSV file with two headers, organisation_name and shortcode

For each row add the data for each Xero organisation that you wish to process

When you login to Xero, the shortcode is this part of the URL https://go.xero.com/app/[THISBIT]/dashboard it will look like !wr1224 or similar, this is what you want in the shortcode column

The organisation name should just be the organisation name you wish to use. 

See https://github.com/growthwise/pad_examples/blob/main/super_urls.csv as an example, you will need to update the data accordingly to your own organisations and shortcodes

You can download that file and update it according to your own needs (note: you'll need it later in these instructions)

## Seting up the flow ##

Open power automate and create a new flow - make sure you **toggle PowerFX to be on** when you create the flow.

Go to this page https://github.com/growthwise/pad_examples/blob/main/super_check_bot

Copy and paste the data from it into your new flow.

## Fixing the Element Selections ##

PowerAutomate desktop to the best of my knowledge does not have a way of actually sharing a flow like this with elements already preset - so follow the steps below to fix the errored steps, the errors are just because we need to teach powerautomate again the browser elements to target. 

We also have a video on how to complete this here: [insert youtube url]

Open Microsoft Edge and the login to Xero - this will allow you to use power automates UI Element Picker

There are 3 steps that will need your attention:

- Step 13: You need to locate the element for "end date" using control click in the browser to identify the element
- Step 14: You need to locate the element "View" (the view button) using control click in the browser to identify the element
- Step 16: You need to locate the elemenet for Span 'gridcoloum-1018-textEl' (the select all button) using control click in the browser to identify the element

To fix them, double click on the step then click in the "UI Element" box 

Click on Add UI Element

Scroll over the relevane element and control + left click to select it. 

*If you're not seeing the red boxes around the elements you may need to install the powerautomate extension. See here https://learn.microsoft.com/en-us/power-automate/desktop-flows/install-browser-extensions*

Repeat this for each required element in the steps listed above. 

## Running the Flow ##

Once you've got the elements sorted its time to click on "Run" 

You will be asked to select a date, this is the date that we're going to input as our super due date end date. 

You will then need to select your CSV file containing your Xero organisation data

From here on, since we were logged in earlier the browser should continue to run the flow, if it fails you may need to login to Xero first in the created browser window (just press stop on the flow and then login)
Once you're logged in press run again. 

The flow will display some messages along the way just to indicate what is happening - you can press OK on these dialog boxes. 

The last part of the flow, you will be shown the super liability based on your set due date, and the overall super liability of the organisation. 

The flow will repeat this for every record in your CSV file. 

## Speeding up the flow ##

Since we're using this as an example there are things that are shown like the display messages for dates and the URL variable. You can disable these so the flow is not as interrupted. We've left them in to help you troubleshoot.

## How you could extend the flow ##

We've made this flow with expansion in mind, for example instead of just displaying the super liability amounts as a message - you could write them to a spreadsheet for all extracted results. 

Enjoy Building, and share what you create :-)

*If this repo has been helpful go check out our Youtube channel www.youtube.com/@growthwise or connect with me on Linkedin https://www.linkedin.com/in/beaugaudron/*
