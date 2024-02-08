# For Ubuntu

## Dependencies

`sudo apt install nim redis libsass-dev`


## Build nitter

`nimble build -d:release`

Prompt: No local packages.json found, download it from internet? [y/N]
Answer: y

`nimble scss`

`nimble md`

`cp nitter.example.conf nitter.conf`

Customize nitter.conf

Put Twitter credentials in twitter_oauth.py, then run it to generate the tokens to give to nitter:

`python3 twitter_oauth.py >> guest_accounts.json` # wrap output in square brackets, nitter expects a list of accounts
