# NAME

ci-test - The wrapper to run circleCI test locally

# SYNOPSIS

     # single job
     ci-test.pl circleci-config-file job-name
     # all jobs
     ci-test.pl circleci-config-file
     # run tests under current directory
     ci-test.pl

# DESCRIPTION

Run circleci test locally.

This script assume you put all dependency repos in one directory, say, /home/somebody/git/regentmarkets.
Please make sure all dependency repos are there. Don't forget _travis-scripts_. It is required when starting services in docker.

When you test a repo, you can run script as:

    ci-test.pl repo/.circleci/config.yml

The script will map repo/.. to docker's /home/git/regentmarkets. And then test script can access those codes. It will not do _git pull_ on your local directory.
So it's your task to update those repos.
