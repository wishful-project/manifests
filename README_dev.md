Developer Installation
======================

1. Create an account at our gitlab -> Go to: https://github.com/

2. Upload your public key into you account settings.

3. Install requirements:

        sudo apt-get install wget git python python-virtualenv python-dev python3-dev python3-pip

4. Configure your git credentials:

        git config --global user.name "Your Name"
        git config --global user.email "you@example.com"

5. Download git-repo:

        wget https://storage.googleapis.com/git-repo-downloads/repo
        chmod a+x ./repo

5. Get manifest files:

        python2 ./repo init -u ssh://git@github.com/wishful-project/manifests.git
        python2 ./repo init -m dev.xml

6. Get all repositories:

        # to get all repositories
        python2 ./repo sync
        # set master branch for all repos
        python2 ./repo forall -c 'git checkout master'
        # set dev branch if repo has one
        python2 ./repo forall -c 'git checkout dev'
        # to check status of all repositories
        python2 ./repo status


Installation
============

1. Create virtual environment:

        virtualenv -p /usr/bin/python3 ./dev

2. Activate virtual environment:

        source ./dev/bin/activate

3. Install all dependencies (if all needed):

        pip3 install -U -r ./.repo/manifests/requirements_dev.txt

4. Deactivate virtual environment (if you need to exit):

        deactivate

Running examples
================

1. Only local node:

        wishful-agent --config ./config_local.yaml

2. Global and local nodes (run with -v for debug mode):
        # start broker to enable data exchange
        wishful-broker

        # start global node
        cd ./examples/simple_controller
        wishful-agent --config ./config_master.yaml

        # start local node
        cd ./examples/simple_controller
        wishful-agent --config ./config_slave.yaml
