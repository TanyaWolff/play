Cool, the https protocol actually works!
I was playing around with ssh
Tried
eval `ssh-agent`
env |grep SSH_AUTH_SOCK
env |grep SSH_AGENT_PID 
ps -ef | grep ssh-agent
kill -9 $extra-agent # those that aren''t the one I just added
ssh-add -l
ssh-add ~/.ssh/id_rsa
sse-add -l

But that didn''t work

I changed repo url to 
https://TanyaWolff@github.com/TanyaWolff/play.git by:
git remot set-url origin https://TanyaWolff@github.com/TanyaWolff/play.git
Then when I did a git push, it prompted for password (my github account pw).
And the push was successful!
Oops, spoke too soon.
I followed the guidelines at https://help.github.com/articles/using-ssh-over-the-https-port to force ssh over 443

