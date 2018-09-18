# otrs2slack
Post new OTRS tickets to Slack (written in python).

## PREREQUISITES

Debian OS:
```
sudo apt install python3-pymysql python3-requests
```

## CLONE THE REPO

Clone the repo to a folder on your OTRS host, e.g.:
```
cd /opt
git clone https://github.com/magenbrot/otrs2slack.git
```

## SETUP OTRS

Goto Admin -> Generic Agent -> Add Job

Settings:
* Job name: OTRS to Slack

* Event Based Execution:
  * Event Trigger:
  * Type: Ticket
  * Event: TicketCreate

* Select Tickets:
  * ie. Queue "Support" only

* Execute Ticket Commands:
  * CMD: . /opt/otrs2slack/.secrets && /opt/otrs2slack/otrs2slack.py

## SETUP SLACK

Visit this link on [slack.com](https://api.slack.com/apps?new_app=1). Log in with the account you want to have OTRS tickets posted to.

Give the app a name and select the workspace. Navigate to incoming webhooks and switch them on.

"Add New Webhook to Workspace" and select the channel where you want the messages to show up. Remember the webhook URL for the next step.

## SETUP otrs2slack

Open the .secrets file in an editor and setup the URLs and MySQL connection.
