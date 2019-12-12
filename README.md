# Multiple submodules example

## How to create a sub module

1. Create a main project in github

https://github.com/zhouhao27/multi-modules

2. Create a local directory `multi-modules`

```
$ git init
$ git add .
$ git commit -m "Initial commit"
$ git remote add origin https://github.com/zhouhao27/multi-modules.git
$ git push -u origin master
```

3. Create a sub modules `sub-project1` in github

https://github.com/zhouhao27/sub-project1

4. Add sub module in main repository

```
$ git submodule add https://github.com/zhouhao27/sub-project1
```

5. Add and commit the changes to main repository

```
$ git add .
$ git commit -m "Add sub module sub-project1"
$ git push
```

## How to update a sub module

1. Modify the sub module

```
# Do modification
$ cd sub-project1
$ touch test.txt
$ git add .
$ git commit -m "Add a new file"
$ git push

# Commit in main repository
$ git add sub-project1
$ git commit -m "Modify sub-project1"
$ git push
```

2. The sub module updated by the others

```
# Goto sub module folder
$ git pull
```

> So that means we have to know there is a modifications in the sub module. `git status` won't see the changes. 

```
# Goto main repository
$ git add sub-project1
$ git commit -m "sub-project1 updated"
$ git push
```

> So there is another way to do all these by using `git submodule update --remote`

```
# Change the sub module by somebody else
$ git submodule update --remote

# The submodule will become `HEAD detached at 00fd30d`
$ cd sub-project1

# Create the branch
$ git checkout -b 00fd30d
$ git checkout master
$ git merge 00fd30d

# Commit in main repository
$ git add sub-project1
$ git commit -m "Update"
$ git push
```

> To simplify, should use `git submodule update --remote --merge` so that we don't need to merge manually.

## How to clone with submodules






