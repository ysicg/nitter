! Original README.md is in .README.md


### Dependencies (Ubuntu)

`sudo apt install gcc nim redis libsass-dev`

nim version < 2


### Build

`nimble build -d:release`

Prompt: No local packages.json found, download it from internet? [y/N]

Answer: y

`nimble scss`

`nimble md`


### Configure

Make sure you're in the `guest_accounts` branch

`cp nitter.example.conf nitter.conf`

Customize nitter.conf (set a different port for example)


### Add accounts

Put one set of Twitter credentials in `twitter_oauth.py`, then run it to generate the tokens for Nitter:

`python3 twitter_oauth.py`


### Run
`./nitter`


### Setup firewall rules

To keep the instance private and only allow specific IP addresses, use `ufw` as follows:

We will use the default port 19999, but if you setup Nitter to run an on different port, put that instead.


- First reset the firewall rules 

> `sudo ufw reset`


- Allow ssh 

> `sudo ufw allow 22`


- Then allow the white listed IPs, one IP at a time

> `sudo ufw allow from IP_ADDRESS_1 to any port 19999`

> `sudo ufw allow from IP_ADDRESS_2 to any port 19999`

etc.


- Only then, deny the rest

> `sudo ufw deny from any to any port 19999`


- Enable ufw with

> `sudo ufw enable`


- Check if things are configured correctly

> `sudo ufw status verbose`


###### Note:

Because firewall rules are ordered, we must reset them every time we want to add/modify/delete an IP address to/from the whitelist.
Meaning that the commands above need to be rerun.

