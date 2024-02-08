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

`cp nitter.example.conf nitter.conf`

Customize nitter.conf (set a different port for example)

### Add accounts

Put one set of Twitter credentials in `twitter_oauth.py`, then run it to generate the tokens for Nitter:

`python3 twitter_oauth.py`


### Run
`./nitter`
