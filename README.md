WiSHFUL repository wrapper
==========================

Useful links:

- http://source.android.com/source/using-repo.html
- http://www.instructables.com/id/Using-Googles-repo-command-in-your-own-projects/
- http://xda-university.com/as-a-developer/repo-tips-tricks

Usage:

- Download git-repo

        wget https://storage.googleapis.com/git-repo-downloads/repo
        chmod a+x ./repo

- Now that we have repo, you can clone all your projects in one easy command.

        ./repo init -u ssh://git@gitlab.tubit.tu-berlin.de/wishful/wishful_manifests.git

- Then from there just run:

        # to get all repositories
        ./repo sync
        # to create master branch on all
        ./repo start master --all
        # to check status of all repositories
        ./repo status

- Create virtual environment:

        #create virtual environment
        virtualenv dev

        #activate it
        source ./dev/bin/activate

        #install all dependencies (if all needed)
        pip install -U -r ./.repo/manifests/requirements.txt

        #run example controller
        #to enable debug mode run with parameter -v
        cd ./examples/simple
        ./wishful_simple_controller --config ./controller_config.yaml

        #run example agent
        #to enable debug mode run with parameter -v
        cd ./examples/simple
        ./wishful_simple_agent --config ./agent_config.yaml

        #deactivate virtual environment (if you need to exit)
        deactivate

