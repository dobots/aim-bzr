# AIM

For a proper introduction see the [AIM website](http://mrquincle.github.com/aim-bzr/). This AIM repository currently contains:

* [rur-builder](https://github.com/mrquincle/rur-builder) to generate header files for a range of middlewares
* [aimtools](https://github.com/mrquincle/aimtools), a suite of tools to create, register, copy, and connect modules
* [zmqserver](https://github.com/mrquincle/zmqserver), a nameserver for ZeroMQ connections
* [zmqconnect](https://github.com/mrquincle/zmqconnect), a exogenous coordination method to connect two modules with each other
* [aimserver](https://github.com/mrquincle/aimserver), a REST interface for the aimtools
* [aim_modules](https://github.com/mrquincle/aim_modules), a repository of reusable AI modules

## For users

The AIM modules in the repository are quite "in flux". Hence, we do not yet compile them by default. However, to draw a parallel, to be useful: an operating system requires drivers, a multi-agent system requires functional agents, a machine learning framework requires algorithms. For that reason it would be silly not to compile the AI modules for you, even if that increases the dependencies of this repository. If the modules are compiling entities, it is much easier to think about a REST API that pulls a module from a certain repository and compiles and runs it for you on a server. 

The current modules:

* WriteModule has one output over which it sends a fixed value
* ReadModule reads one input over which it receives a certain value


## For developers

As explained at [kernel.org](https://www.kernel.org/pub/software/scm/git/docs/howto/using-merge-subtree.html) the subtree merge is like this:

    git remote add -f zmqconnect git@github.com:mrquincle/zmqconnect.git
    git merge --strategy ours --no-commit zmqconnect/master
    git read-tree --prefix=zmqconnect/ -u zmqconnect/master
    git commit --message "Merge zmqconnect as subdirectory \"zmqconnect\""
    git push

And later on the merges are done with:

    git pull --strategy subtree zmqconnect master

How to indicate when a module is ready to be included in the compilation process will be described soon.

## Launchpad

The code on Launchpad can be found at:

* https://code.launchpad.net/aim
* https://launchpad.net/~dobots/+archive/ppa
* https://code.launchpad.net/~dobots/+recipe/aim-daily
* http://bazaar.launchpad.net/~dobots/aim/master/files

## Copyrights
The copyrights (2013) belong to:

- License: LGPL v.3
- Author: Anne van Rossum
- Almende B.V., http://www.almende.com and DO bots B.V., http://www.dobots.nl
- Rotterdam, The Netherlands

