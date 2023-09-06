# git
Tips and use of git.

## Remote

Two Repositories: **team** and **personal**
I wish to synchronize my personal git with my branch on my team project.
A branch needs to be created in our team repo:

    git branch ecolin
The "ecolin" branch will be created.
Get into the personal repo and add a remote:

    git remote add team https://github.com/elcolin/team

Then it's important to pull from the wanted branch:

    git pull team ecolin

**To add permanantly**

    git config --global --add remote.team.url https://github.com/url/to/team/repo

**NOT MANDATORY**
Does not work if there is a name mismatch
Then you can create a tracking relationship between your main branch on your personal repo and your branch on the team repo:

    git branch --set-upstream-to=team/ecolin main

You won't have to specify the remote each time you push.

To push on your team repo and branch:

    git push team HEAD:ecolin

To push on your base repo:

    git push origin

# Docker
## Launch Docker
On **Linux**

    sudo systemctl start docker
## Build Image
**TODO**
## Remove Image
**TODO**
## Launch Container
**TODO**
## Stop Container
**TODO**


## Frequent errors

### Pulling image

    => ERROR [angular internal] load metadata for docker.io/library/node:16                                                                                 0.4s
    ------
     > [angular internal] load metadata for docker.io/library/node:16:
    ------
    failed to solve: node:16: error getting credentials - err: exit status 1, out: ``
    make: *** [reload] Error 17

 ### Solution
 
     rm  ~/.docker/config.json

# CPP

## References
Use references when you want to avoid copying data and work on the original object:

    void modifyValue(int& x) {
        x = x * 2;
    }
## const
Use const when you want to guarantee the object won't be modified.

    class MyClass {
    public:
        int getValue() const {
            return data;
        }
    private:
        int data;
    };
