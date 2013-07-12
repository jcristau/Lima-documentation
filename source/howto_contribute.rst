Prerequisite
============


For collaborative development, we use the "Fork & Pull" model from github.com. So anyone who wants to contribute needs an account on github.com. Then you need to fork the project you want to contribute.


If you want to contribute with a new camera plugin you should first request us (by email @ lima@esrf.fr) to get the new
plug-in camera sub-module created. Then, as above you will need to fork the submodule project.


Create a github account
```````````````````````

This is an easy task, you have to go to `Sign up - Github`_

  .. _Sign up - Github: https://github.com/signup/free

Fork a project
``````````````

On the `github`_ site, It is far better explained than we could do ;)

   .. _github: https://help.github.com/articles/fork-a-repo

Contribute guideline
====================

It is very simple to contribute, you should follow the steps below. 

 1. Branch

 First of all you have to create a branch for a new feature or for a bug fix, use a explicit
 branch name, for instance "soleil_video_patch" .

 2. Code/patch
 
  If it's a patch from an existing module, respect and keep the coding style of the previous programmer (indentation,variable naming,end-line...)
  If you're starting a new camera project, you've just to respect few rules:
    - Class member must start with 'm_'
    - Class method must be in camel case
    - You must define the camera's namespace

 3. Commit
 
  Do as many commit as you need with clear comment.
  Prefer atomic commit with single change rather than a huge commit with too many changes inside.

 4. Pull Request

  Then submit a `pull request`_

     .. _pull request: https://help.github.com/articles/using-pull-requests

 At this stage you have to wait, we need sometimes to accept or reject your request.
 So there are two possible issues:

    1. The Pull-request is accepted:

    we merge your branch with the the main project master branch, then everything is fine and you can
    now synchronize your forked project with the main project.
  
    2. The pull-request is rejected:
    
    The pull request could be rejected if:

      - the new code doesn't compile
      - it breaks backword compatibility
      - the python wrapping is missing or not updated
      - the commit log message doesn't describe what you actually do
    
      In case of a new camera plugin submodule the first pull request will be rejected if:
      - as above
      - the documentation is missing or if it does follow the guidelines (e.i :ref:`guidelines`)

      You will be informed by a message (github pull-request interface) where we can give you some advises
      to improve the next pull-request.
      At this stage you have to return itme 2. and try again to submit the pull-request.


..  LocalWords:  namespace repo Github github
