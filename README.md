# Verus-Builders
Docker build environments for VerusCoin

This is where the Dockerfile definition is kept, with auto-builds onto [davidldawes on Docker hub](https://hub.docker.com/r/davidldawes/verus-builders).

The container makes it easy to build VerusCoin for assorted Linux distributions and windows. Mac is currently not available.

Get the automatically built Docker container defintion from [Docker hub](https://hub.docker.com/r/davidldawes/verus-builders). You select the operating system by using the appropriate tag when fetching and referencing the container. The following list of operating systems supported also shows you which tag to use to get the correct container.

**Supported Operating Systems**
* **centos** - asherd/verus-builders:verus-centos 
* **ubuntu** - asherd/verus-builders:verus-ubuntu 
* **windows** - asherd/verus-builders:verus-windows 

# VerusCoin
Arguably the world's most advanced technology, zero knowledge privacy-centric blockchain, Verus Coin brings Sapling performance and zero knowledge features to an intelligent system with interchain smart contracts and a completely original, combined proof of stake/proof of work consensus algorithm that solves the nothing at stake problem. With this and its approach towards CPU mining and ASICs, Verus Coin strives to be one of the most naturally decentralizing and attack resistant blockchains in existence.

# Building VerusCoin
You can get things up and running with a docker pull & docker run command. You can leave the -v command out if you're just pushing results back to github, but be aware that without the -v on the docker run command, on exiting the container all of the disk contents are reset and any clones and builds and especially updates you did within the container will be lost.

    mkdir ~/centos-builder-docker
    docker pull asherd/verus-builders:verus-centos
    docker run -v ~/centos-builder-docker:/build -it asherd/verus-builders:verus-centos /bin/bash
    [root@168c1a5eb6d7 build]#

We're now in the build directory of the container, which is mapped to centos-builder-docker on the computer's drive. From there you can clone the code and launch a build in the container, since all the tools are already installed.

    [root@168c1a5eb6d7 build]# git clone https://gitlab.com/VerusCoin/VerusCoin.git
    Cloning into 'VerusCoin'...
    remote: Enumerating objects: 112905, done.
    remote: Counting objects: 100% (112905/112905), done.
    remote: Compressing objects: 100% (27229/27229), done.
    remote: Total 112905 (delta 85046), reused 112782 (delta 84958)
    Receiving objects: 100% (112905/112905), 85.78 MiB | 10.65 MiB/s, done.
    Resolving deltas: 100% (85046/85046), done.
    [root@168c1a5eb6d7 build]# cd VerusCoin/
    [root@168c1a5eb6d7 VerusCoin]# zcutil/build.sh

It's time consuming and produces piles of output.

## Speeding Up the Build
You can add the -j command line option to the ./zcutils/build.sh command to take advantage of multiple threads to speed things up; if you have a 4 core system then use

    ./zcutil/build.sh -j4

Note that it makes it a little harder to track errors, since they often occur before the other threads finish so you end up having to scroll back through a mess of text to find them.

