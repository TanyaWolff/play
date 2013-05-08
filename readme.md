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
Still can't push to https url
Found out that connection to github should always be as git user, so I put url back to https://github.com/TanyaWolff/play.git

Config:
[tanya@fit-vm12-25 play]$ cat .git/config
[core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
[remote "origin"]
        fetch = +refs/heads/*:refs/remotes/origin/*
        url = https://github.com/TanyaWolff/play.git
[branch "master"]
        remote = origin
        merge = refs/heads/master

[tanya@fit-vm12-25 play]$ cat ~/.gitconfig
[user]
        name = TanyaWolff
        email = twolff@ca.ibm.com
[push]
        local = simple
[apply]
        whitespace = nowarn
[color]
        branch = auto
        status = auto

