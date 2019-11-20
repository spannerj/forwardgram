# forwardgram
Forward messages from multiple Telegram channels to one output channel.

The code is running on an Ubuntu EC2 instance on AWS

To access ssh in passing the location of the pem file

```
ssh -i ~/Documents/code/spannerj_aws.pem ubuntu@ec2-18-224-171-219.us-east-2.compute.amazonaws.com
```

If you need to copy anything from your machine to the server copy this example:
```
scp -i ~/Documents/code/spannerj_aws.pem /Users/Spencer/Code/scripts/forwardgram/forwardgram.session ubuntu@ec2-18-224-171-219.us-east-2.compute.amazonaws.com:~/.
```

The app is running in a loop inside a screen session. To access you can list the sessions:

``` 
screen -ls
```

Then attach to your session using the screen id. For example:
```
screen -r 3634.pts-0.ip-172–31–34–247
```

To detach from the session (and to leave running):
```
CTRL + A + D
```

If you need to create a new screen session simply enter:
```
screen
```

## Setup
Create virtual env if not already created:
```
python3 -m venv venv`
```

Activate the environment:
```
source venv/bin/activate
```

Install requirements:
```
python -m pip install -r requirements.txt
```

## Run
```
python forwardgram.py config.yml
```