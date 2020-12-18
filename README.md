# stdlib
An opinionated shell library for macOS

## Usage

Place the `stdlib` file somewhere easily accessible and add the following line to your shell script to make use of the various functions.

```
#!/bin/bash

source /path/to/stdlib

...
```

I've tried to make the functions almost english-like, say we run jamf, want to install Google Chrome when a user is logged in and display a jamfHelper notification on success:

```
#!/bin/bash

source /Library/Managed/stdlib

if user_logged_in
then
  # Run a jamf policy
  run_policy install_chrome
  
  if dir_exists "/Applications/Google Chrome.app"
  then
    jamf_helper "Install Successful" "Google Chrome was successfully installed to your Applications folder" "/path/to/custom.icon"
  fi
fi

```

## Why?

I found I was always repeating myself or finding previous scripts to copy/paste. I could have easily made Clippings of these for BBEdit but I wanted something portable and able to be pushed to clients for use in other scripts.

## Contribute!

Please, if you find an issue, a better way to do something or additions, send a pull request!
