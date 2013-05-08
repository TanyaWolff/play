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
So 2 questions:
1 Now how do I do a silent push, without prompting for pw?

2 If I made a new account on github with user tanya, would I be able to remove
the user in the url, since I am su - tanya in bash?
