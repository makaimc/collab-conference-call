#Conference Calling

*Conference Calling* is a [Collab](https://github.com/cfpb/collab) application 
that searches the 
[Staff Directory](https://github.com/cfpb/collab-staff-directory) 
and dials every selected participant into a conference call. 


##Pages

Conferencing Calling currently only has two different views:

* Select participants
* Conference dialed

##Screenshot

Simply select "Conference Call" from the Tools menu, or go to 
/conference-call/.

![selection page](screenshots/selection.jpg "Select Participants page")

Hit the "Dial Conference" button once you select the people who you want 
to dial together into a conference. You'll see the success screen below:

![dialed page](screenshots/dial-conference.jpg "Conference dialed page")


##Installation

To use this application you will need to first have 
[Collab](https://github.com/cfpb/collab) along with 
[Staff Directory](https://github.com/cfpb/collab-staff-directory) installed.

Then, once you clone this repo, you can install the application using 
setuptools:

`python setup.py install`

Or, if you are developing with this app, you can add it to your search path 
like:

```
cd collab
ln -s ../collab-conference-call/conference_call .
```

Once the application is installed, add it to core collab's 
`INSTALLED_APPS` in your `local_settings.py` file:

```
INSTALLED_APPS += ( 'staff_directory', 'conference_call', )
```

You'll also need 4 variables in your local_settings.py so you can use 
the Twilio service:

```
TWILIO_ACCOUNT_SID=''  # account sid from your Twilio user page goes here
TWILIO_AUTH_TOKEN=''   # auth token from your Twilio user page goes here
TWILIO_POSTBACK_URL='' # collab server hostname plus /conference-call/postback/
TWILIO_CONF_NUMBER=''  # number purchased from Twilio that initiates the calls

##Contributing

Please read the [contributing guide](./CONTRIBUTING.md).
