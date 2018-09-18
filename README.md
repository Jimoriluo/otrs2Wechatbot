# otrs2slack
Post new OTRS tickets to Slack (written in python)

PREREQUISITES

Debian OS
sudo apt install python3-pymysql python3-requests


SETUP OTRS

Goto Admin -> Generic Agent -> Add Job

Settings:

Job name: OTRS to Slack

Event Based Execution:
  Event Trigger:
    Type: Ticket
    Event: TicketCreate

Select Tickets:
  ie. Queue "Support" only

Execute Ticket Commands:
  CMD: . /opt/.secrets && /opt/otrs2slack.py
