# Python GIT Library

- License: BSD
- Pythons: Python 3.5+
- Platforms: Linux
##
This library is Just What You Need when working with git repositories from Python.
It is simple, but extremely flexible.

Provides Commit objects and easy branch inspection.

Git.run() method returns subprocess.run() results, but takes git command as string argument.

## Setup

Append downloaded repository path to PYTHONPATH.

## Quickstart

Import Git class:
```python
from atudomain.git.Git import Git
```

Create Git object:
```python
git = Git('/home/user/example-repo')
```

Get list of remote origin branches:
```python
branches = git.get_branches(include='^remotes/origin')
```

Get list of local branches:
```python
branches = git.get_branches(exclude='^remotes/')
```

Get list of Commits for the current branch:
```python
commits = git.get_commits()
```

Get list with last Commit for the current branch:
```python
commits = git.get_commits('HEAD^..HEAD')
```

Get committer date from Commit:
```python
committer_date = commits[0].committer_date
```

Get commit id from Commit:
```python
commit_id = commits[0].commit_id
```

Check if Commit is a merge:
```python
is_merge = commits[0].is_merge
```

Get 'git status -s' output as a string:
```python
result = git.run('status -s').stdout
```

