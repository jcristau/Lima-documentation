Prerequisite
============


For collaborative development, we use the "Fork & Pull" model from github.com. So anyone who wants to contribute needs an account on github.com. Then you need to fork the project you want to contribute.


If you want to contribute with a new camera plugin you should first request us (by email @ lima@esrf.fr) to get the new
plugin camera submodule created. Then, as abow you will need to fork the submodule project.


Create a github account
```````````````````````

This is an easy task, you have to go to `Sign up - Github`_

  .. _Sign up - Github: https://github.com/signup/free

Fork a project
``````````````

On the `github`_ site, It is far better explained than I could do ;)

   .. _github: https://help.github.com/articles/fork-a-repo

Contribute
==========

At this stage you have to create a branch for a new feature or for a bug fix.

Do as many commit as you need with clear comment.
Prefer atomic commit with single change rather than a huge commit with too many changes inside.

Then submit a `pull request`_

     .. _pull request: https://help.github.com/articles/using-pull-requests


The pull request will be rejected if:

    - the new code doesn't compile
    - break backword compatibility
    - the python wrapping is missing or not updated
    - commit's comment doesn't describe what you actually do
    
In case of a new camera plugin submodule the first pull request will be rejected if:
    - as above
    - the documentation is missing or if it does follow the guidelines (e.i :ref:`guidelines`)
