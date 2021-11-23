---
layout: post
title: Clearing notebook outputs when comitting to git
post_description: Clearning ipython notebook outputs when committing to git
excerpt_separator: <!--more-->
---
# Clearing notebook outputs when comitting to git

Committing notebooks to git is nice, but committing withoutputs can be troublesome. You want the code to be open but not neccessarily the outputs of your particular use case.

Using this method you can keep the outputs local and commit notebooks that do not contain cell outputs.

In you root folder for the repom you'll need 2 new files


.gitattributes
```*
.ipynb filter=jupyternotebook
```
and


.gitconfig 
```
[filter "jupyternotebook"]
	clean = "jupyter nbconvert --ClearOutputPreprocessor.enabled=True --to=notebook --stdin --stdout --log-level=ERROR"
```

You will then need to run this command from the terminal while in the repos root.
`git config --local include.path ../.gitconfig`
This will add a reference to the new .gitconfig file to the local config file for thios one repo