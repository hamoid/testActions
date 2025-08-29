A quick test of caching apt packages in GitHub actions for faster completion of actions.

Here I tested running `xvfb-run glxinfo -B`. In worst case it has taken over 2 minutes in the past. Caching makes it happen in a second.

I also tested having two separate actions that need the same package to see if it's cached for both. It seems to be the case.
