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