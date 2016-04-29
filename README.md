WiSHFUL repository wrapper
==========================

1. Create an account at our gitlab -> Go to: https://gitlab2.tkn.tu-berlin.de/
2. Upload your public key into you account settings.

Usage:

- Requirements:

        sudo apt-get install wget git python python-virtualenv python-dev python3-dev python3-pip

- Download git-repo

        wget https://storage.googleapis.com/git-repo-downloads/repo
        chmod a+x ./repo

- Now that we have repo, you can clone all your projects in one easy command.

        ./repo init -u ssh://git@gitlab.tkn.tu-berlin.de/wishful/wishful_manifests.git

- Then from there just run:

        # to get all repositories
        ./repo sync
        # to create master branch on all
        ./repo start master --all
        # to check status of all repositories
        ./repo status

- Install project:

        #create virtual environment
        virtualenv -p /usr/bin/python3 ./dev

        #activate it
        source ./dev/bin/activate

        #install all dependencies (if all needed)
        pip3 install -U -r ./.repo/manifests/requirements.txt

        #deactivate virtual environment (if you need to exit)
        deactivate

- Run example:

        #run example controller
        #to enable debug mode run with parameter -v
        cd ./examples/simple
        ./wishful_simple_controller --config ./controller_config.yaml

        #run example agent
        #to enable debug mode run with parameter -v
        cd ./examples/simple
        ./wishful_simple_agent --config ./agent_config.yaml
