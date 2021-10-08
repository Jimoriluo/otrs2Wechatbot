# otrs2Wechatbot

推送OTRS最新的工单至企业微信机器人

## PREREQUISITES

python3-pymysql 
python3-requests

## CLONE THE REPO

Clone the repo to a folder on your OTRS host, e.g.:
```
cd /opt
git clone https://github.com/Jimoriluo/otrs2Wechatbot.git
```

## SETUP OTRS

Goto Admin -> Generic Agent -> Add Job

Settings:
* Job name: OTRS to Wechatbot

* Event Based Execution:
  * Event Trigger:
  * Type: Ticket
  * Event: TicketCreate

* Select Tickets:
  * ie. Queue "Support" only

* Execute Ticket Commands:
  * CMD: `. /opt/otrs2wechatbot/.secrets && /opt/otrs2slack/otrs2wechatbot.py`


## SETUP otrs2Wechatbot

Copy .secrets.dist to .secrets file, open it in an editor and setup the URLs and MySQL connection.
