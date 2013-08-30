Github collaboration workflow
-----------------------------

Steps to follow when you see a repository in Github that you want to customize for your own use and also collaborate with: 

* Fork desired repository from your github account

* Clone fork in your computer: 

If you use Python, clone package in your src directory with: 

    $ pip install -e git+[github_fork_https_url]#egg=[package_name]

To install in such a way that any source change will be visible right away without reinstall each time: 

    $ cd src/[package_name]
      $ python setup.py develop 

* Add upstream repo: 

    $ git remote add upstream [github_original_https_url]

* Create “development” branch to put your changes and test them before merge in master

* If you want suggest a patch to upstream repo, use “Pull Request” in Github account. Beware put patch commits in ad-hoc branch derived from master, since all commits you put later in the branch will be added to pull request  

* From time to time pull upstream if you want your fork synchronized

* Note that commits to forked repos don't add to "Your Contributions" stats. In turn pull requests do 
