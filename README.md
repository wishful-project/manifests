WiSHFUL repository wrapper
==========================

Useful links:

- http://source.android.com/source/using-repo.html
- http://www.instructables.com/id/Using-Googles-repo-command-in-your-own-projects/
- http://xda-university.com/as-a-developer/repo-tips-tricks

Usage:

- Download git-repo

        curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
        chmod a+x ~/bin/repo

- Now that we have repo, you can clone all your projects in one easy command.

        repo init -u ssh://git@gitlab.tubit.tu-berlin.de/wishful/wishful_manifests.git

- Then from there just run:

        # to get all repositories
        repo sync
        # to create master branch on all
        repo start master --all
