# terminalAlert
Use this shell script to alert you (via system notifications on your Mac) when your terminal command has completed


When running a long shell script/command, it's nice to go browse some aimless chatter on twitter, and it would be even better to know when the proccess is complete and you can get back to work.  That's what this shell script and alias set up is for.  The following are the instructions, had I given this missive more time I'd have made more brief.

## 1.  Make the Shell Script.

Find a nice quiet place to store your shell scripts.  I went with ```~/Users/itali43``` , b/c that's where my bash profile is (next step, don't worry we'll cover it fully).

So Create the .sh file (or any file, it's not required to be .sh) and call it 'alertme.sh' like so:
```touch alertme.sh```
Next edit this file, I like vi, so I did 
```vi alertme.sh```
Then copy and paste all (~3 lines) of the accompanying .sh file in this project into the new file you just made.  It looks like this: 



Great, get out of insert ```esc```, save and quit ```:wq```.

Last thing before aliasing, make the file executable from outside of the alertme.sh file (man that's poor wording), using the following command:
```chmod +x alertme.sh```

## 2. Add to Alias

Aliases are really great, they are custom shortcuts in bash. 

You should be in your current user's directory (same as above, ```~/Users/itali43```) for this part, if you aren't already.

Check to see that you have a bash_profile:
```ls -a```
You're looking for this little guy: ```.bash_profile```.  If you don't have one, create one. (the ```touch``` command should work for that).

If you do / after you've made it, give her a: ```vi .bash_profile```

Edit it so that it looks like this:
``` 
# added by Anaconda 2.0.1 installer <~(this is a comment, hooray! - itali43)
export PATH="/Users/itali43/anaconda/bin:$PATH"
EDITOR=nano
alias lola="git lola"
alias u='cd ..; pwd'
alias hi='~/alertme.sh'

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

# Setting PATH for Python 3.6
# The original version is saved in .bash_profile.pysave
PATH="/Library/Frameworks/Python.framework/Versions/3.6/bin:${PATH}"
export PATH
```
NOTE:  I have two additional alias's defined there just to give you a feel of what they look like, but the only required one for this to work is: 
```alias hi='~/alertme.sh'```

Once that's copied, give that escape key and a ```:wq``` (save and quit), and you should be done.

Next time you start up a new terminal window (when bash reloads) you can use your new alert.

## 3. DONE! How to use:

So, in practice you just have to add ``` ; hi ``` to the end of your command.  Note "hi" is the alert I chose, you can use something different if you'd like.

```pod update; hi```

Result:

![Image of Result](https://github.com/itali43/terminalAlert/blob/master/terminalAlertImage.png)


## GREAT SUCCESS


